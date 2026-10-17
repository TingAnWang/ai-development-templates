# AI-assisted development: session and review templates

Reusable Markdown templates for giving AI coding sessions clear responsibilities,
bounded assignments, and evidence-based reviews. These files accompany a Medium
series about using AI in development. They are intended for developers who want
to make implementation, handoffs, and review easier to follow across sessions.

Start with one small task and one implementation session. Add a separate reviewer
when an independent check is useful; add a coordinator when several tasks or
sessions need coordination. The full project workflow shown in the examples is
an option, not a prerequisite.

## Where these files come from

The source is [12 · Copy-ready templates and checklists](https://app.notion.com/p/12-Copy-ready-templates-and-checklists-3eb5ef30d44781949a9fef9ccc4fd834),
part of *AI-Assisted Development & Knowledge Management — A Practical Guide*.
The Notion page may require access. It contains short task, message, delivery,
verification, review, and human-decision examples as well as the attachments from
which this collection was prepared. This folder contains the adapted attachments;
it is not an export of the entire chapter.

The public-copy edits consolidate the shared session template, standardize editable
fields, and distinguish reusable instructions from historical project examples.

**Medium articles:** links and article-to-template mappings will be added when
the series URLs are available. You can use the getting-started steps below
without access to the articles or Notion page.

## Start here: which file should I use?

Read this table in order. The numbered folders group the source material; they
do not prescribe the order of work.

| What you want to do | Start with | Optional reference |
| --- | --- | --- |
| Give a session an implementation role | [Shared session template](00_shared/SESSION_SPEC_TEMPLATE.md) | [Historical implementation example](03_implementation/SESSION_SPEC_PROJECT_FABLE.md) |
| Coordinate assignments and integration review | [The same shared session template](00_shared/SESSION_SPEC_TEMPLATE.md) | [Historical coordinator/reviewer example](02_coordinator_reviewer/SESSION_SPEC_CODEX.md) |
| Review a delivered task without repairing it | [Reviewer session template](04_pure_reviewer/SESSION_SPEC_TASK_DELIVERY_REVIEWER_TEMPLATE.md) | [Historical reviewer specification](04_pure_reviewer/SESSION_SPEC_TASK_DELIVERY_REVIEWER.md) |
| Write the result of a delivery review | [Review report template](04_pure_reviewer/TASK_DELIVERY_REVIEW_TEMPLATE.md) | The reviewer template defines the verdict rules |
| Document a correction to an earlier delivery | [Patch note template](01_patch/codex-patch-note-template-v1.md) | Use after there is a delivery to correct |

The shared session template replaces the two identical `SESSION_SPEC_TEMPLATE.md`
files previously kept in the coordinator and implementation folders. Both roles
now use `00_shared/SESSION_SPEC_TEMPLATE.md`.

## Understand the documents and roles

A **session specification** defines a session's continuing role and boundaries.
A **task assignment** defines the particular job: goal, inputs, permitted changes,
acceptance checks, and stopping point. A **delivery receipt** records what was
actually delivered and checked. A **review report** assesses that delivery against
the assignment. A **patch note** records a later correction.

Session specifications do not replace task assignments. This collection provides
session, review-report, and patch templates; dedicated task-assignment and delivery
receipt templates are not included. For a first task, put those details in a clear
chat message or project document. The Notion source has short examples.

| Role | Main responsibility |
| --- | --- |
| Human owner | Chooses the goal and scope, resolves material decisions, and decides acceptance and subsequent work. |
| Coordinator/reviewer | Turns goals into bounded assignments and checks integration and technical claims. |
| Implementer | Makes the assigned change and delivers artifacts, checks, and limitations. |
| Task-delivery reviewer | Inspects a submitted delivery and reports findings without taking over implementation. |

Codex, Fable, and Opus are names used in the source examples for tools or sessions
assigned those roles. They are not required identities for your setup. Choose your
own session names. A reviewer who helped author a change should disclose that
involvement rather than describe the review as independent.

## Your first task

1. **Choose a small outcome.** State the desired behavior, files that may change,
   checks that demonstrate completion, and where the work stops. One human can
   manage the handoffs; automatic dispatch and multiple simultaneous agents are
   not required.
2. **Create a working copy of the shared session template.** For example, save it
   as `docs/sessions/implementer.md` in your development project. Fill the role,
   responsibilities, sources, outputs, and review owner. Keep these reusable
   source templates separate from your filled records.
3. **Adapt the metadata and dependencies.** Follow the next two sections. Assign
   a unique record ID and actual author/date, set `record_type: session_spec` and
   `is_template: false`, and choose a status that reflects the real state.
4. **Give the assistant the specification and task together.** If it can read
   project files, identify their paths explicitly. Otherwise, paste the completed
   specification followed by the assignment. Replace every editable field in the
   starter message below before sending it.
5. **Inspect the delivery.** Ask for usable artifact paths, changes made, checks
   actually performed and their results, unchecked areas, and unresolved issues.
   Verify the behavior that matters before deciding acceptance.
6. **Add a reviewer when useful.** Copy the reviewer session template and report
   template into your project. Give the reviewer the original assignment,
   delivered version, allowed checks, and an exact report destination. The
   reviewer reports findings; the human decides whether to request corrections.

Starter message, assuming you used the implementation-spec destination above:

```text
Read docs/sessions/implementer.md and the applicable project instructions.
Carry out this task:

Goal: REPLACE_TASK_OUTCOME
Inputs and baseline: REPLACE_INPUTS_AND_VERSIONS
Allowed changes: REPLACE_WRITABLE_PATHS_AND_SCOPE
Acceptance checks: REPLACE_REQUIRED_CHECKS
Delivery destination: REPLACE_DELIVERY_DESTINATION
Reviewer: REPLACE_REVIEW_OWNER
Stop after: REPLACE_STOP_CONDITION

Deliver the artifact paths, what changed, actual check results, limitations,
and anything that needs a human decision.
```

For a follow-up review, identify the completed reviewer specification, task,
delivery, and report template by their actual project paths. A report destination
can follow `reviews/REPLACE_TASK_ID/REPLACE_REVIEW_ID/review.md`. Give each review
its own path so a later review preserves the earlier findings.

## Fill editable fields consistently

All editable fields use `REPLACE_FIELD_NAME`: uppercase words separated by
underscores. This includes anonymized details in historical examples and fields
inside embedded report examples. A token can be part of a path or identifier,
such as `REPLACE_PROJECT_SLUG-codex`. Replace the token itself with your value.

| Field | Meaning | Illustrative value |
| --- | --- | --- |
| `REPLACE_PROJECT_ROOT` | Absolute root of your development project | `D:/projects/sample-app` |
| `REPLACE_RECORD_SCHEMA` | Your chosen record-schema identifier | `sample_app_agent_record/v1` |
| `REPLACE_SOURCE_SESSION` | Session that actually authored the record | `sample-implementer` |
| `REPLACE_RECORD_ID` | Unique identity for this document | `sample-implementer-session-v1` |
| `REPLACE_CREATED_AT` | Actual record creation date | `2026-10-16` |

The schema identifier labels your records; this collection does not include a
schema validator. Front matter is the YAML metadata between the opening `---`
lines. `source_session` identifies the authoring session, while
`destination_session` identifies a recipient. Do not confuse the two.

Complete required fields before using a copy. Remove optional fields or sections
that do not apply; where a project requires a field, use its documented
`not_applicable` value with a reason. Use `unknown` or `not_checked` for missing
facts rather than inventing evidence. `null` means no value has been recorded.
Remove usage instructions from the finished record. Search your filled copy for
`REPLACE_` to catch remaining editable fields.

## Adapt paths and project dependencies

You need a project folder, a Markdown editor, and an AI assistant. Git is useful
for reviewing changes and preserving versions. SQLite, Notion, a shared ledger,
multiple models, and an automation framework are optional.

| Reference in the source material | How to adapt it |
| --- | --- |
| `AGENTS.md` | Use your project's actual instructions file or put the applicable instructions in the assignment. Remove an unused reference. |
| `README.md` / current navigation | Point to the document that identifies your current assignment and status; the task document itself can serve this purpose. |
| `docs/SESSION_SPEC_STANDARD.md` | Historical project convention, not an included dependency. For a first use, follow the completion instructions in the chosen template. Remove this reference if your project has no separate standard, or replace it with your own. |
| `handoffs/` | Optional task/message directory. Use the location where you actually keep assignments. |
| Knowledge-workflow README / synchronization ledger | Optional records for tracking selected documents and publication. Remove these requirements if you do not use that workflow. |
| SQLite / Notion / publication owners | Remove the publication block and related requirements if you use neither destination. If you keep them, record actual states and owners. |

The reviewer template's `output_template` initially names the report template
from this collection's root. When adopting it, update that field and its Markdown
link to wherever you put the report template. Do the same for all moved files.

Metadata paths are relative to the declared `project_root` unless marked absolute;
ordinary Markdown links resolve relative to the document containing the link.
Template instructions describe potential destinations in your own project, not
additional files promised by this collection. After copying, check both kinds
of reference from their intended locations.

## Read the examples as historical context

The three example specifications are anonymized adaptations of source project
records. Their dates, session names, statuses, and publication fields describe
the source examples as recorded. They do not establish the current state of
this repository or of a project that adopts them.

In particular, the implementation example's `sqlite: indexed` and
`notion: published` are historical metadata, not starting defaults. To adopt an
example, create a new record, replace its identity, authorship, dates, authority,
paths, owners, and states, and remove domain-specific requirements that do not
apply. Prefer starting from the shared template and consulting examples for
wording.

The reviewer files use `PASS`, `CHANGES_REQUIRED`, and `INCONCLUSIVE`, with the
rules in the reviewer specification. The broader Notion chapter also illustrates
other review wording; use the explicit rules of the specification you adopt.
A passing technical review records its stated scope; the human owner still
decides acceptance and the next action.
