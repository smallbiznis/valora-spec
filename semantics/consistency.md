# Consistency

Consistency model:
- Usage ingestion is eventually consistent. Accepted usage may take time to appear in aggregation, invoices, or list endpoints.
- Subscription create and update operations are strongly consistent for the subscription resource (read-after-write for that subscription).
- Invoice lists and aggregates are eventually consistent until an invoice is finalized.
- Finalized invoices are strongly consistent and immutable.

Client assumptions:
- Do not assume immediate visibility of usage in invoice or subscription views.
- Use idempotency keys for safe retries of POST operations.
- Treat list endpoints as potentially stale and order-independent.

Billing correctness guarantees:
- Valora computes invoices deterministically from accepted usage, subscription state, and pricing rules.
- Finalized invoices reflect all accepted usage within the billing window known at finalization time.
- Late or corrected usage is reflected by issuing a new invoice or a voided-and-reissued sequence, not by mutating a finalized invoice.
