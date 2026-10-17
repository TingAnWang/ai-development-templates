---
record_schema: "REPLACE_RECORD_SCHEMA"
record_id: "REPLACE_RECORD_ID"
record_type: patch_note_template
agent: "REPLACE_AUTHORING_AGENT"
source_session: "REPLACE_SOURCE_SESSION"
prepared_by: "REPLACE_PREPARED_BY"
task_id: "REPLACE_TASK_ID"
created_at: "REPLACE_CREATED_AT"
status: reusable_template
is_template: true
version: 1
project_id: "REPLACE_PROJECT_ID"
qualifies: "REPLACE_ORIGINAL_DELIVERY_RECORD_ID_OR_PATH"
supersedes: null
authorization_reference: "REPLACE_AUTHORIZED_PATCH_TASK_OR_DECISION"
review:
  owner: "REPLACE_REVIEW_OWNER"
  state: pending
  decision_reference: null
publication:
  sqlite: not_indexed
  notion: not_published
  routing_owner: "REPLACE_ROUTING_OWNER"
  publication_owner: "REPLACE_PUBLICATION_OWNER"
  next_gate: select_for_next_authorized_alignment_milestone
---

# PATCH.md — delivery update
## Using this template
Use a patch note to record a correction or bounded update to an existing delivery:
**what changed, why, what was checked, what remains unchanged, and what happens next**.
It may cover code, documentation, a review interface or delivery packaging. It is
not a machine-applicable code diff, an execution authorization or a claim of approval.

Copy this file to a new task-owned `PATCH.md`, or use a descriptive name such as
`REPLACE_DELIVERY_NAME_PATCH.md`. Keep separate patch records for separate deliveries rather
than overwriting a historical note.

Before issuing the copy:

- Assign its own `record_id`, `task_id`, creation date and actual author in `agent`,
  `source_session` and `prepared_by`. Record the session that actually wrote the
  patch note rather than its recipient.
- Set `record_type: patch_note`, `is_template: false` and the actual document status:
  `draft` while preparing or `delivered_awaiting_review` when delivered. Record
  review completion separately, with its real decision reference.
- Replace every `REPLACE_FIELD_NAME` value. Use `not_applicable` with a reason for an
  inapplicable section; use `not_checked` or `unknown` for missing evidence.
- `qualifies` identifies the original delivery being updated. Leave `supersedes`
  null for an additive note; set it only when a named earlier record is explicitly
  replaced. This never erases the earlier evidence.
- Adjust publication owners for the receiving project. Do not pre-mark indexing,
  publication or acceptance as complete. Remove this usage section from the copy.

Optional project pattern: if available, consult an earlier patch note from your project
(`REPLACE_EXISTING_PATCH_NOTE_PATH`) and its delivery receipt
(`REPLACE_EXISTING_PATCH_RECEIPT_PATH`).

