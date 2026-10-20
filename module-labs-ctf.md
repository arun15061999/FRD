# Module Analysis: labs-ctf

Review state: Partial source trace completed for lab authoring and CTF flag submission; remaining lab session/container and CTF lifecycle flows pending.

## Findings

Environment example comments state absent container host degrades labs/CTF to read-only and image allowlist is default deny. Challenge lifecycle, flag scoring, provisioning, isolation, access rules, and database effects remain untraced.

## Frontend pages

- src/app/admin/page.tsx
- src/app/admin/achievements/page.tsx
- src/app/admin/affiliates/page.tsx
- src/app/admin/analytics/page.tsx
- src/app/admin/analytics/churn/page.tsx
- src/app/admin/assignments/page.tsx
- src/app/admin/assignments/submissions/page.tsx
- src/app/admin/audit/page.tsx
- src/app/admin/badges/page.tsx
- src/app/admin/battle-pass/page.tsx
- src/app/admin/blog/page.tsx
- src/app/admin/bulk-import/page.tsx
- src/app/admin/careers/page.tsx
- src/app/admin/categories/page.tsx
- src/app/admin/certificate-templates/page.tsx
- src/app/admin/certificate-templates/new/page.tsx
- src/app/admin/certificate-templates/[id]/edit/page.tsx
- src/app/admin/certificates/page.tsx
- src/app/admin/chat-reports/page.tsx
- src/app/admin/community-challenges/page.tsx
- src/app/admin/community-moderation/page.tsx
- src/app/admin/competencies/page.tsx
- src/app/admin/compliance/data-residency/page.tsx
- src/app/admin/coupons/page.tsx
- src/app/admin/courses/page.tsx
- src/app/admin/courses/approvals/page.tsx
- src/app/admin/courses/featured/page.tsx
- src/app/admin/courses/import/page.tsx
- src/app/admin/courses/new/page.tsx
- src/app/admin/courses/revisions/page.tsx
- src/app/admin/credentials/award/page.tsx
- src/app/admin/ctf/page.tsx
- src/app/admin/ctf/challenges/new/page.tsx
- src/app/admin/ctf/challenges/[id]/page.tsx
- src/app/admin/ctf/competitions/new/page.tsx
- src/app/admin/ctf/competitions/[id]/page.tsx
- src/app/admin/dashboard/page.tsx
- src/app/admin/dashboard/benchmarking/page.tsx
- src/app/admin/dashboard/cohorts/[id]/page.tsx
- src/app/admin/email/page.tsx
- src/app/admin/events/page.tsx
- src/app/admin/events/settings/page.tsx
- src/app/admin/exams/page.tsx
- src/app/admin/exams/approvals/page.tsx
- src/app/admin/exams/attempts/page.tsx
- src/app/admin/exams/[id]/page.tsx
- src/app/admin/exams/[id]/accommodations/page.tsx
- src/app/admin/feedback/page.tsx
- src/app/admin/forum-moderation/page.tsx
- src/app/admin/grade-appeals/page.tsx
- src/app/admin/integrations/health/page.tsx
- src/app/admin/integrations/plugins/page.tsx
- src/app/admin/kyc-templates/page.tsx
- src/app/admin/leaderboard-seasons/page.tsx
- src/app/admin/learner-intelligence/page.tsx
- src/app/admin/learning-analytics/page.tsx
- src/app/admin/learning-paths/page.tsx
- src/app/admin/lti-platforms/page.tsx
- src/app/admin/memberships/page.tsx
- src/app/admin/mentors/page.tsx
- src/app/admin/micro-credentials/page.tsx
- src/app/admin/moderation/page.tsx
- src/app/admin/monitoring/page.tsx
- src/app/admin/monitoring/crons/page.tsx
- src/app/admin/monitoring/dashboard-health/page.tsx
- src/app/admin/monitoring/incidents/page.tsx
- src/app/admin/monitoring/jobs/page.tsx
- src/app/admin/monitoring/system-health/page.tsx
- src/app/admin/newsletter/page.tsx
- src/app/admin/notification-templates/page.tsx
- src/app/admin/notifications/page.tsx
- src/app/admin/objectives/page.tsx
- src/app/admin/orders/page.tsx
- src/app/admin/organizations/page.tsx
- src/app/admin/organizations/applications/page.tsx
- src/app/admin/organizations/[id]/page.tsx
- src/app/admin/organizations/[id]/dashboard/page.tsx
- src/app/admin/organizations/[id]/dashboard/compliance/page.tsx
- src/app/admin/organizations/[id]/dashboard/customize/page.tsx
- src/app/admin/organizations/[id]/dashboard/exports/page.tsx
- src/app/admin/organizations/[id]/dashboard/roi/page.tsx
- src/app/admin/organizations/[id]/dashboard/skills/page.tsx
- src/app/admin/organizations/[id]/departments/page.tsx
- src/app/admin/organizations/[id]/departments/[deptId]/members/page.tsx
- src/app/admin/organizations/[id]/white-label/page.tsx
- src/app/admin/payouts/page.tsx
- src/app/admin/peer-reviews/page.tsx
- src/app/admin/products/page.tsx
- src/app/admin/products/create/page.tsx
- src/app/admin/products/[id]/edit/page.tsx
- src/app/admin/question-bank/page.tsx
- src/app/admin/reports/page.tsx
- src/app/admin/reports/create/page.tsx
- src/app/admin/reports/[id]/edit/page.tsx
- src/app/admin/reports/[id]/exports/page.tsx
- src/app/admin/reviews/page.tsx
- src/app/admin/risk-signals/page.tsx
- src/app/admin/rubrics/page.tsx
- src/app/admin/rubrics/create/page.tsx
- src/app/admin/rubrics/[id]/page.tsx
- src/app/admin/security/page.tsx
- src/app/admin/security/devices/page.tsx
- src/app/admin/security/records/page.tsx
- src/app/admin/settings/page.tsx
- src/app/admin/settings/automation/page.tsx
- src/app/admin/shop/page.tsx
- src/app/admin/students/page.tsx
- src/app/admin/support/page.tsx
- src/app/admin/teachers/page.tsx
- src/app/admin/teachers/kyc-verification/page.tsx
- src/app/admin/teachers/[id]/kyc-review/page.tsx
- src/app/admin/users/page.tsx
- src/app/admin/users/orphans/page.tsx
- src/app/admin/webhooks/page.tsx
- src/app/admin/webhooks/dashboard/page.tsx
- src/app/ctf-portal/page.tsx
- src/app/instructor/page.tsx
- src/app/instructor/accessibility/page.tsx
- src/app/instructor/accessibility/[courseId]/page.tsx
- src/app/instructor/affiliates/page.tsx
- src/app/instructor/affiliates/portal/page.tsx
- src/app/instructor/ai-suggestions/page.tsx
- src/app/instructor/analytics/page.tsx
- src/app/instructor/analytics/courses/[courseId]/page.tsx
- src/app/instructor/analytics/predictive/page.tsx
- src/app/instructor/assignments/page.tsx
- src/app/instructor/assignments/create/page.tsx
- src/app/instructor/assignments/grading-queue/page.tsx
- src/app/instructor/assignments/[id]/appeals/page.tsx
- src/app/instructor/assignments/[id]/code-config/page.tsx
- src/app/instructor/assignments/[id]/edit/page.tsx
- src/app/instructor/assignments/[id]/extensions/page.tsx
- src/app/instructor/assignments/[id]/peer-reviews/page.tsx
- src/app/instructor/assignments/[id]/plagiarism/page.tsx
- src/app/instructor/assignments/[id]/rubric/page.tsx
- src/app/instructor/assignments/[id]/submissions/page.tsx
- src/app/instructor/assignments/[id]/submissions/[submissionId]/page.tsx
- src/app/instructor/assignments/[id]/submissions/[submissionId]/grade/page.tsx
- src/app/instructor/attendance/page.tsx
- src/app/instructor/blog/page.tsx
- src/app/instructor/blog/new/page.tsx
- src/app/instructor/blog/[id]/edit/page.tsx
- src/app/instructor/bulk-operations/page.tsx
- src/app/instructor/cart-recovery/page.tsx
- src/app/instructor/cart-recovery/settings/page.tsx
- src/app/instructor/certificates/page.tsx
- src/app/instructor/chat/page.tsx
- src/app/instructor/checkout-offers/page.tsx
- src/app/instructor/coauthor-invitations/page.tsx
- src/app/instructor/command-center/page.tsx
- src/app/instructor/community-challenges/page.tsx
- src/app/instructor/competencies/page.tsx
- src/app/instructor/competencies/triggers/page.tsx
- src/app/instructor/content-gap-reports/page.tsx
- src/app/instructor/coupons/page.tsx
- src/app/instructor/course-import-jobs/page.tsx
- src/app/instructor/course-templates/page.tsx
- src/app/instructor/courses/page.tsx
- src/app/instructor/courses/freshness/page.tsx
- src/app/instructor/courses/new/page.tsx
- src/app/instructor/courses/[id]/page.tsx
- src/app/instructor/courses/[id]/analytics/page.tsx
- src/app/instructor/courses/[id]/assignment-groups/page.tsx
- src/app/instructor/courses/[id]/broadcast/page.tsx
- src/app/instructor/courses/[id]/coauthors/page.tsx
- src/app/instructor/courses/[id]/edit/page.tsx
- src/app/instructor/courses/[id]/exams/[examId]/proctoring/page.tsx
- src/app/instructor/courses/[id]/forum/page.tsx
- src/app/instructor/courses/[id]/forum/[threadId]/page.tsx
- src/app/instructor/courses/[id]/friction-map/page.tsx
- src/app/instructor/courses/[id]/gamification/page.tsx
- src/app/instructor/courses/[id]/grade-settings/page.tsx
- src/app/instructor/courses/[id]/grading/page.tsx
- src/app/instructor/courses/[id]/labs/page.tsx
- src/app/instructor/courses/[id]/lessons/page.tsx
- src/app/instructor/courses/[id]/lessons/[lessonId]/interactive/page.tsx
- src/app/instructor/courses/[id]/practice-labs/page.tsx
- src/app/instructor/courses/[id]/preview/page.tsx
- src/app/instructor/courses/[id]/sales-page/page.tsx
- src/app/instructor/courses/[id]/video-intelligence/page.tsx
- src/app/instructor/ctf/page.tsx
- src/app/instructor/ctf/challenges/page.tsx
- src/app/instructor/ctf/challenges/new/page.tsx
- src/app/instructor/ctf/competitions/new/page.tsx
- src/app/instructor/ctf/competitions/[id]/page.tsx
- src/app/instructor/ctf/[id]/page.tsx
- src/app/instructor/dashboard/page.tsx
- src/app/instructor/dashboard/command-center/page.tsx
- src/app/instructor/earnings/page.tsx
- src/app/instructor/email-campaigns/page.tsx
- src/app/instructor/email-campaigns/new/page.tsx
- src/app/instructor/exams/page.tsx
- src/app/instructor/exams/create/page.tsx
- src/app/instructor/exams/grading-queue/page.tsx
- src/app/instructor/exams/proctoring/page.tsx
- src/app/instructor/exams/question-analysis/page.tsx
- src/app/instructor/exams/results/page.tsx
- src/app/instructor/exams/[id]/page.tsx
- src/app/instructor/exams/[id]/accommodations/page.tsx
- src/app/instructor/exams/[id]/analytics/page.tsx
- src/app/instructor/exams/[id]/appeals/page.tsx
- src/app/instructor/exams/[id]/attempts/[attemptId]/grade/page.tsx
- src/app/instructor/exams/[id]/results/page.tsx
- src/app/instructor/exams/[id]/team-sessions/page.tsx
- src/app/instructor/feedback/page.tsx
- src/app/instructor/forums/page.tsx
- src/app/instructor/friction-map/page.tsx
- src/app/instructor/friction-map/[courseId]/page.tsx
- src/app/instructor/grading/page.tsx
- src/app/instructor/grading/anonymous/page.tsx
- src/app/instructor/grading/messages/page.tsx
- src/app/instructor/learning-funnel/page.tsx
- src/app/instructor/learning-objectives/page.tsx
- src/app/instructor/learning-objectives/create/page.tsx
- src/app/instructor/learning-paths/page.tsx
- src/app/instructor/learning-paths/[id]/page.tsx
- src/app/instructor/live-sessions/page.tsx
- src/app/instructor/live-sessions/attendance/page.tsx
- src/app/instructor/live-sessions/course/page.tsx
- src/app/instructor/live-sessions/[id]/classroom/page.tsx
- src/app/instructor/live-sessions/[id]/manage/page.tsx
- src/app/instructor/live-sessions/[id]/stream/page.tsx
- src/app/instructor/lms-integrations/page.tsx
- src/app/instructor/marketplace/page.tsx
- src/app/instructor/mentorship/page.tsx
- src/app/instructor/mentorship/profile/page.tsx
- src/app/instructor/mentorship/[requestId]/page.tsx
- src/app/instructor/micro-credentials/page.tsx
- src/app/instructor/my-learning/page.tsx
- src/app/instructor/peer-reviews/page.tsx
- src/app/instructor/peer-reviews/auto-assign/page.tsx
- src/app/instructor/peer-reviews/moderation/page.tsx
- src/app/instructor/products/page.tsx
- src/app/instructor/products/manage/page.tsx
- src/app/instructor/products/new/page.tsx
- src/app/instructor/products/[id]/analytics/page.tsx
- src/app/instructor/profile/page.tsx
- src/app/instructor/question-bank/page.tsx
- src/app/instructor/quizzes/page.tsx
- src/app/instructor/reports/page.tsx
- src/app/instructor/resources/page.tsx
- src/app/instructor/resources/add/page.tsx
- src/app/instructor/revenue-insights/page.tsx
- src/app/instructor/reviews/page.tsx
- src/app/instructor/rubrics/page.tsx
- src/app/instructor/rubrics/create/page.tsx
- src/app/instructor/rubrics/library/page.tsx
- src/app/instructor/rubrics/[id]/edit/page.tsx
- src/app/instructor/sales/page.tsx
- src/app/instructor/scenarios/page.tsx
- src/app/instructor/scenarios/create/page.tsx
- src/app/instructor/scenarios/[id]/page.tsx
- src/app/instructor/scenarios/[id]/sessions/page.tsx
- src/app/instructor/settings/page.tsx
- src/app/instructor/settings/audit-trail/page.tsx
- src/app/instructor/students/page.tsx
- src/app/instructor/students/[id]/page.tsx
- src/app/instructor/students-at-risk/page.tsx
- src/app/instructor/study-groups/page.tsx
- src/app/instructor/study-groups/[id]/page.tsx
- src/app/instructor/support/page.tsx
- src/app/instructor/support/create/page.tsx
- src/app/instructor/support/[id]/page.tsx
- src/app/instructor/surveys/page.tsx
- src/app/instructor/verification/page.tsx
- src/app/instructor/webinars/page.tsx
- src/app/learner/adaptive-path/page.tsx
- src/app/learner/credentials/page.tsx
- src/app/learner/gamification/page.tsx
- src/app/learner/labs/page.tsx
- src/app/learner/labs/[id]/page.tsx
- src/app/learner/mentorship/page.tsx
- src/app/learner/momentum/page.tsx
- src/app/learner/skill-gaps/page.tsx
- src/app/student-ctf/page.tsx
- src/app/student-ctf/challenges/page.tsx
- src/app/student-ctf/challenges/[id]/page.tsx

