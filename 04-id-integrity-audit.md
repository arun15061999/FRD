# FRD Identifier Integrity Audit

Audit date: 20 October 2026. This checks ID continuity and definition/reference use in docs/FRD.md. IDs recur in traceability tables by design; repeated references are not duplicate requirement definitions.

| Prefix | Unique IDs | Expected range | Definition/reference note |
|---|---:|---|---|
| FR | 31 | FR-001–FR-031 | Requirement definitions in §§9 and 29.2; repeated once in requirement-level RTM. |
| BR | 31 | BR-001–BR-031 | Business-rule definitions in §§12 and 29.4; referenced in traceability. |
| VAL | 42 | VAL-001–VAL-042 | Validation definitions in §§14 and 29.5; referenced in traceability. |
| AC | 31 | AC-001–AC-031 | Acceptance criteria definitions in §§22 and 29.5; linked to requirements in RTM. |
| TC | 39 | TC-001–TC-039 | Proposed test scenarios in §§23 and 29.5; none are claimed executed. |
| API | 2 | API-001–API-002 | Detailed catalog/create API contracts; remaining API files inventoried, not individually contracted. |
| SC | 8 | SC-001–SC-008 | Screen family identifiers; exhaustive screen specifications pending. |
| WF | 17 | WF-001–WF-017 | Workflow IDs across §§13 and 29.4. Most secondary workflows are partial. |

## Audit result

- FR, BR, VAL, AC, TC, API, SC, and WF identifiers use stable, unique numeric sequences within their defined ranges.
- FR identifiers recur in the RTM as references; this is intentional and the RTM does not define a second requirement.
- Test scenarios are explicitly marked proposed/not executed.
- Many page/API/module items still lack detailed specifications and acceptance tests; see 02-coverage-checklist.md and 01-api-route-coverage-gaps.md.
