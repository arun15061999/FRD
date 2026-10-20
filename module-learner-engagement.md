# Module Analysis: learner-engagement

Review state: Partial source trace completed for weekly learner stats and streak freeze; remaining gamification/recommendation rules pending.

## Findings

Engagement surfaces are inventoried. Points and streak formulas, eligibility, seasonal transitions, recommendation inputs, idempotency and anti-abuse controls are pending.

## API route files

- src/app/api/v1/activity/track/route.ts
- src/app/api/v1/gamification/badges/route.ts
- src/app/api/v1/gamification/battle-pass/route.ts
- src/app/api/v1/gamification/birthday-status/route.ts
- src/app/api/v1/gamification/challenges/route.ts
- src/app/api/v1/gamification/cosmetics/route.ts
- src/app/api/v1/gamification/leaderboard/route.ts
- src/app/api/v1/gamification/leaderboard/history/route.ts
- src/app/api/v1/gamification/me/route.ts
- src/app/api/v1/gamification/my-stats/route.ts
- src/app/api/v1/gamification/notifications/route.ts
- src/app/api/v1/gamification/shop/route.ts
- src/app/api/v1/gamification/social/challenges/route.ts
- src/app/api/v1/gamification/streak-badges/route.ts
- src/app/api/v1/gamification/streaks/route.ts
- src/app/api/v1/leaderboard/route.ts
- src/app/api/v1/leaderboard/extended/route.ts
- src/app/api/v1/leaderboard-seasons/route.ts
- src/app/api/v1/leaderboard-seasons/active/route.ts
- src/app/api/v1/leaderboard-seasons/[id]/route.ts
- src/app/api/v1/leaderboard-seasons/[id]/leaderboard/route.ts
- src/app/api/v1/momentum/route.ts
- src/app/api/v1/mystery-box/route.ts
- src/app/api/v1/personalization/adaptation/route.ts
- src/app/api/v1/personalization/profile/route.ts
- src/app/api/v1/personalization/segment/route.ts
- src/app/api/v1/personalization/skill-gaps/route.ts
- src/app/api/v1/personalization/status/route.ts
- src/app/api/v1/prestige/route.ts
- src/app/api/v1/prestige/reset/route.ts
- src/app/api/v1/recommendations/courses/route.ts
- src/app/api/v1/recommendations/feedback/route.ts
- src/app/api/v1/recommendations/rating/route.ts
- src/app/api/v1/recommendations/track-click/route.ts
- src/app/api/v1/spin-wheel/route.ts

## Frontend pages

