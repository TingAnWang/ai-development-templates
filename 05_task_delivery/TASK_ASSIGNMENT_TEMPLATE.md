# Task assignment template

Use this for one outcome, alongside an adopted [session role](../00_shared/SESSION_SPEC_TEMPLATE.md)
if you use one. For a small change, the [README starter message](../README.md#your-first-task)
may be enough. Replace every `REPLACE_` field, remove irrelevant sections, and
preserve the issued version when amending it. This template is not an assignment.

## Identity and inputs

- Task ID and revision: REPLACE_TASK_ID_AND_REVISION
- Authoring session (`source_session`): REPLACE_ACTUAL_AUTHOR
- Date: REPLACE_DATE
- Recipient: REPLACE_IMPLEMENTER
- Assignment/authorization reference: REPLACE_REQUEST_OR_DECISION
- Project root and applicable instructions: REPLACE_ROOT_AND_INSTRUCTIONS
- Baseline: REPLACE_COMMIT_OR_IDENTIFIED_SNAPSHOT
- Inputs and their versions: REPLACE_INPUTS_AND_VERSIONS
- Writable paths: REPLACE_WRITABLE_PATHS
- Delivery and receipt destinations: REPLACE_OUTPUT_PATHS

Use a commit and short file list unless separate input identities or access
restrictions matter. A referenced file does not automatically authorize access
to everything it mentions.

## Outcome and boundaries

**Outcome:** REPLACE_USER_VISIBLE_BEHAVIOR_OR_FINITE_QUESTION

**Allowed supporting work:** REPLACE_RELATED_CODE_TEST_HARNESS_OR_DOC_CHANGES

**Outside scope:** REPLACE_EXCLUDED_DATA_BEHAVIOR_OR_ACTIONS

**Must preserve:** REPLACE_MEANINGS_HUMAN_EDITS_COMPATIBILITY_OR_SOURCE_IDENTITY

## Acceptance

Name observable behavior and evidence, not only an aggregate test count.
Add a refusal case and a legitimate success case where a guard is central.

| ID | Required behavior or output | Evidence needed on the delivered version |
| --- | --- | --- |
| A1 | REPLACE_REQUIRED_OUTCOME | REPLACE_CHECK_AND_SAVED_RESULT |
| A2 | REPLACE_INTEGRITY_OR_FAILURE_BEHAVIOR | REPLACE_NEGATIVE_AND_POSITIVE_CHECKS |

Use the [requirement/test matrix](../07_acceptance/REQUIREMENT_TEST_MATRIX_TEMPLATE.md)
only when more detail helps.

## Corrections, resources, and stopping

- Routine corrections already authorized: REPLACE_PERMITTED_REPAIR_SCOPE
- Correction policy: REPLACE_CONTINUE_WITHIN_SHARED_BUDGET_OR_EXPLICIT_LIMIT
- Planning estimate, if useful: REPLACE_ESTIMATE_OR_NOT_USED
- Hard limits and what consumes them: REPLACE_LIMITS_AND_ACCOUNTING
- Material decisions reserved for owner: REPLACE_SCOPE_OR_MEANING_CHANGES
- Stop condition: REPLACE_TERMINAL_GATE_OR_MATERIAL_BLOCKER

Do not turn an estimate into a hard stop unless the assignment says so.
Preserve meaningful failed checks. For a fixed experiment, optionally adopt
[separate preparation and execution controls](EXECUTION_CONTROLS_TEMPLATE.md);
ordinary repairs do not need a frozen-attempt protocol.

A blocker report identifies the affected requirement, reproducible consequence
or missing essential evidence, work already completed, and smallest needed
decision. Continue unaffected authorized work when useful. Cosmetic preferences
do not silently become acceptance requirements.

## Delivery and next owner

Return a [receipt](DELIVERY_RECEIPT_TEMPLATE.md) with exact artifacts/version,
acceptance results, earlier failures, unverified areas, and remaining decisions.

- Review owner and permitted verification: REPLACE_REVIEW_OWNER_AND_SCOPE
- Acceptance owner: REPLACE_ACCEPTANCE_OWNER
- Next action within this assignment, or stop: REPLACE_NEXT_ACTION_OR_STOP

A receipt does not assign work to another session. Include publication or
deployment only when the actual assignment covers it.

