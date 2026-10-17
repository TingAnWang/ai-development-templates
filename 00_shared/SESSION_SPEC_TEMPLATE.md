---
record_schema: "REPLACE_RECORD_SCHEMA"
session_spec_version: 1
record_id: "REPLACE_RECORD_ID"
agent: "REPLACE_AUTHORING_AGENT"
source_session: "REPLACE_SOURCE_SESSION"
prepared_by: "REPLACE_PREPARED_BY"
destination_session: "REPLACE_RECIPIENT_SESSION_NAME"
record_type: session_spec_template
task_id: "REPLACE_DEFINITION_TASK_ID"
session_id: "REPLACE_STABLE_LOGICAL_SESSION_ID"
session_name: "REPLACE_RECIPIENT_SESSION_NAME"
project_id: "REPLACE_PROJECT_ID"
project_root: "REPLACE_PROJECT_ROOT"
role: "REPLACE_PRIMARY_ROLE"
created_at: "REPLACE_CREATED_AT"
version: 1
supersedes: null
status: active_template
effective_from: "REPLACE_EFFECTIVE_FROM"
is_template: true
authority:
  approved_by: null
  approval_reference: null
  execution_requires_assigned_task: true
references:
  project_instructions: "REPLACE_PROJECT_RELATIVE_INSTRUCTIONS_PATH"
  current_navigation: "REPLACE_PROJECT_RELATIVE_NAVIGATION_PATH"
  task_at_issue: null
  knowledge_workflow: null
scope:
  read_context: []
  responsibility_areas: []
  write_scope: defined_by_each_authorized_task
  exclusions: []
handoff:
  reviewer: "REPLACE_REVIEW_OWNER"
  acceptance_owner: "REPLACE_HUMAN_DECISION_OWNER"
  stop_rule: deliver_assigned_outputs_and_wait_at_the_named_review_gate
publication:
  sqlite: not_indexed
  notion: not_published
  routing_owner: "REPLACE_ROUTING_OWNER"
  publication_owner: "REPLACE_PUBLICATION_OWNER"
  next_gate: review_session_spec_before_selecting_for_publication
---

# Session specification template: coordinator or implementer

Use this shared format for either a coordinator/reviewer or an implementation
session. See the [getting-started guide](../README.md) for role selection,
editable fields, and optional project dependencies. Replace every
`REPLACE_FIELD_NAME` field before issuing a completed specification.

No separate `SESSION_SPEC_STANDARD.md` is needed to start. If your project has
its own documentation standard, add its actual path under `references` and
follow it. Remove publication fields and requirements when those destinations
are not part of your workflow.

When creating the session record, assign its own unique `record_id`, set
`record_type: session_spec` and `is_template: false`, replace `active_template`
with the actual specification state, and title the document with the session's
name. Record applicable authority under `authority`; leave approval fields null
until there is an actual decision to cite. Use the actual author/session/date and
repair relative links.
The recipient is not the author; an adopted format is not permission for an
unassigned task.

## 1. Mission

REPLACE_MISSION

State the outcome this session supports in two or three sentences.
Explain the problem it owns, not just the tools/model it uses.

## 2. Responsibilities and boundaries

| Owns | Supports / hands off to | Does not decide or change independently |
| --- | --- | --- |
| REPLACE_CONCRETE_RESPONSIBILITY | REPLACE_NAMED_COLLABORATOR_AND_INTERFACE | REPLACE_BOUNDARY |

Role ownership persists across tasks. The exact files, operations, resource
limits and delivery scope come from the current authorized task, not this table.

## 3. Required context and sources of truth

List the applicable instructions, current navigation, accepted decisions,
contracts/interfaces and source evidence. Identify historical material and
proposals explicitly. For each important source give its path/record ID; pin its
revision/hash when the task depends on frozen bytes.

REPLACE_REQUIRED_SOURCES_AND_TASK_LOCATION

Identify required sources and how to find the latest active task. Paths are
relative to `project_root` unless explicitly identified otherwise; ordinary
Markdown links resolve relative to this document's location.

## 4. Working procedure

1. Read current instructions and assignment; confirm owner, scope, expected
   outputs, acceptance checks and stopping point.
2. Inspect existing work before changing it; preserve human edits and other
   sessions' artifacts. Report genuine conflicts, not speculative obstacles.
3. Perform the bounded work and proportionate verification. Keep evidence separate
   from interpretation, and implementation separate from independent acceptance.
4. Deliver a concise receipt with results, artifact links, tests/checks, limits
   and unresolved decisions. Update permitted navigation or give its owner a
   pending entry. Stop at the assigned gate.

REPLACE_ROLE_SPECIFIC_STEPS

Specify required role-specific steps, including the applicable implementation
tests, review reproductions or publication read-back. Include only the steps
relevant to this session's responsibilities.

## 5. Outputs and definition of done

| Output | Destination or naming convention | Required verification |
| --- | --- | --- |
| REPLACE_PRIMARY_DELIVERABLE | REPLACE_TASK_CONTROLLED_PATH | REPLACE_CHECK |
| Delivery receipt | REPLACE_RECEIPT_LOCATION | Actual source session, evidence, limits, next owner/gate |

Done means the assigned output and its verification are delivered; it does not
mean every project backlog item is fixed or human judgments have been accepted.

## 6. Coordination, permissions and stopping

- Request missing decisions from: REPLACE_DECISION_OWNER.
- Deliver to / reviewed by: REPLACE_REVIEWER.
- Human semantic or domain acceptance belongs to: REPLACE_ACCEPTANCE_OWNER.
- Shared files require one identified writer and preservation of prior versions.
- Helpers, costly runs and external publication follow the active task's explicit
  limits; no automatic dispatch or next-phase execution.
- On a blocker: report the evidence, affected scope and smallest needed decision;
  complete unrelated safe in-scope work. Do not invent approval or weaken a guard.

REPLACE_ROLE_SPECIFIC_STOP_CONDITION

Describe any role-specific stop condition. Distinguish a blocking correctness issue
from a non-blocking cosmetic improvement.

## 7. Knowledge maintenance and provenance

Every newly authored Markdown identifies its actual `source_session`. Link the
task, sources, delivery and review so later sessions can recover the reasoning.
Human approvals are attributed to their real decision-maker and source.

REPLACE_KNOWLEDGE_MAINTENANCE_REQUIREMENTS

If you use a shared synchronization ledger, identify its path and owner. Track Markdown
delivery/review, SQLite membership and Notion publication separately. If publication
is outside the assignment, report its pending owner/gate; do not claim synchronization
or launch a refresh. Keep private human answers out of publication unless authorized.
If you do not use SQLite, Notion, or a shared ledger, replace this field with
your actual record-maintenance procedure and remove the unused requirements.

## 8. Revision and approval

REPLACE_REVISION_AND_APPROVAL_BASIS

Identify the applicable approval source, remaining unresolved responsibilities, and
what this revision supersedes. Do not mark active with unresolved editable fields or
without applicable approval. Preserve prior sent/approved versions.
