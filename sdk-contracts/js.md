# JavaScript SDK Contract

- The SDK is a thin transport client; it must not implement billing, aggregation, or rating logic.
- The SDK must not perform hidden retries. Any retry behavior must be explicit and caller-controlled.
- POST /usage and POST /subscriptions must require an Idempotency-Key input and set the header.
- Errors must surface the raw error payload (code, message, retryable) and HTTP status without reinterpretation.
- Expose cancellation and timeout controls (for example via AbortController) and allow custom fetch/agent injection.
