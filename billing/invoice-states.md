# Invoice States

State definitions:
- DRAFT: Computed but not issued. Amounts can still change.
- FINALIZED: Issued and immutable. Amounts and line items do not change.
- VOID: Canceled and non-payable. Terminal state.

Allowed transitions:
- DRAFT -> FINALIZED
- DRAFT -> VOID
- FINALIZED -> VOID (administrative reversal; does not modify the original amounts)

Invalid transitions:
- FINALIZED -> DRAFT
- VOID -> DRAFT
- VOID -> FINALIZED
- DRAFT -> DRAFT (no-op; not a state transition)
- FINALIZED -> FINALIZED (no-op; not a state transition)
- VOID -> VOID (no-op; not a state transition)
