# Worked example: finish a review workflow

Companion to **Giving an AI Implementer Enough Room to Finish**.
Start with the [filled task](TASK.md), then compare its requirements with the
[adapted receipt](RECEIPT.md). To use the pattern in your own project, copy the
[task](../../05_task_delivery/TASK_ASSIGNMENT_TEMPLATE.md) and
[receipt](../../05_task_delivery/DELIVERY_RECEIPT_TEMPLATE.md) templates.

**Provenance:** prepared with AI drafting assistance from the author's saved
project records and approved article draft, with a factual cutoff of November 10,
2026. The viewer assignment and completion note are dated October 13; they
predate the October 17 public template baseline. The diagnostic successor task,
report, and result review are dated November 4–5. Original project files, raw
logs, and datasets are not included. Results below are reported historical
results, not checks executed by this documentation repository. Adapted wording
is labeled; direct quotations are identified.

## Why the task needed to change

The review tool had reset/export/import and history defects. Repairs addressed
the mechanisms, but a later delivery still lacked a completed browser
save/resume check. The owner needed the usable workflow and its evidence.

Two actual clauses from the viewer completion assignment were:

> Also fix related defects discovered in normal reviewing, changing answers, import/export, point selection, the harness or finalizer during this assignment.

> There is **no separate correction-iteration quota** for CPU implementation, tests, harnesses or finalization. Fix related problems, retain meaningful failure records and continue within the above budget without another authorization.

The shared resource budget still applied, including six browser launches.
The permission covered related repairs; it did not change question meanings,
drawing targets, human answers, or model-work scope.

The final completion note reported three corrections to a test helper and
browser harness, with no production viewer code changes during those corrections.
Launches one and two failed on harness defects. Launch three passed 63 steps
on the delivered site bytes. Headless Firefox and synthetic answers limited
what that result established; the real unsaved-work navigation dialog was untested.

The useful pattern is acceptance tied to a complete user action sequence.
There is no measured claim here that the wording alone caused the result.

## Different controls for a fixed diagnostic

A later diagnostic had one real attempt. An early version stopped in its own
module-origin guard before any evaluator call: dry-run had skipped the import
and guard exercised during real execution. Another version failed preflight
because a reusable sealer treated already loaded helper modules as if the
sealing call had introduced them.

The repaired boundary distinguished modules introduced by the call from the
requirements of a fresh standalone process, and tested both contexts.

The successor assignment used these controls, condensed here as an adaptation:

| Stage | Allowance | Gate/stop |
| --- | --- | --- |
| Preparation | At most two non-evaluating passes and one bounded correction between them | All required controls pass on the same identified revision |
| Real execution | One attempt using the unchanged passing revision | No behavioral repair, resume, or retry after start |

Positive controls and refusals for the exact expected reason mattered. An
unrelated error that rejects both good and bad inputs does not validate a guard.

An actual instruction was:

> If all 15 pass and bindings hold, use r1; do not spend the second pass merely to repeat success.

The third version passed all 15 unique controls on its first pass and produced
13 complete records in one real attempt. The second-pass allowance was unused;
its presence cannot be credited with causing success.

All 13 records still routed to the model: three flags, ten cannot-evaluate
results, zero clear cases. A subsequent comparison used 26 saved model answers
and made no new inference calls. It found no routing benefit in that grouped,
synthetic, development-exposed sample. Completion did not require a favorable
experimental result.

Use the [optional execution controls](../../05_task_delivery/EXECUTION_CONTROLS_TEMPLATE.md)
when preserving attempt identity matters. The viewer's repair policy and this
diagnostic's fixed-attempt policy answer different needs; neither is a default
for every assignment.

## What to adapt

Keep the outcome, supporting repair permission, concrete acceptance evidence,
and candid receipt. Choose your own resource limits. For a simple change, omit
the experimental controls. Keep test answers separate from real judgments, and
report an unchecked workflow explicitly.

