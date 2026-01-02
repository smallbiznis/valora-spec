# Subscription States

State definitions:
- CREATED: Subscription exists but is not yet active.
- ACTIVE: Subscription is active and billable.
- PAUSED: Temporarily stopped; billing is suspended.
- CANCELED: Cancellation requested; no renewals.
- ENDED: Service has ended and billing is complete. Terminal state.

Allowed transitions:
- CREATED -> ACTIVE
- CREATED -> CANCELED
- ACTIVE -> PAUSED
- ACTIVE -> CANCELED
- ACTIVE -> ENDED
- PAUSED -> ACTIVE
- PAUSED -> CANCELED
- PAUSED -> ENDED
- CANCELED -> ENDED

Any transition not listed above is invalid.
