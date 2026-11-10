# Filled test-plan example: annotation history and resume

**Status:** adaptation of requirements in the November 10 prepared synthetic-only
implementation assignment. **All rows below are proposed checks, not passing
results.** The earlier targeted design review is a different evidence set.

**Adaptation author:** repository maintainer with AI drafting assistance  
**Prepared:** November 10, 2026  
**Scope:** selected requirements illustrating the method; not the complete
27-rule contract or a runnable test suite.  
**Implementation version:** not supplied in this example.

| Rule | Planned implementation responsibility | Scenario and expected evidence | Layer | Coverage | Result |
| --- | --- | --- | --- | --- | --- |
| Pending-text Keep | Resolve owning label and text state immediately before the event | Refuse invalid Keep even if later text is present; retain a valid recovery case | Semantic history | unverified | Not run |
| Initial pending evidence | Use the owning occurrence's creation sequence when no text event exists | Correct identity, omitted identity, and forged identity cases | Semantic history | unverified | Not run |
| Owner consistency | Validate relationship ownership against valid history before dependent checks | Owner mismatch refused for the correct reason; valid owner accepted | Semantic history | unverified | Not run |
| Source identity | Validate actual opened SVG against record identity before replacing work | Matching synthetic SVG/record round trip succeeds; wrong-source import refuses without losing current work | Import/export integration | unverified | Not run |
| Save/resume | Preserve decisions and history across a full revision | Browser export, fresh resume, continued edit, re-export, and comparison outside the browser | Browser workflow | unverified | Not run |

For a real implementation, map each responsibility to an actual code location,
include every required rule, and attach saved results to each executed check.
Record expectations before implementation inspection when the review assignment
requires that independence.

Use real hashes of the invented SVG in importer fixtures. Keep semantic fixtures
separate when their identifiers were never backed by a source file. Do not
weaken import validation to make those fixtures fit.

Coverage is classified as executed, statically argued, or unverified; execution
status is separate from whether the result passed. A screenshot supports a
display observation, not all semantic or importer requirements.

The source records establish qualified design acceptance and preparation of an
implementation task. They do not establish a completed annotation tool, real
drawing suitability, human usability, or training-data permission.

