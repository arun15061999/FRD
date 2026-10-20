# FRD Coverage Checklist

Status key: **Inventoried** = path-level discovery done; **Partial** = source trace exists but module not exhaustive; **Pending** = no substantive behavior review yet. Update only with source evidence.

## Page route groups

| Route group | Page count | Status | Module note |
|---|---:|---|---|
| (public) | 40 | Partial | module notes: source path matches in 00 inventory and module files |
| admin | 115 | Inventoried | module notes: source path matches in 00 inventory and module files |
| api | 0 | Inventoried | module notes: source path matches in 00 inventory and module files |
| auth | 8 | Partial | module notes: source path matches in 00 inventory and module files |
| checkout | 5 | Partial | module notes: source path matches in 00 inventory and module files |
| college-admin | 6 | Inventoried | module notes: source path matches in 00 inventory and module files |
| courses | 3 | Partial | module notes: source path matches in 00 inventory and module files |
| ctf-portal | 1 | Inventoried | module notes: source path matches in 00 inventory and module files |
| dashboard | 153 | Partial | module notes: source path matches in 00 inventory and module files |
| fonts | 0 | Inventoried | module notes: source path matches in 00 inventory and module files |
| instructor | 150 | Partial | module notes: source path matches in 00 inventory and module files |
| learner | 8 | Partial | module notes: source path matches in 00 inventory and module files |
| live | 1 | Inventoried | module notes: source path matches in 00 inventory and module files |
| maintenance | 1 | Inventoried | module notes: source path matches in 00 inventory and module files |
| offline | 1 | Inventoried | module notes: source path matches in 00 inventory and module files |
| ref | 0 | Inventoried | module notes: source path matches in 00 inventory and module files |
| resources | 1 | Inventoried | module notes: source path matches in 00 inventory and module files |
| student-ctf | 3 | Inventoried | module notes: source path matches in 00 inventory and module files |
| styles | 0 | Inventoried | module notes: source path matches in 00 inventory and module files |
| verify | 1 | Inventoried | module notes: source path matches in 00 inventory and module files |
| verify-certificate | 2 | Inventoried | module notes: source path matches in 00 inventory and module files |

## API first-level domains

| Domain | Route files | Status | Review artifact |
|---|---:|---|---|
| certificates | 1 | Inventoried; behavioral review pending | 00 inventory + module notes / gap catalog |
| cron | 4 | Inventoried; behavioral review pending | 00 inventory + module notes / gap catalog |
| docs | 2 | Inventoried; behavioral review pending | 00 inventory + module notes / gap catalog |
| inngest | 1 | Inventoried; behavioral review pending | 00 inventory + module notes / gap catalog |
| rum | 1 | Inventoried; behavioral review pending | 00 inventory + module notes / gap catalog |
| saml | 3 | Inventoried; behavioral review pending | 00 inventory + module notes / gap catalog |
| scim | 5 | Inventoried; behavioral review pending | 00 inventory + module notes / gap catalog |
| v1 | 945 | Inventoried; behavioral review pending | 00 inventory + module notes / gap catalog |

## Supporting source inventories

| Area | Inventory | Status |
|---|---|---|
| UI components/hooks/contexts | docs/frd-analysis/00-repository-inventory.md | Inventoried; module linkage incomplete |
| Domain and service files | docs/frd-analysis/00-repository-inventory.md | Inventoried; detailed call graph pending |
| Validation schemas | docs/frd-analysis/00-repository-inventory.md | Inventoried; field extraction partial |
| Generated types and SQL migrations | src/types and supabase/migrations | Migration path inventory; complete schema/constraint extraction pending |
| External integrations | .env.example and src/lib/integrations, src/domains/integrations, provider services | Configuration names inventoried; runtime unverified |
| Tests and fixtures | tests and src/__tests__ | Path inventory done; tests not run; requirements mapping partial |

## Deep analysis passes

| Module note | Current state | Next required work |
|---|---|---|
| module-assessment-grading | Partial: assignment listing and submission grading traced; exam lifecycle pending | reconcile every screen, endpoint, schema, table, RLS rule, and test |
| module-commerce-payments | Partial: quote and Razorpay/Stripe fulfillment branches traced | checkout UI, order creation, refunds, provider retries, accounting, and data dictionary |
| module-community-events-support | Partial: forum thread create/list and support ticket create traced | replies, moderation, events and complete ticket lifecycle |
| module-credentials-achievements | Partial: micro-credential issuance traced; other credential workflows pending | certificate issuance/revocation and public verification behavior |
| module-identity-access | Partial: signup/signin traced; recovery/session/2FA/SSO pending | enumerate all auth forms, policy branches, session/cookie behavior, and tests |
| module-integrations-mobile | Partial: integration health, LTI, Mux webhook traced | calendar/mobile/push/LMS/SCORM/xAPI flows and provider failure behavior |
| module-labs-ctf | Partial: lab authoring and CTF flag submission traced | container execution/session lifecycle, scoring and all CTF flows |
| module-learner-engagement | Partial: weekly stats and streak freeze traced | remaining gamification, rewards, leaderboard and recommendation logic |
| module-learning-content | Partial: course catalog/create and draft-to-lessons path traced | full lesson/progress/enrollment/path and approval workflows |
| module-media-content-files | Partial: upload security and resource listing traced | complete upload scanner/storage lifecycle and downloads/deletion |
| module-notifications-content-marketing | Partial: in-app list/create/read-all traced | email/newsletter triggers, templates, recipient rules, retries, and opt-outs |
| module-organization-tenant | Partial: org create/member invite/tenant context traced | all departments, domains, billing, roster, roles, and full RLS mapping |
| module-other-api-domains | Inventory only; behavior pending | classify and trace each cross-cutting API domain |
| module-platform-admin-operations | Partial: user list/summary and saved reports traced; shared API wrapper reviewed | admin page permissions/actions, jobs, exports, audit and operational rules |

