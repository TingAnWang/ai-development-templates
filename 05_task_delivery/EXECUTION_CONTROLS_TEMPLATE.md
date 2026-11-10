# Optional preparation and execution controls

Use this supplement when retries or changes after observation affect the meaning
or cost of an operation. For ordinary implementation, the task's shared repair
budget may be sufficient. The numbers in the [diagnostic example](../examples/implementer_completion/README.md#different-controls-for-a-fixed-diagnostic)
are historical choices, not defaults.

Replace every `REPLACE_` field. Attach this to an identified task; it does not
grant permission to run anything by itself.

- Task/revision: REPLACE_TASK_REFERENCE
- Authoring session (`source_session`): REPLACE_ACTUAL_AUTHOR
- Date: REPLACE_DATE
- Operation and reason to control retries: REPLACE_OPERATION_AND_REASON

## Define accounting before work starts

| Control | Assigned value |
| --- | --- |
| Preparation activity allowed | REPLACE_ALLOWED_PREPARATION |
| Maximum preflight passes | REPLACE_PASS_LIMIT |
| Corrections allowed between passes | REPLACE_CORRECTION_LIMIT_AND_SCOPE |
| Real/costly calls allowed during preparation | REPLACE_CALL_ALLOWANCE |
| Event that consumes a real attempt | REPLACE_PRECISE_START_EVENT |
| Maximum real attempts | REPLACE_ATTEMPT_LIMIT |
| Failure, interruption, or partial-result disposition | REPLACE_RETRY_OR_STOP_POLICY |
| Shared hard limits, including failed attempts | REPLACE_LIMITS_AND_ACCOUNTING |

A crash can consume an attempt even when it produces no useful result. Decide
this in the assignment, not after seeing the outcome. Name any authorized recovery
instead of treating “resume” as automatically different from retry.

## Preparation gate

- Required controls: REPLACE_CONTROLS_AND_EXPECTED_RESULTS
- Each important guard has a legitimate success case and a failure for the
  expected reason. An unrelated error rejecting both is insufficient evidence.
- Exercise the entry point and execution context that the real operation uses.
  A rehearsal that skips a critical import or guard does not validate it.
- Preserve each tested revision, commands, inputs, outcomes, and failures.
- Once the required controls pass, proceed only as authorized; do not consume
  extra passes merely to repeat success.

## Identify the passing revision

Record the executable/configuration/input versions and exact invocation:
REPLACE_IDENTITY_MANIFEST_OR_COMMIT_AND_FILE_LIST.

If this task freezes execution, only the unchanged passing revision may start.
A change after the gate needs the task's specified revalidation route:
REPLACE_REVALIDATION_OR_STOP_RULE.

## Execution and result

Save full results before displaying summaries. If display is clipped, read the
saved output rather than repeating the operation. Report actual attempts,
partial results, discrepancies, and unknown overhead.

After execution starts, permitted changes/recovery are:
REPLACE_EXACT_POLICY.

Deliver a [receipt](DELIVERY_RECEIPT_TEMPLATE.md). A useful negative result can
complete the assigned question; do not tune until favorable without a new
assignment that preserves the original result.