- src/app/dashboard/page.tsx
- src/app/dashboard/achievements/page.tsx
- src/app/dashboard/adaptive-path/page.tsx
- src/app/dashboard/admin/enrollments/page.tsx
- src/app/dashboard/admin/video-usage/page.tsx
- src/app/dashboard/ai-tutor/page.tsx
- src/app/dashboard/analytics/page.tsx
- src/app/dashboard/assignments/page.tsx
- src/app/dashboard/assignments/anonymous-grading/page.tsx
- src/app/dashboard/assignments/[id]/page.tsx
- src/app/dashboard/assignments/[id]/code/page.tsx
- src/app/dashboard/assignments/[id]/submissions/[submissionId]/feedback/page.tsx
- src/app/dashboard/assignments/[id]/view/page.tsx
- src/app/dashboard/attendance/page.tsx
- src/app/dashboard/badges/page.tsx
- src/app/dashboard/blog/page.tsx
- src/app/dashboard/blog/add/page.tsx
- src/app/dashboard/blog/[id]/edit/page.tsx
- src/app/dashboard/calendar/page.tsx
- src/app/dashboard/calendar-settings/page.tsx
- src/app/dashboard/catch-up/page.tsx
- src/app/dashboard/certificate-preview/page.tsx
- src/app/dashboard/certificates/page.tsx
- src/app/dashboard/certificates/issue/page.tsx
- src/app/dashboard/certificates/[id]/appendix/page.tsx
- src/app/dashboard/chat/page.tsx
- src/app/dashboard/checkout/cancel/page.tsx
- src/app/dashboard/checkout/success/page.tsx
- src/app/dashboard/checkout/upsell/[courseId]/page.tsx
- src/app/dashboard/checkout/[courseId]/page.tsx
- src/app/dashboard/clr/page.tsx
- src/app/dashboard/community/page.tsx
- src/app/dashboard/community/challenges/page.tsx
- src/app/dashboard/competencies/page.tsx
- src/app/dashboard/competencies/tree/page.tsx
- src/app/dashboard/coupons/page.tsx
- src/app/dashboard/courses/page.tsx
- src/app/dashboard/courses/add/page.tsx
- src/app/dashboard/courses/browse/page.tsx
- src/app/dashboard/courses/saved/page.tsx
- src/app/dashboard/courses/[id]/page.tsx
- src/app/dashboard/courses/[id]/edit/page.tsx
- src/app/dashboard/courses/[id]/forum/page.tsx
- src/app/dashboard/courses/[id]/forum/[threadId]/page.tsx
- src/app/dashboard/courses/[id]/grades/page.tsx
- src/app/dashboard/courses/[id]/learn/page.tsx
- src/app/dashboard/courses/[id]/lessons/page.tsx
- src/app/dashboard/courses/[id]/lessons/[lessonId]/page.tsx
- src/app/dashboard/courses/[id]/lessons/[lessonId]/forum/page.tsx
- src/app/dashboard/courses/[id]/prove-it/page.tsx
- src/app/dashboard/credentials/page.tsx
- src/app/dashboard/ctf/page.tsx
- src/app/dashboard/ctf/challenges/[id]/page.tsx
- src/app/dashboard/ctf/challenges/[id]/edit/page.tsx
- src/app/dashboard/ctf/create/page.tsx
- src/app/dashboard/ctf/disclaimer/page.tsx
- src/app/dashboard/ctf/[id]/page.tsx
- src/app/dashboard/ctf-teams/page.tsx
- src/app/dashboard/employer-pathways/page.tsx
- src/app/dashboard/enrollments/page.tsx
- src/app/dashboard/enrollments/add/page.tsx
- src/app/dashboard/enrollments/success/page.tsx
- src/app/dashboard/events/page.tsx
- src/app/dashboard/events/create/page.tsx
- src/app/dashboard/events/registrations/page.tsx
- src/app/dashboard/events/[id]/page.tsx
- src/app/dashboard/events/[id]/edit/page.tsx
- src/app/dashboard/events/[id]/live/page.tsx
- src/app/dashboard/exams/page.tsx
- src/app/dashboard/exams/attempts/page.tsx
- src/app/dashboard/exams/create/page.tsx
- src/app/dashboard/exams/grading/page.tsx
- src/app/dashboard/exams/[id]/page.tsx
- src/app/dashboard/exams/[id]/edit/page.tsx
- src/app/dashboard/exams/[id]/grade/[attemptId]/page.tsx
- src/app/dashboard/exams/[id]/questions/page.tsx
- src/app/dashboard/exams/[id]/results/[attemptId]/page.tsx
- src/app/dashboard/exams/[id]/take/page.tsx
- src/app/dashboard/feedback/page.tsx
- src/app/dashboard/flashcards/page.tsx
- src/app/dashboard/following/page.tsx
- src/app/dashboard/forums/page.tsx
- src/app/dashboard/gamification/page.tsx
- src/app/dashboard/grades/page.tsx
- src/app/dashboard/grades/appeals/page.tsx
- src/app/dashboard/grades/messages/page.tsx
- src/app/dashboard/grades/what-if/page.tsx
- src/app/dashboard/guilds/page.tsx
- src/app/dashboard/invitations/[token]/page.tsx
- src/app/dashboard/jobs/page.tsx
- src/app/dashboard/leaderboard/page.tsx
- src/app/dashboard/learning-debt/page.tsx
- src/app/dashboard/learning-path/page.tsx
- src/app/dashboard/live-sessions/page.tsx
- src/app/dashboard/live-sessions/[id]/join/page.tsx
- src/app/dashboard/membership/page.tsx
- src/app/dashboard/membership/billing/page.tsx
- src/app/dashboard/mentorship/page.tsx
- src/app/dashboard/mentorship/find/page.tsx
- src/app/dashboard/mentorship/requests/page.tsx
- src/app/dashboard/mentorship/stats/page.tsx
- src/app/dashboard/mentorship/[requestId]/page.tsx
- src/app/dashboard/momentum/page.tsx
- src/app/dashboard/my-products/page.tsx
- src/app/dashboard/notes/page.tsx
- src/app/dashboard/notifications/page.tsx
- src/app/dashboard/onboarding/page.tsx
- src/app/dashboard/orders/page.tsx
- src/app/dashboard/organizations/page.tsx
- src/app/dashboard/organizations/[id]/page.tsx
- src/app/dashboard/peer-reviews/page.tsx
- src/app/dashboard/peer-reviews/[id]/page.tsx
- src/app/dashboard/personalization/page.tsx
- src/app/dashboard/portfolio/page.tsx
- src/app/dashboard/preferences/email/page.tsx
- src/app/dashboard/preferences/recommendations/page.tsx
- src/app/dashboard/products/page.tsx
- src/app/dashboard/products/create/page.tsx
- src/app/dashboard/products/[id]/edit/page.tsx
- src/app/dashboard/products/[id]/reviews/page.tsx
- src/app/dashboard/profile/page.tsx
- src/app/dashboard/progress/page.tsx
- src/app/dashboard/progress/skill-tree/page.tsx
- src/app/dashboard/recommendations/page.tsx
- src/app/dashboard/redeem-seat/page.tsx
- src/app/dashboard/referrals/page.tsx
- src/app/dashboard/resources/page.tsx
- src/app/dashboard/resources/add/page.tsx
- src/app/dashboard/resources/[id]/edit/page.tsx
- src/app/dashboard/scenarios/page.tsx
- src/app/dashboard/scenarios/[id]/page.tsx
- src/app/dashboard/security/devices/page.tsx
- src/app/dashboard/settings/page.tsx
- src/app/dashboard/skill-gaps/page.tsx
- src/app/dashboard/skills/page.tsx
- src/app/dashboard/students/page.tsx
- src/app/dashboard/students/add/page.tsx
- src/app/dashboard/students/[id]/page.tsx
- src/app/dashboard/students/[id]/edit/page.tsx
- src/app/dashboard/study-groups/page.tsx
- src/app/dashboard/study-groups/[id]/page.tsx
- src/app/dashboard/study-plan/page.tsx
- src/app/dashboard/support/page.tsx
- src/app/dashboard/support/create/page.tsx
- src/app/dashboard/support/refund/page.tsx
- src/app/dashboard/support/[id]/page.tsx
- src/app/dashboard/surveys/page.tsx
- src/app/dashboard/sync-conflicts/page.tsx
- src/app/dashboard/teachers/[[...slug]]/page.tsx
- src/app/dashboard/team-exams/page.tsx
- src/app/dashboard/transactions/page.tsx
- src/app/dashboard/transactions/add/page.tsx
- src/app/dashboard/transactions/[id]/page.tsx
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

