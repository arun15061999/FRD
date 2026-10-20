# Module Analysis: other-api-domains

Review state: Inventory completed; behavioral analysis pending.

## Findings

Remaining cross-cutting and lesser-classified route families are listed so none are omitted silently. Independent functional analysis and API/data mapping are pending.

## API route files

- src/app/api/v1/abandonment-tracking/events/route.ts
- src/app/api/v1/accessibility/route.ts
- src/app/api/v1/activity/track/route.ts
- src/app/api/v1/avatar/route.ts
- src/app/api/v1/badges/route.ts
- src/app/api/v1/badges/[id]/route.ts
- src/app/api/v1/bootstrap/route.ts
- src/app/api/v1/bulk/import/route.ts
- src/app/api/v1/csp-report/route.ts
- src/app/api/v1/csrf/route.ts
- src/app/api/v1/developer/api-keys/route.ts
- src/app/api/v1/developer/api-keys/[id]/route.ts
- src/app/api/v1/email-test/route.ts
- src/app/api/v1/incomplete-courses/route.ts
- src/app/api/v1/learning-debt/route.ts
- src/app/api/v1/me/public-profile/route.ts
- src/app/api/v1/notes/route.ts
- src/app/api/v1/policy-acceptances/route.ts
- src/app/api/v1/public/mentors/route.ts
- src/app/api/v1/seasonal/events/route.ts
- src/app/api/v1/seasonal/events/[eventId]/claim/route.ts
- src/app/api/v1/seasonal/events/[eventId]/join/route.ts
- src/app/api/v1/seasonal/events/[eventId]/progress/route.ts
- src/app/api/v1/sections/[id]/route.ts
- src/app/api/v1/student-competencies/route.ts
- src/app/api/v1/student-competencies/leaderboard/route.ts
- src/app/api/v1/student-competencies/report/route.ts
- src/app/api/v1/transactions/route.ts
- src/app/api/v1/transactions/[id]/route.ts
- src/app/api/v1/user/route.ts

## Frontend pages


## Field rules, workflows, and dependencies

Not extracted yet. Follow the UI action through route, service/domain, DB operation, and external side effect. Separate frontend validation, server schemas, and SQL/RLS constraints.

## Validation matrix

Pending source review; no field requiredness is inferred from filenames or UI labels.

## Open questions

Runtime flags, external provider behavior, and complete screen/database semantics are unverified. No tests are claimed as executed.