No earlier patch note, shared ledger, database, or Notion page is required to use
this template. See the [dependency-adaptation guide](../README.md#adapt-paths-and-project-dependencies)
and remove unused publication metadata, rows, and requirements from your copy.

## 1. Delivery update summary
REPLACE_TWO_OR_THREE_SENTENCES_DESCRIBING_THE_ACTUAL_CHANGE_AND_ITS_OUTCOME.

| Item | Record |
| --- | --- |
| Original delivery | REPLACE_RECORD_ID_AND_LINK_TO_ORIGINAL_RECEIPT |
| Baseline identity | REPLACE_VERSION_COMMIT_OR_MANIFEST_HASH_AS_APPLICABLE |
| Patch assignment / authorization | REPLACE_TASK_OR_DECISION_LINK |
| Updated delivery | REPLACE_VERSION_AND_USABLE_ARTIFACT_ENTRY_POINT |
| Delivery state | REPLACE_COMPLETED_PARTIAL_OR_BLOCKED_WITH_REASON |
| Review state | REPLACE_PENDING_OR_ACTUAL_REVIEW_DISPOSITION_AND_REFERENCE |

The baseline must identify the bytes or version actually patched. A previous
release name alone is insufficient if local changes were already present.

## 2. Reason and scope
- **Problem / request:** REPLACE_OBSERVED_PROBLEM_OR_REQUESTED_IMPROVEMENT.
- **Evidence before the patch:** REPLACE_REPRODUCTION_OR_SOURCE_REFERENCE.
- **Authorized changes:** REPLACE_FILES_COMPONENTS_OR_DOCUMENT_SECTIONS_IN_SCOPE.
- **Outside scope:** REPLACE_IMPORTANT_ACTIONS_OR_ARTIFACTS_NOT_AUTHORIZED.

If reproduction was not possible, say so and explain the evidence used. Do not
describe an anticipated effect as a reproduced defect.

## 3. Changes delivered
| Change ID | Before | After | Affected files / interfaces | Verification |
| --- | --- | --- | --- | --- |
| P01 | REPLACE_PREVIOUS_BEHAVIOR_OR_WORDING | REPLACE_DELIVERED_BEHAVIOR_OR_WORDING | REPLACE_PATHS_OR_CONTRACTS | REPLACE_CHECK_REFERENCE |

- **Diff / change manifest:** REPLACE_LINK_OR_NOT_APPLICABLE_WITH_REASON.
- **Before / after identities:** REPLACE_RELEVANT_VERSIONS_HASHES_OR_MANIFEST_LINK.
- **Compatibility and migration:** REPLACE_CALLER_DATA_OR_WORKFLOW_IMPACT_OR_NONE_WITH_BASIS.

For an additive correction to an earlier receipt, identify the original claim and
the corrected claim precisely. Preserve the original receipt and explain the
scope in which the correction applies.

## 4. Verification actually performed
| Check | Method / command and scope | Actual result | Evidence |
| --- | --- | --- | --- |
| Original issue | REPLACE_REPRODUCTION_METHOD | REPLACE_PASS_FAIL_OR_NOT_CHECKED | REPLACE_LOG_OR_RECORD |
| Patched behavior | REPLACE_FOCUSED_CHECK | REPLACE_ACTUAL_RESULT | REPLACE_LOG_OR_RECORD |
| Regression / preservation | REPLACE_RELEVANT_CHECK | REPLACE_ACTUAL_RESULT | REPLACE_LOG_OR_RECORD |

- **Not tested:** REPLACE_UNCHECKED_ENVIRONMENTS_CASES_OR_USER_STEPS.
- **Failed checks and corrections:** REPLACE_INITIAL_FAILURES_CHANGES_AND_RERUNS_OR_NONE.
- **Operational use:** REPLACE_ACTUAL_MODEL_GPU_RENDER_INSTALL_OR_EXTERNAL_WRITE_ACTIVITY_OR_NONE.
- **Limits of the evidence:** REPLACE_WHAT_THE_CHECKS_DO_NOT_ESTABLISH.

Keep initial failures and final results distinct. Record a planned check as
`not_run`, not passed. For a visual change, distinguish browser/render inspection
from structural tests. Do not claim semantic accuracy from transport or mechanics
checks. Link detailed resource measurements only when relevant to the task.

## 5. Preservation and effect on earlier results
- **Protected artifacts:** REPLACE_WHAT_WAS_REQUIRED_TO_REMAIN_UNCHANGED.
- **Preservation check:** REPLACE_HASH_DIFF_OR_OTHER_EVIDENCE_AND_ITS_SCOPE.
- **Historical runs and human answers:** REPLACE_WHETHER_ANY_WERE_CHANGED_OR_RECOMPUTED.
- **Backup / recovery:** REPLACE_BEFORE_COPY_OR_VERSION_REFERENCE_AND_RECOVERY_REQUIREMENTS.

A code correction does not retroactively change a saved experiment's result.
Any rerun or migration needs its own authority and identity. Describe recovery
without executing it or discarding another person's changes. Do not claim
byte-identical preservation without a comparison.

## 6. Remaining issues and handoff
| Item | Consequence / blocking status | Owner | Next action / gate |
| --- | --- | --- | --- |
| REPLACE_ISSUE_OR_NONE | REPLACE_EFFECT_AND_WHETHER_IT_BLOCKS_USE | REPLACE_OWNER | REPLACE_REQUIRED_DECISION_OR_CHECK |

- **Reviewer:** REPLACE_NAMED_SESSION_OR_PERSON.
- **Requested disposition:** REPLACE_EXACT_SCOPE_FOR_ACCEPTANCE_OR_FURTHER_REVIEW.
- **Stop condition:** REPLACE_WHERE_THIS_ASSIGNMENT_STOPS.
- **Not authorized by this delivery:** REPLACE_FOLLOW_ON_RUNS_PUBLICATION_OR_OTHER_WORK.

Distinguish implementation delivery, technical review and human acceptance. A
minor caveat may remain open without blocking the next separately assigned step.

## 7. Navigation and publication impact
| Surface | Actual action / state | Evidence or pending owner and next gate |
| --- | --- | --- |
| Markdown / navigation | REPLACE_SCOPED_UPDATE_OR_UNCHANGED | REPLACE_LINKS_AND_BACKUPS_IF_EDITED |
| SQLite | REPLACE_NOT_INDEXED_PENDING_EXCLUDED_OR_VERIFIED | REPLACE_CHECKPOINT_AND_SOURCE_IDENTITY_OR_OWNER_GATE |
| Notion | REPLACE_NOT_PUBLISHED_PENDING_EXCLUDED_OR_VERIFIED | REPLACE_PAGE_AND_READ_BACK_OR_OWNER_GATE |
| Git | REPLACE_NOT_APPLICABLE_UNCOMMITTED_COMMITTED_OR_PUBLISHED | REPLACE_REPOSITORY_COMMIT_REMOTE_CHECK_OR_LIMITATION |

Update only authorized destinations. If your project uses a shared synchronization ledger,
identify it as `REPLACE_SYNCHRONIZATION_LEDGER_PATH` and use that existing queue.
If a queue edit is outside scope, state the pending item and
owner here. A source link is not indexing; a local commit is not a remote push.
Exclude private payloads from publication unless explicitly authorized.

## 8. Author closeout checklist
- [ ] Original delivery and patch authority are identified; all placeholders are resolved.
- [ ] YAML parses; author, date, status and record identity are accurate.
- [ ] Changes, evidence, unchecked areas and failed attempts are disclosed.
- [ ] Protected material and prior results are accounted for without overstating checks.
- [ ] Artifact links resolve; next reviewer, owner and stop condition are explicit.
- [ ] Publication and Git states reflect actual actions, not intentions.

These are author checks, not independent approval. A later reviewer records their
own disposition and scope in the appropriate review record.
