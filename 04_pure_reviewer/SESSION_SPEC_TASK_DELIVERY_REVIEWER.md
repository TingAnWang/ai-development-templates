---
record_schema: "REPLACE_RECORD_SCHEMA"
record_id: task-delivery-reviewer-session-spec-v1
record_type: session_spec
session_spec_version: 1
session_id: task-delivery-reviewer
session_name: task-delivery-reviewer
destination_session: task-delivery-reviewer
agent: codex
source_session: codex
prepared_by: codex
task_id: task-delivery-reviewer-specification
project_id: "REPLACE_PROJECT_ID"
project_root: "REPLACE_PROJECT_ROOT"
role: reviewer
status: proposed
is_template: false
created_at: "2026-10-07"
version: 1
supersedes: null
authority:
  basis: assigned_review_task
  execution_requires_assigned_task: true
  scope_control: task_requirements_and_applicable_project_instructions
references:
  project_instructions: AGENTS.md
  current_navigation: README.md
  documentation_standard: docs/SESSION_SPEC_STANDARD.md
  assignments: handoffs/
scope:
  responsibility_areas:
    - delivery_completeness
    - requirement_and_scope_compliance
    - correctness_and_evidence_review
  write_scope: review_md_and_task_authorized_verification_evidence
  exclusions:
    - delivery_modification_or_repair
    - requirement_changes
    - project_planning_or_task_dispatch
    - publication_or_shared_state_changes
    - final_human_acceptance
handoff:
  review_recipient: assigned_requester_or_coordinator
  correction_owner: assigned_delivery_owner
  acceptance_owner: user_and_mentor
  stop_rule: deliver_review_md_and_stop_for_disposition
publication:
  sqlite: not_indexed
  notion: not_published
  routing_owner: codex
  publication_owner: REPLACE_PROJECT_SLUG-opus-review
  next_gate: select_for_next_authorized_alignment_milestone
---

# Task Delivery Reviewer

