# Delivery receipt template

Answer the issued task's acceptance conditions. Keep a small delivery short.
Replace all `REPLACE_` fields and remove unused sections. This is an author's
record of evidence; a separate [review report](../04_pure_reviewer/TASK_DELIVERY_REVIEW_TEMPLATE.md)
assesses it.

## Delivery identity

- Task and amendments: REPLACE_TASK_AND_AMENDMENT_REFERENCES
- Authoring session (`source_session`): REPLACE_ACTUAL_AUTHOR
- Date: REPLACE_DATE
- Baseline: REPLACE_INPUT_VERSION
- Delivered version: REPLACE_COMMIT_OR_ARTIFACT_IDENTITIES
- Artifacts: REPLACE_USABLE_PATHS
- Outcome: REPLACE_WHAT_NOW_WORKS_OR_WHAT_WAS_LEARNED

## What changed and why

REPLACE_CONCRETE_BEFORE_AFTER_AND_SCOPE

Identify supporting harness/document changes separately when they explain a
failure. Do not claim that production behavior changed if only a test changed.

## Acceptance evidence

Use `met`, `not_met`, `not_verified`, or `not_applicable` with a reason.
These are the delivery author's assessments, not an independent verdict.

| Task criterion | Status | Actual check and result | Evidence location and tested version | Limit |
| --- | --- | --- | --- | --- |
| REPLACE_CRITERION_ID | REPLACE_STATUS | REPLACE_ACTUAL_CHECK_AND_RESULT | REPLACE_RESULT_PATH_AND_VERSION | REPLACE_LIMIT_OR_NONE_IDENTIFIED |

Distinguish checks performed by this author from another author's saved results.
A planned command is not an executed check. If nothing was run, say so.
Explain whether the checked version matches the delivered version.

## Failures, corrections, and resource use

REPLACE_MEANINGFUL_FAILURES_CORRECTIONS_AND_RETAINED_EVIDENCE

Record consumed attempts where the task counts them, including failed launches.
Report measured usage separately from unknown overhead. Do not silently reset an
attempt count or rerun a judging command only to recover clipped output; recover
its saved result instead.

## Limits and unresolved decisions

REPLACE_UNCHECKED_BEHAVIOR_REMAINING_DEFECTS_AND_NEEDED_DECISIONS

State what the evidence does not establish. Synthetic answers can demonstrate
tool behavior without proving real human judgments correct.

## Disposition

- Review state and reference: REPLACE_ACTUAL_REVIEW_STATE_OR_NOT_REVIEWED
- Owner acceptance and reference: REPLACE_ACTUAL_DECISION_OR_NOT_RECORDED
- Next owner/action: REPLACE_OWNER_AND_CONCRETE_NEXT_ACTION

For a task with multiple destinations, add only the destinations actually used:

| Destination or artifact | Actual state | Evidence/read-back | Next owner/action |
| --- | --- | --- | --- |
| REPLACE_DESTINATION | REPLACE_STATE | REPLACE_REFERENCE_OR_NOT_CHECKED | REPLACE_OWNER_AND_ACTION |

Local completion, technical review, human acceptance, indexing, and publication
are separate facts. Use a current decision reference without rewriting earlier
receipts to look as though they knew the later outcome.

