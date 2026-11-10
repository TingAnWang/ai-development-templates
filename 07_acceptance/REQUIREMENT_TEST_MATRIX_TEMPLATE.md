# Requirement-to-test matrix template

Use this when a behavioral contract has several rules or layers of evidence.
For a small change, a few acceptance rows in the
[task](../05_task_delivery/TASK_ASSIGNMENT_TEMPLATE.md) are sufficient.

Replace all `REPLACE_` fields. Begin with expectations and `unverified` status.
Filling a row is not evidence that its check ran.

- Task/contract revision: REPLACE_TASK_AND_CONTRACT
- Authoring session (`source_session`): REPLACE_ACTUAL_AUTHOR
- Date: REPLACE_DATE
- Implementation version: REPLACE_COMMIT_OR_NOT_IMPLEMENTED
- Required rule set: REPLACE_COMPLETE_REQUIRED_RULE_LIST
- Verification scope and allowed execution: REPLACE_SCOPE_AND_PERMISSIONS
- Prior involvement/helper lineage: REPLACE_DISCLOSURE

## Coverage and results

| Rule | Implementation responsibility/location | Scenario and expected result | Evidence layer | Coverage | Actual result and saved evidence |
| --- | --- | --- | --- | --- | --- |
| REPLACE_RULE_ID | REPLACE_MODULE_OR_PLANNED_RESPONSIBILITY | REPLACE_SUCCESS_OR_FAILURE_AND_REASON | REPLACE_LAYER | unverified | Not run |

Duplicate rows for different scenarios. Include legitimate recovery as well as
refusal. For history-dependent behavior, test the state at the relevant event,
not only the final snapshot. Include every required rule, even if its evidence
is still missing.

Coverage describes the method, separately from the result:

- **executed:** identify the tested version, command/procedure, actual outcome,
  and saved evidence; an executed test can fail.
- **statically argued:** identify the inspected artifact and reasoning; this
  does not establish runtime behavior.
- **unverified:** identify the missing check, evidence, or access.
- **not applicable:** cite the task's exclusion and reason.

These labels do not replace the [reviewer's requirement statuses and verdict](../04_pure_reviewer/SESSION_SPEC_TASK_DELIVERY_REVIEWER_TEMPLATE.md#5-required-output-reviewmd).
A static argument satisfies a requirement only if it supplies the evidence that
requirement actually needs.

## Distinguish evidence layers

| Layer | What it can establish | Additional evidence it does not replace |
| --- | --- | --- |
| Semantic fixtures | Rules on deliberately constructed states/histories | Real source identity and importer behavior |
| Import/export integration | Matching source/record round trip and bad-input refusal without losing current work | Browser control behavior |
| Browser workflow | User actions, save, fresh resume, continued edit, re-export | Domain truth of human answers |
| Human/domain review | Suitability or correctness within the reviewed scope | General performance outside that scope |

Adapt the layers to your product. Never disable an identity guard to make a
synthetic fixture pass. Use a matching synthetic source/record pair when testing
an importer.

## Gaps and disposition

REPLACE_UNCOVERED_RULES_FAILURES_INTERPRETATIONS_AND_NEXT_OWNER

Report corrected fixtures or expectations and keep earlier runs identifiable.
A passing total does not imply full-contract coverage.

