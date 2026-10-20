# Module Analysis: media-content-files

Review state: Partial source trace completed for secure upload and resource listing; full download/delete and malware review lifecycle pending.

## Findings

Resource/upload/avatar/video routes are inventoried. MIME/size limits, storage lifecycle, access controls, deletion behavior, signed URLs, and provider failure paths are pending.

## API route files

- src/app/api/v1/avatar/route.ts
- src/app/api/v1/broadcast-attachments/route.ts
- src/app/api/v1/resources/route.ts
- src/app/api/v1/resources/[id]/route.ts
- src/app/api/v1/resources/[id]/download/route.ts
- src/app/api/v1/resources/[id]/purchase/route.ts
- src/app/api/v1/upload/route.ts
- src/app/api/v1/video/create/route.ts
- src/app/api/v1/video/embed/[videoId]/route.ts
- src/app/api/v1/video/session/heartbeat/route.ts
- src/app/api/v1/video/status/[videoId]/route.ts
- src/app/api/v1/video/streaming/route.ts
- src/app/api/v1/video/upload-url/route.ts

## Frontend pages

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
- src/app/live/[id]/page.tsx
- src/app/resources/page.tsx

## Field rules, workflows, and dependencies

Not extracted yet. Follow the UI action through route, service/domain, DB operation, and external side effect. Separate frontend validation, server schemas, and SQL/RLS constraints.

## Validation matrix

Pending source review; no field requiredness is inferred from filenames or UI labels.

## Open questions

Runtime flags, external provider behavior, and complete screen/database semantics are unverified. No tests are claimed as executed.

## Partial cross-layer findings

`POST /api/v1/upload` accepts multipart fields `file`, `bucket` (defaults `event-banners`), and optional `courseId`; bucket must be in an allowlist and `validateUploadOwnership` must allow caller. Lesson content allows PDF/MP4/WebM/MOV up to 500 MB with extension/MIME match; broadcast attachments allow PDF only up to 10 MB; other buckets accept image extensions JPEG/PNG/GIF/WebP and binary signature is checked. Data residency is enforced and written to compliance audit. File scanner is invoked; safe/unsafe handling and async scan dispatch are in route; unsafe file is rejected (422). Storage and scan-dispatch details need full pass. Evidence: `src/app/api/v1/upload/route.ts:16-50,147+`, `src/lib/storage/secure-upload.ts`, `src/lib/security/file-scanner.ts`.

`GET /api/v1/resources` scopes public rows for anonymous callers; admin can list all filtered rows; teacher gets public plus own; student gets public/free plus access associated with enrolled courses. Listing is paginated and includes schema-compatibility fallback. Evidence: `src/app/api/v1/resources/route.ts`.
