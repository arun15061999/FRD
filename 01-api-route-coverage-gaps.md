# API Route Coverage Gap Catalog

Generated from a path-level diff between filesystem API route files and module-specific route manifests. Each path below exists in the complete repository inventory but is not listed in an assigned module analysis note. All paths are accounted for in the repository inventory; these gap entries remain behaviorally unreviewed.

Unassigned module manifest paths: 132 of 962 total API route files. This does not imply unused or orphaned routes.

## certificates/verify (1)

- src/app/api/certificates/verify/[certNumber]/route.ts

## cron/build-profiles (1)

- src/app/api/cron/build-profiles/route.ts

## cron/refresh-segments (1)

- src/app/api/cron/refresh-segments/route.ts

## cron/score-churn (1)

- src/app/api/cron/score-churn/route.ts

## cron/system-health (1)

- src/app/api/cron/system-health/route.ts

## docs/route.ts (1)

- src/app/api/docs/route.ts

## docs/spec (1)

- src/app/api/docs/spec/route.ts

## inngest/route.ts (1)

- src/app/api/inngest/route.ts

## rum/route.ts (1)

- src/app/api/rum/route.ts

## saml/acs (1)

- src/app/api/saml/acs/route.ts

## saml/login (1)

- src/app/api/saml/login/[orgSlug]/route.ts

## saml/metadata (1)

- src/app/api/saml/metadata/route.ts

## scim/v2 (5)

- src/app/api/scim/v2/ResourceTypes/route.ts
- src/app/api/scim/v2/Schemas/route.ts
- src/app/api/scim/v2/ServiceProviderConfig/route.ts
- src/app/api/scim/v2/Users/[id]/route.ts
- src/app/api/scim/v2/Users/route.ts

## v1/ai (14)

- src/app/api/v1/ai/analyze-assignment-safety/route.ts
- src/app/api/v1/ai/generate-assignment/route.ts
- src/app/api/v1/ai/generate-outline/route.ts
- src/app/api/v1/ai/generate-questions/route.ts
- src/app/api/v1/ai/generate-rubric/route.ts
- src/app/api/v1/ai/grade-assist/route.ts
- src/app/api/v1/ai/index-lesson/route.ts
- src/app/api/v1/ai/rag/index/route.ts
- src/app/api/v1/ai/scenario-chat/route.ts
- src/app/api/v1/ai/study-partner/route.ts
- src/app/api/v1/ai/study-plan/route.ts
- src/app/api/v1/ai/tutor/lessons/route.ts
- src/app/api/v1/ai/tutor/route.ts
- src/app/api/v1/ai/usage-policy/route.ts

## v1/attendance (4)

- src/app/api/v1/attendance/bulk/route.ts
- src/app/api/v1/attendance/checkin/route.ts
- src/app/api/v1/attendance/report/route.ts
- src/app/api/v1/attendance/route.ts

## v1/dashboard (3)

- src/app/api/v1/dashboard/instructor-summary/route.ts
- src/app/api/v1/dashboard/student-summary/route.ts
- src/app/api/v1/dashboard/summary/route.ts

## v1/drip (2)

- src/app/api/v1/drip/cron/route.ts
- src/app/api/v1/drip/trigger/route.ts

## v1/feedback (3)

- src/app/api/v1/feedback/[id]/follow-up/route.ts
- src/app/api/v1/feedback/[id]/mark-reviewed/route.ts
- src/app/api/v1/feedback/mine/route.ts

## v1/instructor (59)