## API route files and methods

- src/app/api/v1/competencies/route.ts — GET, POST
- src/app/api/v1/competencies/triggers/route.ts — GET, POST
- src/app/api/v1/competencies/triggers/[id]/route.ts — DELETE, PATCH
- src/app/api/v1/competencies/[id]/route.ts — DELETE, PATCH
- src/app/api/v1/ctf/challenges/route.ts — GET, POST
- src/app/api/v1/ctf/challenges/[id]/route.ts — DELETE, GET, PATCH
- src/app/api/v1/ctf/challenges/[id]/courses/route.ts — DELETE, GET, POST
- src/app/api/v1/ctf/challenges/[id]/hints/route.ts — GET, POST
- src/app/api/v1/ctf/challenges/[id]/hints/[hintId]/route.ts — DELETE, PATCH
- src/app/api/v1/ctf/challenges/[id]/hints/[hintId]/unlock/route.ts — POST
- src/app/api/v1/ctf/challenges/[id]/instance/route.ts — DELETE, GET, POST
- src/app/api/v1/ctf/challenges/[id]/submit/route.ts — POST
- src/app/api/v1/ctf/competitions/route.ts — GET, POST
- src/app/api/v1/ctf/competitions/[id]/route.ts — DELETE, GET, PATCH
- src/app/api/v1/ctf/competitions/[id]/challenges/route.ts — GET, POST
- src/app/api/v1/ctf/competitions/[id]/scoreboard/route.ts — GET
- src/app/api/v1/ctf/competitions/[id]/teams/route.ts — DELETE, GET, POST
- src/app/api/v1/ctf/events/route.ts — GET, POST
- src/app/api/v1/ctf/events/[id]/route.ts — DELETE, GET, PATCH
- src/app/api/v1/ctf/guild-scores/route.ts — GET, POST
- src/app/api/v1/ctf/leaderboard/route.ts — GET
- src/app/api/v1/ctf/scoreboard/route.ts — GET
- src/app/api/v1/ctf/teams/route.ts — GET, POST
- src/app/api/v1/ctf/teams/[id]/route.ts — DELETE, GET, POST
- src/app/api/v1/labs/route.ts — GET, POST
- src/app/api/v1/labs/analytics/route.ts — GET
- src/app/api/v1/labs/[labId]/route.ts — GET, PATCH
- src/app/api/v1/labs/[labId]/hint/route.ts — POST
- src/app/api/v1/labs/[labId]/run/route.ts — POST
- src/app/api/v1/labs/[labId]/start/route.ts — POST
- src/app/api/v1/labs/[labId]/stop/route.ts — POST
- src/app/api/v1/labs/[labId]/submit/route.ts — POST
- src/app/api/v1/student-competencies/route.ts — GET, POST
- src/app/api/v1/student-competencies/leaderboard/route.ts — GET
- src/app/api/v1/student-competencies/report/route.ts — GET