## Field rules, workflows, and dependencies

Not extracted yet. Follow the UI action through route, service/domain, DB operation, and external side effect. Separate frontend validation, server schemas, and SQL/RLS constraints.

## Validation matrix

Pending source review; no field requiredness is inferred from filenames or UI labels.

## Open questions

Runtime flags, external provider behavior, and complete screen/database semantics are unverified. No tests are claimed as executed.

## Partial cross-layer findings

`GET /api/v1/gamification/my-stats` is student/admin, resolves student row (404 if absent), aggregates XP events from the last 7 days, successful CTF submissions and submitted exams in the same period, unrevoked certificates tied to enrollments, video watch seconds (all rows) into rounded one-decimal total hours, and lifetime successful CTF submissions. Response fields: `weeklyXp`, `labsThisWeek` (count of successful CTF submissions), `assessmentsThisWeek`, `certificatesEarned`, `totalHoursLearned`, `totalLabsSolved`. The property name `labsThisWeek` is what code returns even though it counts CTF submissions. Evidence: `src/app/api/v1/gamification/my-stats/route.ts:7-77`.

`GET /api/v1/gamification/streaks` supports admin `student_id` UUID lookup, otherwise current user; absent student returns zeroed streak/defaults. It reads streak, insurance quantity >0, and multiplier tiers ascending. `POST` is student-only with strict `{action:'freeze'}`; service consumes freeze for own streak and returns 409 when not applicable. Evidence: `src/app/api/v1/gamification/streaks/route.ts` and `src/domains/platform/streak.service.ts`.
