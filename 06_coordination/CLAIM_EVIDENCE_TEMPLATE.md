# Claim and evidence map template

Use this for a summary, release note, or knowledge update whose claims draw on
multiple records. A few rows beside the document may be enough.
Replace all `REPLACE_` fields; remove destinations your task does not use.

- Record ID/revision: REPLACE_RECORD_ID_AND_REVISION
- Authoring session (`source_session`): REPLACE_ACTUAL_AUTHOR
- Date: REPLACE_DATE
- Assigned scope and source cutoff: REPLACE_SCOPE_AND_CUTOFF
- Summary/delivery version: REPLACE_DOCUMENT_VERSION

## Claims

| ID | Claim to publish | Source/version and author | Review/evidence basis | Qualification or unsupported extension |
| --- | --- | --- | --- | --- |
| C1 | REPLACE_PRECISE_CLAIM | REPLACE_SOURCE_LOCATION_VERSION_AND_AUTHOR | REPLACE_PERFORMED_OR_REPORTED_CHECK | REPLACE_LIMIT_AND_WHAT_CANNOT_BE_INFERRED |

Preserve a negative result and its qualifications. “Execution completed” does not
mean “the method improved performance.” Distinguish an owner's interpretation
from a tested result. Resolve conflicting records by their scope and dated
decisions; do not silently rewrite historical sources.

## Decisions and destinations

| Item/destination | Actual state at cutoff | Decision or read-back evidence | Next owner/action |
| --- | --- | --- | --- |
| Technical result | REPLACE_STATE | REPLACE_REFERENCE | REPLACE_OWNER_AND_ACTION |
| Local summary | REPLACE_STATE | REPLACE_REFERENCE | REPLACE_OWNER_AND_ACTION |
| REPLACE_EXTERNAL_DESTINATION | REPLACE_STATE | REPLACE_REFERENCE_OR_MISSING_FACT | REPLACE_OWNER_AND_ACTION |

Use precise states such as prepared, delivered, reviewed, accepted with
qualifications, pending, held, or published with read-back. State what each
refers to. Do not add planned items to a verified coverage total.

## Optional publication prerequisite

Complete this only when the assignment includes preparing or performing an
external update:

- Exact destination and proposed change: REPLACE_DESTINATION_AND_CHANGE
- Existing authorization or remaining decision: REPLACE_AUTHORITY_OR_GATE
- Required capture scope: REPLACE_PAGES_SUBTREES_ROWS_OR_OTHER_SCOPE
- Method and evidence of coverage: REPLACE_SUPPORTED_CAPTURE_AND_PAGINATION
- Missing facts and their consequence: REPLACE_GAPS_OR_NONE_IDENTIFIED
- Planned verification after the authorized change: REPLACE_READBACK_CHECKS
- Disposition when prerequisites fail: REPLACE_HOLD_OR_AUTHORIZED_ALTERNATIVE

A response saying it is not truncated does not, by itself, establish that all
intended content was included. Record what the method actually proves. If the
agreed prerequisite remains unmet, preserve the proposed change and the exact
decision needed. See the [worked hold](../examples/coordination_and_publication/README.md#the-publication-hold).

