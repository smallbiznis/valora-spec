# Billing Lifecycle

Valora computes billing from accepted usage and subscription state. External systems execute payments and settlement.

Canonical flow:

usage -> aggregation -> rating -> invoice (DRAFT) -> invoice (FINALIZED)

- usage: Usage records are ingested and validated.
- aggregation: Usage is grouped by subscription, metric, and time window.
- rating: Aggregated usage is priced using the active plan and pricing rules.
- invoice (DRAFT): A draft invoice is generated for review and reconciliation.
- invoice (FINALIZED): The invoice is finalized and issued.

Once finalized, an invoice is immutable. Corrections are handled by issuing a new invoice or voiding the prior one; the finalized record itself is never altered.
