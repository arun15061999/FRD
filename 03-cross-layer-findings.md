# Cross-Layer Analysis Pass: Identity, Learning, Assessment, Commerce, Organizations

This pass follows selected high-impact operations through UI/client, API, validation, service logic, persistence, and side effects. It is intentionally scoped; each module's coverage checklist remains partial.

## Identity and access

### Sign-in trace

| Layer | Evidence / behavior |
|---|---|
| UI/client | `src/domains/identity/supabase-auth.provider.ts:120` calls `/api/v1/auth/signin`; `src/app/auth/login/page.tsx` handles resend-verification and SSO resolution. |
| API | `src/app/api/v1/auth/signin/route.ts:24` is public, manually rate-limited by IP with fail-closed behavior, and has wrapper rate limiting/CSRF disabled for this pre-session flow. |
| Validation | `src/lib/validators/identity.schemas.ts:39`: valid email; nonempty password. |
| Business logic | Checks lockout before password auth; lockout service failure returns 503; unconfirmed email returns 403; invalid credentials return 401; success clears failed counter and writes login audit event. Successful login can include a nonblocking high-volume breach warning. |
| Persistence / effects | Supabase Auth sign-in; failed-login counters and audit events; session response. Exact cookie persistence is handled in auth provider/client integration. |
| Test evidence | `src/__tests__/unit/api/v1/auth/signin.route.test.ts` and `src/__tests__/integration/auth-login-integration.test.ts` exist; not executed in this analysis. |

### Signup trace

`src/app/api/v1/auth/signup/route.ts:181` uses manual namespaced per-IP rate limit (fail closed), request validation, configurable strong-password policy, email risk checks (block known bad email; fail open on infrastructure error), and breached-password check (block if known breached; fail open on check failure). Role is constrained to `student`/`teacher`; verification redirect differs by role. With both service key and email provider configured, custom signup generates action link, provisions profile rows, sends verification with retry (up to three attempts), and rolls back partially provisioned users in failure paths. Duplicate-account attempts use a response with no user/session so the endpoint does not reveal account existence. The alternate Supabase email flow also exists; detailed branching is still to review.

## Learning content

### Course creation trace

| Layer | Evidence / behavior |
|---|---|
| UI | `src/app/instructor/courses/new/page.tsx:135` is the create/edit wizard; `saveCourse` creates draft payload and sends `teacher_id`, `is_published:false`, `status:'draft'`, `approval_status:'draft'`; new course submit navigates to lessons first because approval submission requires lessons. |
| Client service | `src/domains/learning/course.service.ts:90` POSTs JSON to `/api/v1/courses`; update uses PATCH `/api/v1/courses/[id]`. |
| API | `src/app/api/v1/courses/route.ts:273`; roles admin/teacher, optional API key with `courses:write`. |
| Schema | `src/lib/validators/learning.schemas.ts` course base/create/update schemas; full field list in FRD §11. |
| Persistence | inserts `courses`, selects category and teacher; optional unsupported columns may be stripped and retried; duplicate unique violation becomes conflict. Audit record follows successful creation. |
| Recovery/UI | Save errors show toast and release saving state. New course creation routes to edit or lessons based on action. |

## Assessment and grading

### Assignment listing and grade trace

`GET /api/v1/assignments` in `src/app/api/v1/assignments/route.ts:48` scopes a teacher to their teacher ID; for students it resolves student profile and enrolled course IDs, returning empty page when no profile/enrollments exist, and filters to published assignments. It supports course/published/scenario filters and pagination. Student responses are passed through `sanitizeCodeConfigForStudent` to remove hidden test harness content. Rich relation projection failure retries a reduced select.

`POST /api/v1/submissions/[submissionId]/grade` in `src/app/api/v1/submissions/[submissionId]/grade/route.ts:87` is admin/teacher only. A teacher's inaccessible submission is returned as not found after access resolution to avoid ID probing. Rubric grading checks attached rubric identity and deletion, validates criteria through `rubricService`, clamps criterion scores, records raw/submitted and final values, applies late penalty once through `recordAssignmentGrade`, audits the write, then triggers `assignment.reviewed`, student notification, competency updates, and event tracking on best-effort paths.

Schema caution: `src/lib/validators/assignments.schemas.ts` exports `createAssignmentSecureSchema`, `submitAssignmentSchema`, and `gradeAssignmentSchema`. The inspected `/api/v1/assignments` route imports `createAssignmentSchema` from `learning.schemas.ts`; do not attribute the secure schema's exact rules to that route without checking every handler. The grade endpoint also uses local `rubricGradeSchema` and `gradeSubmissionSchema` paths.

## Commerce and payments

### Quote trace

`POST /api/v1/checkout/quote` (`src/app/api/v1/checkout/quote/route.ts:8,27`) requires exactly one of course/bundle ID; supports up to 10 bump IDs, coupon, student referral, and referral credit. It invokes `priceCheckout` read-only. `src/domains/commerce/checkout-pricing.server.ts:241` loads item, checks availability/currency/price, adds eligible bump lines, applies coupon (bounded by subtotal), referral discount (bounded by remaining), referral credit (bounded by balance and minimum charge), computes taxable amount, GST, and rounded total. It returns explicit error codes for absent/unavailable course or bundle, currency mismatch, invalid bundle price, unavailable bump, and invalid coupon/referral.

### Payment verification trace

`POST /api/v1/razorpay/verify` (`src/app/api/v1/razorpay/verify/route.ts:27,40`) validates provider order ID, payment ID, and signature as nonempty strings; requires admin/teacher/student. It verifies signature and routes fulfillment through shared order fulfillment. Order status transition uses a compare-and-set style helper; retries fulfillment; unfulfillable paid orders are left paid and queue refund review. Emails run only for the winning fulfillment transition. Accounting is settled idempotently. Runtime provider calls not executed.

## Organization and tenant administration

### Organization and invitation trace

`POST /api/v1/organizations` (`src/app/api/v1/organizations/route.ts:10,55`) is admin-only; strict object schema; name length 2–200; optional lowercase slug length 2–200; `is_active` optional/default true; generated slug lowercases/trims and replaces non-alphanumerics with hyphen; unique constraint maps to 409; creates audit record.

`POST /api/v1/organizations/[id]/members` (`src/app/api/v1/organizations/[id]/members/route.ts:59,208`) is managed through organization access helper. Strict payload role enum is owner/admin/member; optional `user_id` UUID and email are resolved by `inviteMember`; handler rejects duplicate membership; creates invitation and sends email, but does not immediately create membership. `GET/POST /api/v1/organization-invitations/[token]` (`src/app/api/v1/organization-invitations/[token]/route.ts:24,44`) requires a signed-in user whose email matches invitation address; mismatched token/email is presented as 404. POST accepts strict `accept` or `decline`; acceptance delegates to invitation service and audits result.

Tenant context is built by `src/lib/middleware/tenant-isolation.ts:134`; organization selector precedence is explicit param → `org_id` query → `x-organization-id` → auth context. Admin is cross-org allowed; non-admin needs membership; missing required context yields 400 and denied membership yields 403.

## Remaining cross-layer work

The module notes and checklist identify unfinished API/page groups. This pass does not cover every component, controller/service, migration, SQL constraint, screen state, external integration, or test. No runtime behavior or tests are asserted as verified.
