# Module Analysis: identity-access

Review state: Partial detailed trace.

## Findings

Sign-in validates signInSchema; rate limits by client IP; applies configured account lockout before password verification; calls Supabase password auth; records failed-login audit; handles unconfirmed email separately; returns generic invalid credentials otherwise. Signup code includes risk/password/breach checks, provisioning, email verification, duplicate-account privacy response, and rollback. KYC applicant route gating is in middleware.

## Frontend pages

- src/app/auth/forgot-password/page.tsx
- src/app/auth/login/page.tsx
- src/app/auth/lti-error/page.tsx
- src/app/auth/reset-password/page.tsx
- src/app/auth/signup/page.tsx
- src/app/auth/two-factor/page.tsx
- src/app/auth/two-factor/setup/page.tsx
- src/app/auth/verify-email/page.tsx

## API route files and methods

- src/app/api/v1/auth/2fa/challenge/route.ts — POST
- src/app/api/v1/auth/2fa/disable/route.ts — POST
- src/app/api/v1/auth/2fa/enable/route.ts — POST
- src/app/api/v1/auth/2fa/recovery-codes/route.ts — POST
- src/app/api/v1/auth/2fa/session/route.ts — DELETE
- src/app/api/v1/auth/2fa/setup/route.ts — POST
- src/app/api/v1/auth/2fa/status/route.ts — GET
- src/app/api/v1/auth/forgot-password/route.ts — POST
- src/app/api/v1/auth/me/route.ts — GET
- src/app/api/v1/auth/policy/route.ts — GET
- src/app/api/v1/auth/resend-verification/route.ts — POST
- src/app/api/v1/auth/signin/route.ts — POST
- src/app/api/v1/auth/signout/route.ts — POST
- src/app/api/v1/auth/signout-others/route.ts — POST
- src/app/api/v1/auth/signup/route.ts — POST
- src/app/api/v1/auth/sso/resolve/route.ts — GET
- src/app/api/v1/auth/update-password/route.ts — POST
- src/app/api/v1/me/public-profile/route.ts — GET, PATCH
- src/app/api/v1/policy-acceptances/route.ts — GET, POST
- src/app/api/v1/preferences/burnout/route.ts — GET, PATCH
- src/app/api/v1/preferences/recommendations/route.ts — GET, PUT
- src/app/api/v1/privacy/consent/route.ts — POST
- src/app/api/v1/privacy/delete/route.ts — POST
- src/app/api/v1/privacy/export/route.ts — GET
- src/app/api/v1/security/zero-trust/challenge/route.ts — POST, PUT
- src/app/api/v1/security/zero-trust/device/route.ts — DELETE, GET, POST
- src/app/api/v1/security/zero-trust/security-questions/route.ts — GET, PUT
- src/app/api/v1/security/zero-trust/verify/route.ts — POST
- src/app/api/v1/student/my-courses/route.ts — GET
- src/app/api/v1/student/surveys/route.ts — POST
- src/app/api/v1/student/video-events/route.ts — POST
- src/app/api/v1/students/route.ts — GET, POST
- src/app/api/v1/students/cyber-badges/route.ts — GET
- src/app/api/v1/students/cyber-progress/route.ts — GET
- src/app/api/v1/students/invite/route.ts — POST
- src/app/api/v1/students/[id]/route.ts — GET, PATCH
- src/app/api/v1/students/[id]/objectives/progress/route.ts — GET
- src/app/api/v1/students/[id]/objectives/[objectiveId]/master/route.ts — POST
- src/app/api/v1/teachers/route.ts — GET
- src/app/api/v1/teachers/invite/route.ts — POST
- src/app/api/v1/teachers/me/route.ts — GET, PATCH
- src/app/api/v1/teachers/[id]/route.ts — DELETE, GET, PATCH
- src/app/api/v1/user/route.ts — GET
- src/app/api/v1/users/route.ts — GET, POST
- src/app/api/v1/users/[id]/route.ts — DELETE, GET, PATCH

## Validation, fields, data and workflow coverage

Field-level rules and traced workflow facts are listed in Findings and cross-referenced in FRD §§9, 11–14. UI versus API versus SQL constraints are not yet reconciled module-wide.

Pending for complete module sign-off: enumerate every screen action; extract route schemas/request/response; trace service calls and table writes; compare Zod rules with UI and migration constraints; record success/error/alternate flows; map tests to stable IDs.

## Dependencies and evidence

Inventory source: docs/frd-analysis/00-repository-inventory.md. Core shared evidence includes src/lib/api/with-api.ts, src/lib/roles.ts and Supabase migrations/RLS. Domain-specific source evidence is cited by repository-relative route and schema paths in Findings and FRD.

## Unresolved questions

Runtime configuration, deployed feature toggles, external-provider response behavior, and uninspected screen/database details remain unverified. No tests are claimed as executed.