## Validation, fields, data and workflow coverage

Pending for complete module sign-off: enumerate every screen action; extract route schemas/request/response; trace service calls and table writes; compare Zod rules with UI and migration constraints; record success/error/alternate flows; map tests to stable IDs.

## Dependencies and evidence

Inventory source: docs/frd-analysis/00-repository-inventory.md. Core shared evidence includes src/lib/api/with-api.ts, src/lib/roles.ts and Supabase migrations/RLS. Domain-specific source evidence is cited by repository-relative route and schema paths in Findings and FRD.

## Unresolved questions

Runtime configuration, deployed feature toggles, external-provider response behavior, and uninspected screen/database details remain unverified. No tests are claimed as executed.

## Partial cross-layer findings

### Lab authoring

`POST /api/v1/labs` is teacher/admin only. `createLabSchema` is strict and requires a course UUID. It requires title (trimmed, 1–255) and language from `python`, `javascript`, `bash`; optional fields include description (max 20,000), image (validated image-reference syntax and rejects `..`), difficulty (`easy|medium|hard`), timeout (integer 1–60 seconds), memory/cpu limits (patterns), starter code (max 48 KiB), up to 50 test cases, up to 10 hints, and publication flag. Handler verifies the course is live and caller can manage its lab scope; otherwise returns not found; it persists `labs` with `is_published` default false and timestamps. Evidence: `src/lib/validators/lab.schemas.ts:4-55`, `src/app/api/v1/labs/route.ts:146+`, `src/domains/labs/lab.service.ts`.

### CTF flag attempt

`POST /api/v1/ctf/challenges/[id]/submit` rate-limits by IP, requires Safe-Use Policy acceptance, validates `flag` as nonempty string max 500, fetches nondeleted published challenge, checks challenge visibility/access and event start/end, requires team membership for team events, checks attempt cap and duplicate solve, compares submitted trimmed flag against bcrypt hashes (static or caller-specific container instance), and records attempt without plaintext flag. Correct-solve writes use a placeholder/claim pattern to avoid solve-number races and repair retry side effects idempotently. Evidence: `src/app/api/v1/ctf/challenges/[id]/submit/route.ts:226+`, `src/lib/validators/ctf.schemas.ts:100-102`.
