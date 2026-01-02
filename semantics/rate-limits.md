# Rate Limits

Valora applies conceptual rate limits to protect service stability. Limits may vary by endpoint, tenant, or time window and can change without notice.

429 behavior:
- HTTP 429 is returned when a limit is exceeded.
- The error body uses code RATE_LIMITED and retryable: true.

Retry-After semantics:
- Retry-After may be provided as seconds or an HTTP-date.
- Clients must honor Retry-After before issuing the next retry.
- When Retry-After is absent, clients should apply exponential backoff with jitter.