- src/app/api/v1/instructor/assignments/[id]/apply-feedback-template/route.ts
- src/app/api/v1/instructor/assignments/[id]/bulk-grade/route.ts
- src/app/api/v1/instructor/assignments/[id]/export-grades/route.ts
- src/app/api/v1/instructor/assignments/[id]/grading-stats/route.ts
- src/app/api/v1/instructor/assignments/grading-queue/route.ts
- src/app/api/v1/instructor/at-risk-students/route.ts
- src/app/api/v1/instructor/audit-trail/route.ts
- src/app/api/v1/instructor/bulk-email/route.ts
- src/app/api/v1/instructor/bulk-flag/route.ts
- src/app/api/v1/instructor/bulk-ops/certificates/route.ts
- src/app/api/v1/instructor/bulk-ops/enroll/route.ts
- src/app/api/v1/instructor/bulk-ops/export/route.ts
- src/app/api/v1/instructor/checkout-offers/[id]/route.ts
- src/app/api/v1/instructor/checkout-offers/route.ts
- src/app/api/v1/instructor/coauthor-invitations/[id]/route.ts
- src/app/api/v1/instructor/coauthor-invitations/route.ts
- src/app/api/v1/instructor/content-gap-reports/[id]/route.ts
- src/app/api/v1/instructor/content-gap-reports/route.ts
- src/app/api/v1/instructor/coupons/[id]/route.ts
- src/app/api/v1/instructor/coupons/route.ts
- src/app/api/v1/instructor/course-ai-insights/route.ts
- src/app/api/v1/instructor/course-import-jobs/route.ts
- src/app/api/v1/instructor/course-quality/route.ts
- src/app/api/v1/instructor/courses/freshness/route.ts
- src/app/api/v1/instructor/courses/route.ts
- src/app/api/v1/instructor/course-templates/apply/route.ts
- src/app/api/v1/instructor/course-templates/route.ts
- src/app/api/v1/instructor/email-campaigns/[id]/enroll/route.ts
- src/app/api/v1/instructor/email-campaigns/[id]/route.ts
- src/app/api/v1/instructor/email-campaigns/[id]/stats/route.ts
- src/app/api/v1/instructor/email-campaigns/route.ts
- src/app/api/v1/instructor/feedback/route.ts
- src/app/api/v1/instructor/friction-map/route.ts
- src/app/api/v1/instructor/gradebook/route.ts
- src/app/api/v1/instructor/kyc-document/route.ts
- src/app/api/v1/instructor/kyc-upload/route.ts
- src/app/api/v1/instructor/learner-summary/route.ts
- src/app/api/v1/instructor/learning-funnel/route.ts
- src/app/api/v1/instructor/ledger/route.ts
- src/app/api/v1/instructor/lesson-feedback/route.ts
- src/app/api/v1/instructor/me/route.ts
- src/app/api/v1/instructor/payout-method/route.ts
- src/app/api/v1/instructor/payouts/route.ts
- src/app/api/v1/instructor/process-ai-suggestions/route.ts
- src/app/api/v1/instructor/recent-enrollments/route.ts
- src/app/api/v1/instructor/register/route.ts
- src/app/api/v1/instructor/revenue-insights/route.ts
- src/app/api/v1/instructor/revenue-summary/route.ts
- src/app/api/v1/instructor/reviews/route.ts
- src/app/api/v1/instructor/sales/route.ts
- src/app/api/v1/instructor/students/[id]/route.ts
- src/app/api/v1/instructor/students/broadcast/[id]/route.ts
- src/app/api/v1/instructor/students/broadcast/route.ts
- src/app/api/v1/instructor/students/route.ts
- src/app/api/v1/instructor/students-at-risk/route.ts
- src/app/api/v1/instructor/submissions/pending-counts/route.ts
- src/app/api/v1/instructor/submissions/route.ts
- src/app/api/v1/instructor/verification/route.ts
- src/app/api/v1/instructor/video-intelligence/route.ts

## v1/instructor-follows (2)

- src/app/api/v1/instructor-follows/[instructorId]/route.ts
- src/app/api/v1/instructor-follows/route.ts

## v1/learners (8)

- src/app/api/v1/learners/[user_id]/adaptive-path/route.ts
- src/app/api/v1/learners/[user_id]/completion-eta/route.ts
- src/app/api/v1/learners/[user_id]/intervention/route.ts
- src/app/api/v1/learners/[user_id]/next-action/route.ts
- src/app/api/v1/learners/[user_id]/readiness/route.ts
- src/app/api/v1/learners/[user_id]/review-queue/route.ts
- src/app/api/v1/learners/[user_id]/skill-gaps/route.ts
- src/app/api/v1/learners/[user_id]/xp-events/route.ts

## v1/lesson-qa (1)

- src/app/api/v1/lesson-qa/route.ts

## v1/live-sessions (7)

- src/app/api/v1/live-sessions/[id]/energy/event/route.ts
- src/app/api/v1/live-sessions/[id]/energy/route.ts
- src/app/api/v1/live-sessions/[id]/meeting/route.ts
- src/app/api/v1/live-sessions/[id]/mux/route.ts
- src/app/api/v1/live-sessions/[id]/room/route.ts
- src/app/api/v1/live-sessions/[id]/route.ts
- src/app/api/v1/live-sessions/route.ts

## v1/scenarios (4)

- src/app/api/v1/scenarios/[id]/session/route.ts
- src/app/api/v1/scenarios/[id]/sessions/[sessionId]/route.ts
- src/app/api/v1/scenarios/[id]/sessions/route.ts
- src/app/api/v1/scenarios/sessions/route.ts

## v1/study-groups (8)

- src/app/api/v1/study-groups/[id]/activity/route.ts
- src/app/api/v1/study-groups/[id]/invite/route.ts
- src/app/api/v1/study-groups/[id]/members/route.ts
- src/app/api/v1/study-groups/[id]/moderation/route.ts
- src/app/api/v1/study-groups/[id]/reports/route.ts
- src/app/api/v1/study-groups/[id]/route.ts
- src/app/api/v1/study-groups/join/route.ts
- src/app/api/v1/study-groups/route.ts
