# Module Analysis: notifications-content-marketing

Review state: Partial source trace completed for in-app notification list and admin creation; email/newsletter/template flows pending.

## Findings

Public content, search, newsletter, email and notification surfaces are inventoried. Trigger-to-template-recipient mapping, opt-out, retries, request schemas, and persistence effects are pending.

## API route files

- src/app/api/v1/blog/route.ts
- src/app/api/v1/blog/analytics/route.ts
- src/app/api/v1/blog/[id]/route.ts
- src/app/api/v1/blog/[id]/approve/route.ts
- src/app/api/v1/blog/[id]/engagement/route.ts
- src/app/api/v1/career-quiz/results/route.ts
- src/app/api/v1/email/opt-outs/route.ts
- src/app/api/v1/email/test/route.ts
- src/app/api/v1/email/unsubscribe/route.ts
- src/app/api/v1/newsletter/confirm/route.ts
- src/app/api/v1/newsletter/subscribe/route.ts
- src/app/api/v1/newsletter/unsubscribe/route.ts
- src/app/api/v1/notification-templates/route.ts
- src/app/api/v1/notification-templates/[id]/route.ts
- src/app/api/v1/notifications/route.ts
- src/app/api/v1/notifications/broadcast/route.ts
- src/app/api/v1/notifications/preferences/route.ts
- src/app/api/v1/notifications/read-all/route.ts
- src/app/api/v1/notifications/[id]/read/route.ts
- src/app/api/v1/public/mentors/route.ts
- src/app/api/v1/search/route.ts
- src/app/api/v1/search/sync/route.ts

## Frontend pages

- src/app/(public)/page.tsx
- src/app/(public)/about/page.tsx
- src/app/(public)/become-instructor/page.tsx
- src/app/(public)/blog/page.tsx
- src/app/(public)/blog/[slug]/page.tsx
- src/app/(public)/certificates/verify/page.tsx
- src/app/(public)/certificates/verify/[code]/page.tsx
- src/app/(public)/compare/page.tsx
- src/app/(public)/compare/ceh-vs-oscp/page.tsx
- src/app/(public)/compare/security-plus-vs-ceh/page.tsx
- src/app/(public)/courses/page.tsx
- src/app/(public)/courses/[slug]/page.tsx
- src/app/(public)/courses/[slug]/offer/page.tsx
- src/app/(public)/credentials/verify/page.tsx
- src/app/(public)/credentials/verify/badge/[hash]/page.tsx
- src/app/(public)/events/page.tsx
- src/app/(public)/events/[id]/page.tsx
- src/app/(public)/events/[id]/room/page.tsx
- src/app/(public)/glossary/page.tsx
- src/app/(public)/instructors/[id]/page.tsx
- src/app/(public)/mentors/page.tsx
- src/app/(public)/newsletter/confirm/page.tsx
- src/app/(public)/partners/apply/page.tsx
- src/app/(public)/passport/[token]/page.tsx
- src/app/(public)/paths/page.tsx
- src/app/(public)/paths/[slug]/page.tsx
- src/app/(public)/portfolio/[userId]/page.tsx
- src/app/(public)/pricing/page.tsx
- src/app/(public)/privacy/page.tsx
- src/app/(public)/refund-policy/page.tsx
- src/app/(public)/search/page.tsx
- src/app/(public)/security/page.tsx
- src/app/(public)/store/page.tsx
- src/app/(public)/store/[slug]/page.tsx
- src/app/(public)/support/page.tsx
- src/app/(public)/terms/page.tsx
- src/app/(public)/tools/career-quiz/page.tsx
- src/app/(public)/tools/practice-test/page.tsx
- src/app/(public)/trust/page.tsx
- src/app/(public)/unsubscribed/page.tsx
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

## Field rules, workflows, and dependencies

Not extracted yet. Follow the UI action through route, service/domain, DB operation, and external side effect. Separate frontend validation, server schemas, and SQL/RLS constraints.

## Validation matrix

Pending source review; no field requiredness is inferred from filenames or UI labels.

## Open questions

Runtime flags, external provider behavior, and complete screen/database semantics are unverified. No tests are claimed as executed.

## Partial cross-layer finding: in-app notifications

`GET /api/v1/notifications` returns only the authenticated user's notifications, optionally filters `unread=true`, sorts newest first, paginates, and adds an independent total unread count. `POST` is admin-only; validates user UUID, title 1–200, message 1–1000, type enum `info|success|warning|error` default `info`, optional nullable link max 500; verifies target user exists then inserts. `POST /api/v1/notifications/read-all` updates only current user's unread records to read. Evidence: `src/app/api/v1/notifications/route.ts:8-60`, `src/app/api/v1/notifications/read-all/route.ts:6-16`, `src/lib/validators/platform.schemas.ts:48-54`.
