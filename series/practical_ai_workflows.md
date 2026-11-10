# Practical AI workflows: article companion

This companion connects three Medium article drafts to reusable instructions and
worked examples. The new series' Medium URLs have not been added yet; the titles
below identify the approved drafts. You can use every linked resource without
the articles or access to the author's project.

## Choose one starting point

| Article | Start with | Filled example | Optional detail |
| --- | --- | --- | --- |
| Giving an AI Implementer Enough Room to Finish | [Task assignment](../05_task_delivery/TASK_ASSIGNMENT_TEMPLATE.md) and [receipt](../05_task_delivery/DELIVERY_RECEIPT_TEMPLATE.md) | [Viewer completion](../examples/implementer_completion/README.md) | [Preparation/execution controls](../05_task_delivery/EXECUTION_CONTROLS_TEMPLATE.md) |
| The Decisions Behind My Multi-Agent Workflow | [Handoff](../06_coordination/HANDOFF_TEMPLATE.md) | [Coordination and publication hold](../examples/coordination_and_publication/README.md) | [Claim/evidence map](../06_coordination/CLAIM_EVIDENCE_TEMPLATE.md) |
| Designing an Annotation Record I Can Trust | [Requirement/test matrix](../07_acceptance/REQUIREMENT_TEST_MATRIX_TEMPLATE.md) | [Annotation history](../examples/annotation_history/README.md) | [Proposed implementation checks](../examples/annotation_history/TEST_PLAN.md) |

For a first coding task, use the [short starter message](../README.md#your-first-task)
or task template and a receipt. Add coordination or a coverage matrix only when
the work needs it. The folders are a menu, not a required sequence.

## What changed from the earlier public collection

The [October 17 baseline](https://github.com/TingAnWang/ai-development-templates/tree/52a4c5dab91d7220cb3afc5dfd18b8bd0b5cf51d)
already distinguished session roles, tasks, receipts, reviews, human acceptance,
and destination states. It supplied role/review/patch templates and a short task
message. It did not supply dedicated task-assignment or delivery-receipt files.

| Earlier collection | This companion adds |
| --- | --- |
| Continuing session responsibility | A concrete outcome assignment and its matching receipt |
| Scope and stopping fields | Worked repair permission and a separate optional fixed-attempt policy |
| Coordination/review roles | Routine decision ownership, phase activation, and a filled handoff |
| Publication-state separation | Claim qualifications and an actual held publication example |
| Evidence-based review | A domain history rule, counterexample, legitimate recovery, and a test-plan matrix |

The October 13 viewer example predates the baseline. The November diagnostic,
coordination, and annotation records supply later task-level detail. This is not
a claim that all underlying principles originated in November.

The existing seven template/example files under folders `00_shared` through
`04_pure_reviewer` are preserved in this update. The README now points to the
additional material. See the [changelog](../CHANGELOG.md).

## How to use the material honestly

**Reusable templates** contain `REPLACE_` fields. Fill them from your own
assignment, remove irrelevant sections, and keep original issued versions.
The new compact templates use Markdown identity fields; they require no YAML
parser or database. If your adopted project convention requires front matter,
add it consistently. The older session/review templates retain their YAML.

**Filled adaptations** condense actual assignments for teaching. They omit
private inputs and machine-specific restrictions, and do not activate work.
The example READMEs identify source types and dates. Direct quotations are
marked separately from adapted wording.

**Reported historical results** describe what the author's saved records say.
This collection does not distribute the private raw evidence or reproduce those
experiments. The new template adaptations have not themselves been evaluated as
a workflow intervention.

**Proposed checks** remain labeled unverified/Not run. The annotation example
does not claim a completed implementation or real-drawing validation.

For each new use, link the actual task, delivered version, checks, qualifications,
and decision owner. Borrow the reasoning behind a control; choose limits suitable
for the task rather than copying historical counts.

## Versioning the article links

Keep earlier article links working by retaining existing paths and using the
baseline link when discussing historical wording. When this companion is
accepted, choose a named release/tag and link each article's companion resources
to that exact version. A future edit to the default branch should not silently
change the instructions an article says it used.

The examples' factual cutoff is November 10, 2026. Later project outcomes belong
in a dated update, not a retroactive rewrite of the reported state.

