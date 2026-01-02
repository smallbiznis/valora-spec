# Retries

Retryable errors:
- RATE_LIMITED (HTTP 429)
- INTERNAL (HTTP 5xx)
- Any error response with retryable: true

Non-retryable errors include INVALID_USAGE and DUPLICATE_IDEMPOTENCY_KEY.

Backoff expectations:
- Use exponential backoff with jitter.
- Honor Retry-After when present; it overrides client backoff.
- Cap retry attempts and total time to avoid indefinite retry loops.

Responsibilities:
- SDKs must not perform hidden retries.
- Clients decide when and how to retry, using the retryable field, HTTP status, and Retry-After.
- For POST requests, retries are only safe when Idempotency-Key is provided.
