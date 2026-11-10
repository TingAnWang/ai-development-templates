# Worked example: a history rule and its acceptance tests

Companion to **Designing an Annotation Record I Can Trust**.
The [filled test plan](TEST_PLAN.md) connects the design to proposed implementation
checks. Start from the [matrix template](../../07_acceptance/REQUIREMENT_TEST_MATRIX_TEMPLATE.md)
for your own product.

**Provenance:** prepared with AI drafting assistance from the author's saved
version-six design addendum, November 10 closure review and acceptance, later
prepared synthetic-implementation assignment, and approved article draft.
Factual cutoff: November 10, 2026. This is a simplified contract example.
The private schema, complete validator, fixtures, browser tool, and drawings
are not included. Historical review results are reported, not reproduced here.

## Separate answers with different meanings

The design used three relationship slots: observed attachment, intended
construction, and target feature/pin. Placement was separate. An observed
attachment could differ from the intended relationship.

Text depended on selected ink. Role and relationships depended on ink and text.
Placement depended on those judgments. Evidence changes made affected answers
pending while preserving their earlier values in history. A deliberate Keep
could reaffirm an answer when its preconditions held; merely retaining a value
did not reaffirm it.

## The actual pending-text clause

> A reaffirmation of a role, a link, a placement or a disposition is invalid when the text of the owning label is pending immediately before that reaffirmation, in sequence order.

The rule concerns the state immediately before the event. Later text cannot
make an earlier invalid Keep valid.

The following is an illustrative history, not a serialized production fixture:

```text
1. Confirm label text and supply a role.
2. Return text to pending; dependent answers need confirmation.
3. Keep the old role while text remains pending.
4. Enter text again.

Step 3 is invalid even though the final snapshot contains text.
```

Ownership and general history validity must be checked first. Explanatory
pseudocode for this one rule is:

```text
for each dependent-answer reaffirmation in sequence order:
    label = its already-validated owning label
    text = latest text after-state for that label with sequence < this event
    if no earlier text event exists:
        text = PENDING
    if text is PENDING:
        reject the reaffirmation
```

The text's own Keep is outside this particular restriction; its other rules
still apply. A draft may remain honestly pending. A fresh answer while text is
pending is a new judgment governed by the other rules, not a Keep.

A legitimate recovery confirms or re-enters text first, then deliberately
reaffirms dependent answers against that evidence, assuming the other identity
and validity requirements hold. If the text event invalidates them again,
they need subsequent confirmation. Silently relabeling Keep as a fresh answer
is not a recovery.

## Test the boundary, including valid behavior

| Illustrative scenario | Expected behavior |
| --- | --- |
| Keep a dependent answer while text is pending, then enter text | Refuse the earlier Keep |
| Save a pending draft without an invalid Keep | Permit an incomplete draft |
| Confirm text, then Keep with valid identity/evidence | Permit recovery |
| Give a fresh answer while text is pending | Evaluate it as a new judgment under remaining rules |
| Change a relationship's owner without valid history | Refuse the ownership mismatch first |

These conceptual expectations are not passing importer or browser tests.
A guard that rejects everything would fail the legitimate cases.

The review task required the reviewer to write focused interpretations and
expected results before reading the implementation author's checker, and to
make an initial independent run first. Permitted reuse of its own earlier
helper required disclosed lineage.

The historical review covered 47 declared states: 45 matched initially and two
matched after a correction to the reviewer's fixture identifier. All 42
comparisons with the writer's saved observations agreed. The review identified
its implemented subset, static checks, and unexercised paths. This supported
qualified design acceptance, not proof of every contract rule or a usable
browser tool.

## From accepted design to implementation requirements

The accepted history rules changed while the wire schema stayed unchanged.
Two owner-selected interpretations also guided implementation: text Keep
affects dependent freshness, and never-entered text uses the owning occurrence's
creation sequence as its initial pending-evidence identity. An interpretation
is not automatically an independently executed result.

A later synthetic-only implementation assignment required all contract rules
and separated semantic fixtures, matching synthetic source/record importer
tests, and browser workflows. Its existence did not establish activation or
completion. The [test plan](TEST_PLAN.md) therefore starts with unverified
coverage and **Not run** results.

Historical invented JSON can exercise a semantic rule without identifying a
real SVG. Import tests need a newly invented source and a matching record with
real hashes/references. Disabling the source guard to import an old fixture
would erase the property being tested.

The transferable method is to name dependencies, invalidate affected answers,
distinguish retained values from reaffirmations, test forbidden and legitimate
histories, and then verify save/resume at the real integration layer. None of
these mechanisms proves that a fresh human answer is true.