## Completion gate

- Every page and API route path must appear in `00-repository-inventory.md` or a module artifact.
- Domain analysis is not complete until representative and exceptional paths trace UI → API → service/domain → persistence → side effect, with validators and tests cross-linked.
- Current state is not full repository analysis. 00 inventory is path coverage; 01 gap catalog records missing module manifests; module status labels distinguish partial from pending.

## API v1 module domain checklist

The top-level src/app/api directory count includes the 1 namespace. This table expands that namespace so every discovered business API domain has an explicit status.

| v1 domain | Route files | Status | Analysis artifact |
|---|---:|---|---|
| abandonment-tracking | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| accessibility | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| achievements | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| activity | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| admin | 147 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| affiliates | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| ai | 14 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| analytics | 15 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| appeals | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| assessments | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| assignments | 24 | Partial cross-layer trace | FRD §29 and docs/frd-analysis/03-cross-layer-findings.md |
| attendance | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| auth | 17 | Partial cross-layer trace | FRD §29 and docs/frd-analysis/03-cross-layer-findings.md |
| avatar | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| badges | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| blog | 5 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| bootstrap | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| broadcast-attachments | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| bulk | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| bundles | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| calendar | 9 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| career-quiz | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| cart-recovery | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| catch-up-cards | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| categories | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| certificates | 6 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| certificate-templates | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| chat | 10 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| checkout | 5 | Partial cross-layer trace | FRD §29 and docs/frd-analysis/03-cross-layer-findings.md |
| churn | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| cohorts | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| commerce | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| community | 6 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| competencies | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| compliance | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| concepts | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| coupons | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| courses | 53 | Partial cross-layer trace | FRD §29 and docs/frd-analysis/03-cross-layer-findings.md |
| credentials | 7 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| cron | 28 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| csp-report | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| csrf | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| ctf | 20 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| dashboard | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| developer | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| discord | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| drip | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| email | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| email-test | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| employer-pathways | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| employers | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| enrollments | 5 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| events | 17 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| exams | 25 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| feedback | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| flashcards | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| forum | 11 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| gamification | 14 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| gradebook | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| grades | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| groups | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| guilds | 7 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| incomplete-courses | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| instructor | 59 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| instructor-follows | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| integrations | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| jobs | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| kudos | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| labs | 8 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| leaderboard | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| leaderboard-seasons | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| learners | 8 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| learning | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| learning-analytics | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| learning-debt | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| learning-objectives | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| learning-paths | 9 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| lesson-qa | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| lessons | 15 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| license-keys | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| live-sessions | 7 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| lms | 5 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| lti | 6 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| me | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| memberships | 7 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| mentorship | 20 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| micro-credentials | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| mobile | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| momentum | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| monitoring | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| mystery-box | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| newsletter | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| notes | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| notifications | 5 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| notification-templates | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| offline | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| orders | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| organization-invitations | 1 | Partial cross-layer trace | FRD §29 and docs/frd-analysis/03-cross-layer-findings.md |
| organizations | 36 | Partial cross-layer trace | FRD §29 and docs/frd-analysis/03-cross-layer-findings.md |
| payouts | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| peer-reviews | 8 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| personalization | 5 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| policy-acceptances | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| portfolio | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| preferences | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| prestige | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| privacy | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| proctoring | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| products | 14 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| public | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| push | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| question-bank | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| razorpay | 4 | Partial cross-layer trace | FRD §29 and docs/frd-analysis/03-cross-layer-findings.md |
| recommendations | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| recurring-billing | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| referrals | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| refund-requests | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| refunds | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| reports | 7 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| resources | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| rubrics | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| scenarios | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| scorm | 7 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| search | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| seasonal | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| sections | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| security | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| settings | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| spin-wheel | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| student | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| student-competencies | 3 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| students | 7 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| study-groups | 8 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| submissions | 9 | Partial cross-layer trace | FRD §29 and docs/frd-analysis/03-cross-layer-findings.md |
| support | 5 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| surveys | 6 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| system | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| teachers | 4 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| team-exams | 10 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| transactions | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| upload | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| user | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| users | 2 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| video | 6 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| webhooks | 10 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| wishlist | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |
| xapi | 1 | Inventory only / pending | 00 inventory + 01 route gap catalog |

## Identifier and consolidation audit

See  4-id-integrity-audit.md for ranges, duplicate/reference handling, and tests-not-executed status. FRD consolidation is in docs/FRD.md; module evidence remains in the numbered and module-specific analysis files.

