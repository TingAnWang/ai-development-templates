---
record_schema: "REPLACE_RECORD_SCHEMA"
record_id: "REPLACE_RECORD_ID"
record_type: task_delivery_review_template
agent: "REPLACE_AUTHORING_AGENT"
source_session: "REPLACE_SOURCE_SESSION"
prepared_by: "REPLACE_PREPARED_BY"
task_id: "REPLACE_REVIEW_ASSIGNMENT_ID"
project_id: "REPLACE_PROJECT_ID"
created_at: "REPLACE_CREATED_AT"
version: 1
supersedes: null
status: draft
is_template: true
reviewed_task_id: "REPLACE_ORIGINAL_TASK_ID"
review_assignment: "REPLACE_REVIEW_ASSIGNMENT_REFERENCE"
reviewer_spec: "REPLACE_ADOPTED_REVIEWER_SPEC_PATH"
delivery_reference: "REPLACE_DELIVERY_RECEIPT_OR_MESSAGE"
delivery_version: "REPLACE_REVISION_HASH_OR_IDENTIFIED_SNAPSHOT"
delivery_owner: "REPLACE_DELIVERY_OWNER"
verdict: null
human_acceptance: not_recorded
publication:
  sqlite: not_indexed
  notion: not_published
  routing_owner: "REPLACE_ROUTING_OWNER"
  publication_owner: "REPLACE_PUBLICATION_OWNER"
  next_gate: select_for_next_authorized_alignment_milestone
---

# Review report template

## Using this template

This file is not a completed review. Use it with the
[reviewer session template](SESSION_SPEC_TASK_DELIVERY_REVIEWER_TEMPLATE.md).
Copy it to the assignment's exact output path, normally
`reviews/REPLACE_TASK_ID/REPLACE_REVIEW_ID/review.md`.

Before delivery:
- Replace all `REPLACE_FIELD_NAME` values and instructional text with actual review facts.
- Set a unique record_id, record_type: task_delivery_review, is_template: false,
  status: delivered, and the actual authoring agent/source_session/prepared_by,
  review task_id, date, version and supersedes value.
- Keep reviewed_task_id as the original task being assessed.
- Set verdict to PASS, CHANGES_REQUIRED or INCONCLUSIVE in the header and body.
- Adjust publication owners/states to the target project; unknown values are null.
  Remove the publication block and related report fields if your workflow does not use them.
- Add as many requirement, evidence and finding entries as necessary.
- Replace placeholder finding examples with "None" if there are no findings.
- Use links that resolve from the final report directory. Remove this usage section
  and the template title above it from the completed report.
Do not copy the template author's identity as the report author's identity.

# Task Delivery Review: REPLACE_TASK_TITLE

## 1. Verdict

**Verdict:** `REPLACE_PASS_CHANGES_REQUIRED_OR_INCONCLUSIVE`

REPLACE_CONCISE_REASON_TIED_TO_THE_REQUIREMENT_RESULTS_AND_MATERIAL_FINDINGS.

**Human acceptance:** REPLACE_NOT_RECORDED_OR_ACTUAL_RECORDED_DECISION_WITH_SOURCE.

## 2. Scope and reviewed sources

| Item | Source / version |
| --- | --- |
| Original task and applicable amendments | REPLACE_PATHS_SECTIONS_AND_VERSIONS |
| Review assignment and permitted checks | REPLACE_ASSIGNMENT_REFERENCE |
| Applicable instructions / domain criteria | REPLACE_REFERENCES_OR_NONE |
| Delivery receipt or message | REPLACE_REFERENCE |
| Delivered artifacts and relevant dependencies inspected | REPLACE_PATHS_AND_VERSIONS_OR_CUTOFF |

**Independence:** REPLACE_ACTUAL_PRIOR_INVOLVEMENT_OR_NONE_AND_ITS_EFFECT_ON_REVIEW.

**Review limits:** REPLACE_EXCLUDED_AREAS_SAMPLING_ACCESS_LIMITS_OR_NONE.

## 3. Requirement-to-delivery assessment

Include every mandatory output, acceptance criterion and scope constraint.
Allowed results: `MET`, `NOT_MET`, `NOT_VERIFIED`, `NOT_APPLICABLE`.
For `NOT_APPLICABLE`, cite the task basis or recorded decision.

| ID | Requirement and source | Mandatory? | Artifact / evidence | Result | Finding / explanation |
| --- | --- | --- | --- | --- | --- |
| R1 | REPLACE_REQUIREMENT_AND_TASK_SECTION | REPLACE_YES_OR_NO | REPLACE_ARTIFACT_LOCATION_AND_EVIDENCE_ID | REPLACE_RESULT | REPLACE_FINDING_ID_OR_REASON |

## 4. Findings

### F1: REPLACE_CONCRETE_FINDING_TITLE

- **Type:** REPLACE_DEFECT_MISSING_EVIDENCE_OR_OBSERVATION
- **Acceptance impact:** REPLACE_BLOCKS_ACCEPTANCE_PREVENTS_CONCLUSION_OR_NON_BLOCKING
- **Requirement / location:** REPLACE_REQUIREMENT_ID_AND_EXACT_ARTIFACT_LOCATION
- **Evidence:** REPLACE_OBSERVED_FACTS_AND_EVIDENCE_REFERENCES
- **Consequence:** REPLACE_EFFECT_ON_CORRECTNESS_COMPLETENESS_COMPLIANCE_OR_CLAIMS
- **Resolution criterion:** REPLACE_WHAT_THE_OWNER_MUST_DEMONSTRATE_TO_RESOLVE_THIS

## 5. Verification evidence

Use evidence IDs referenced by the requirement table and findings. Distinguish
`reviewer_performed`, `delivery_reported` and `not_performed` checks. Include
inspection evidence when no command is appropriate; do not imply tests ran.

| ID | Check / command / inspected source | Evidence origin | Actual result and evidence location | What it establishes / limits |
| --- | --- | --- | --- | --- |
| E1 | REPLACE_CHECK | REPLACE_ORIGIN | REPLACE_RESULT_OR_NOT_PERFORMED_AND_REASON | REPLACE_SUPPORTED_CONCLUSION_AND_LIMITS |

## 6. Unresolved items and disposition

**Missing evidence or decisions:** REPLACE_SPECIFIC_GAPS_AND_AFFECTED_REQUIREMENTS_OR_NONE.

**Existing owner(s):** REPLACE_DELIVERY_OWNER_FOR_CORRECTIONS_AND_REQUESTER_FOR_DISPOSITION.

**Condition for follow-up review:** REPLACE_CHANGED_ARTIFACTS_OR_EVIDENCE_NEEDED_OR_NONE.

**Files written by this review:** REPLACE_REVIEW_MD_PATH_AND_ANY_PERMITTED_EVIDENCE_PATHS.

**Publication state / pending item:** REPLACE_SOURCE_IDENTITY_LOCAL_REVIEW_STATE_SQLITE_AND_NOTION_STATES_AND_EXISTING_QUEUE_OWNER_WHEN_APPLICABLE.

This report completes the assigned delivery review. Final acceptance and any
subsequent work remain with the named decision owners.