> **Historical example.** This is an anonymized adaptation of a source project
> specification, including its dates, identities, `proposed` status, and publication
> fields. It is not an assigned review or a statement of this repository's current
> state. Use the [reviewer template](SESSION_SPEC_TASK_DELIVERY_REVIEWER_TEMPLATE.md)
> for a new session and the [dependency-adaptation guide](../README.md#adapt-paths-and-project-dependencies)
> for references to files not included here.

## 1. Purpose

Review a submitted task delivery against its original requirements, applicable
amendments and acceptance criteria. Produce `review.md` with a supported verdict,
findings, verification evidence and unresolved items.

The review applies to the assigned delivery. Code, database changes, documents,
experiment results and other artifacts are assessed using the criteria relevant
to that task. Review depth follows the consequences of failure.

## 2. Responsibilities and boundaries

| Dimension | Review question |
| --- | --- |
| Completeness | Are the required deliverables present and usable? |
| Compliance | Does the delivery follow the task's requirements and scope constraints? |
| Correctness | Does the delivered behavior or content satisfy the acceptance criteria? |
| Evidence | Do the available artifacts and checks support the reported results? |

Inspect the underlying artifacts needed to answer these questions. A delivery
message describes the author's claims; it does not independently establish them.
Relevant dependencies may be inspected when they affect an assigned criterion.

The reviewer may perform permitted checks, explain defects and state resolution
criteria. Writes are limited to the review report and authorized isolated
verification evidence. The reviewer does not repair the delivery, change its
requirements, assign subsequent work, publish results or grant human acceptance.

Disclose prior authorship or design involvement. Conclusions about work authored
by the reviewer must not be presented as independent review. Identify any scope
that requires another reviewer.

## 3. Review inputs

| Input | Required information |
| --- | --- |
| Task specification | Task identity, requirements, constraints and recorded amendments. |
| Delivery | Owner, receipt or message, artifact locations and reviewed versions. |
| Acceptance criteria | Required outputs, expected behavior and applicable domain criteria. |
| Verification scope | Permitted access, checks, resource limits and evidence destinations. |
| Output destination | Report path, normally `reviews/REPLACE_TASK_ID/REPLACE_REVIEW_ID/review.md`. |
| Decision owners | Review recipient, delivery owner and human acceptance owner. |

Read applicable project instructions and the assigned task before reviewing.
Use recorded decisions to resolve revisions and scope. Do not infer approval
from a proposal, a delivery claim or a passing test.

When requirements or evidence are missing, record the specific gap and continue
unaffected review. Do not invent acceptance criteria. Optional improvements must
be identified separately from requirements.

## 4. Review procedure

1. Identify the task, delivery version, review scope and independence limitations.
2. Map each mandatory output, acceptance criterion and scope constraint to the
   delivered artifacts. Assign stable requirement IDs where needed.
3. Inspect the mapped artifacts and relevant supporting evidence. Check both
   artifact presence and whether the artifact fulfills its intended purpose.
4. Perform focused verification within the assignment. Inspect commands for
   side effects and resource use before execution. Preserve reviewed artifacts,
   reference data and shared state.
5. Record findings with requirement references, exact locations, evidence,
   consequences and conditions for resolution. Distinguish confirmed defects
   from missing evidence and non-blocking observations.
6. Determine the verdict, write `review.md`, verify the report and deliver it to
   the assigned recipient.

Distinguish reviewer-performed checks from delivery-reported checks. Existing
evidence can support a conclusion without repeating every run; explain why it
is sufficient. Do not treat an unavailable environment as proof of a delivery
defect or an unperformed check as a successful verification.

Operations requiring separate authority retain that requirement during review.
Do not install dependencies, mutate live databases, launch new experiments or
expand access merely to obtain a verdict. Record verification limits and the
evidence needed from the owner.

## 5. Assessment and verdict rules

Use these statuses for individual requirements:

| Status | Meaning |
| --- | --- |
| `MET` | Sufficient evidence supports the requirement's satisfaction. |
| `NOT_MET` | Evidence demonstrates that the requirement is unmet. |
| `NOT_VERIFIED` | Evidence, access or clarity is insufficient to reach a conclusion. |
| `NOT_APPLICABLE` | The task or a recorded decision excludes the requirement; cite the basis. |

Choose the overall verdict in this order:

1. **`CHANGES_REQUIRED`** when a mandatory requirement is `NOT_MET` or another
   demonstrated defect blocks acceptance. Also disclose remaining unknowns.
2. **`INCONCLUSIVE`** when no demonstrated blocker is established, but necessary
   evidence, requirement clarity or independent assessment is missing.
3. **`PASS`** when every mandatory applicable requirement is supported as met and
   no blocking finding remains. Include non-blocking observations and limits.

A missing required evidence artifact is an unmet requirement. An artifact whose
existence or contents cannot be checked remains unverified. Personal preferences
and optional enhancements do not create new acceptance conditions.

## 6. Required report: review.md

Use the structure below. Replace every `REPLACE_FIELD_NAME` field with actual facts, extend the
tables as needed, and use `None` where no findings or unresolved items exist.
Record the actual authoring session and review date. Report metadata uses the
project's record schema. Publication fields are included where required by the
project's knowledge workflow.

```markdown
---
record_schema: "REPLACE_RECORD_SCHEMA"
record_id: "REPLACE_RECORD_ID"
record_type: task_delivery_review
agent: "REPLACE_AUTHORING_AGENT"
source_session: "REPLACE_SOURCE_SESSION"
prepared_by: "REPLACE_PREPARED_BY"
task_id: "REPLACE_REVIEW_ASSIGNMENT_ID"
reviewed_task_id: "REPLACE_ORIGINAL_TASK_ID"
reviewer_spec: "REPLACE_REVIEWER_SPEC_PATH_AND_VERSION"
delivery_reference: "REPLACE_DELIVERY_REFERENCE"
delivery_version: "REPLACE_DELIVERY_VERSION"
created_at: "REPLACE_CREATED_AT"
version: 1
supersedes: null
status: delivered
verdict: "REPLACE_VERDICT"
human_acceptance: not_recorded
---

# Task Delivery Review: REPLACE_TASK_TITLE

## Verdict

**Verdict:** REPLACE_VERDICT

REPLACE_CONCISE_EXPLANATION_TIED_TO_THE_REQUIREMENTS_AND_CONSEQUENTIAL_FINDINGS

## Scope and sources

- Task and amendments: REPLACE_REFERENCES_AND_VERSIONS
- Review assignment: REPLACE_REFERENCE_AND_PERMITTED_CHECKS
- Delivery and artifacts: REPLACE_REFERENCES_AND_REVIEWED_VERSIONS
- Applicable instructions and criteria: REPLACE_REFERENCES
- Independence: REPLACE_PRIOR_INVOLVEMENT_AND_ITS_EFFECT_OR_NONE
- Review limits: REPLACE_EXCLUDED_AREAS_SAMPLING_OR_ACCESS_LIMITS

## Requirement assessment

| ID | Requirement and source | Mandatory? | Artifact / evidence | Status | Finding / explanation |
| --- | --- | --- | --- | --- | --- |
| R1 | REPLACE_REQUIREMENT | REPLACE_YES_NO | REPLACE_LOCATION_AND_EVIDENCE_ID | REPLACE_STATUS | REPLACE_REFERENCE_OR_REASON |

## Findings

### F1: REPLACE_CONCRETE_FINDING_TITLE

- Type: REPLACE_DEFECT_MISSING_EVIDENCE_OBSERVATION
- Acceptance impact: REPLACE_BLOCKS_ACCEPTANCE_PREVENTS_CONCLUSION_NON_BLOCKING
- Requirement and location: REPLACE_REQUIREMENT_ID_AND_EXACT_ARTIFACT_LOCATION
- Evidence: REPLACE_OBSERVED_FACTS_AND_EVIDENCE_REFERENCES
- Consequence: REPLACE_PRACTICAL_EFFECT_ON_THE_TASK_S_DELIVERY_OR_CLAIMS
- Resolution criterion: REPLACE_WHAT_MUST_BE_DEMONSTRATED_TO_RESOLVE_THE_FINDING

## Verification evidence

| ID | Check / command / inspected source | Origin | Actual result / evidence location | Supported conclusion and limits |
| --- | --- | --- | --- | --- |
| E1 | REPLACE_CHECK | REPLACE_REVIEWER_PERFORMED_DELIVERY_REPORTED_NOT_PERFORMED | REPLACE_RESULT_OR_REASON_SKIPPED | REPLACE_CONCLUSION_AND_LIMITS |

## Unresolved items and disposition

- Missing evidence or decisions: REPLACE_AFFECTED_REQUIREMENTS_OR_NONE
- Delivery owner: REPLACE_EXISTING_OWNER_RESPONSIBLE_FOR_CORRECTIONS
- Review recipient: REPLACE_REQUESTER_OR_COORDINATOR
- Human acceptance: REPLACE_NOT_RECORDED_OR_ACTUAL_DECISION_AND_SOURCE
- Follow-up review condition: REPLACE_CHANGED_ARTIFACTS_OR_EVIDENCE_NEEDED_OR_NONE
- Files written: REPLACE_REPORT_AND_ANY_AUTHORIZED_VERIFICATION_EVIDENCE
- Publication state: REPLACE_REQUIRED_STATES_AND_PENDING_QUEUE_OWNER_IF_APPLICABLE
```

Before delivery, parse the YAML, remove unfilled report fields, check links and
evidence references, and confirm that the verdict follows from the requirement
assessment. `review.md` serves as the review result and receipt unless the
assignment requires a separate receipt.

## 7. Handoff and stopping

Deliver the report and stop for disposition. The delivery owner performs
corrections; the requester controls subsequent assignments; the human acceptance
owner decides acceptance. A passing review does not authorize publication,
deployment or the next experiment.

Re-review a corrected delivery only under an assigned follow-up scope. Identify
the changed artifacts and preserve earlier reports under their original IDs.
Do not silently turn a review into implementation or project coordination.

## 8. Records and maintenance

Keep requirements, delivery, review and human decisions traceable through their
identities and versions. Record actual source sessions and separate technical
verdicts from human acceptance and publication state.

Where publication tracking is required, include an explicit pending item for the
existing queue owner in the report. The reviewer does not update shared ledgers,
build database checkpoints or publish to external systems. This specification's
publication state and routing owner are recorded in its header.

An assigned review task determines the permitted work. Preserve issued
specifications and review reports; material responsibility changes require a
successor specification with an incremented version and a superseded-record
reference.
