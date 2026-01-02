# Go SDK Contract

- The SDK is a thin transport client; it must not implement billing, aggregation, or rating logic.
- The SDK must not perform hidden retries. Any retry behavior must be explicit and caller-controlled.
- All operations must accept context.Context and honor cancellation and deadlines.
- POST /usage and POST /subscriptions must require an Idempotency-Key input and set the header.
- Errors must surface the raw error payload (code, message, retryable) and HTTP status; prefer a typed error that implements error.
- The HTTP client must be injectable to support custom transport, timeouts, and observability.
