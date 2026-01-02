# Idempotency

Idempotency protects clients from duplicate processing when a request is retried.

Required endpoints:
- POST /usage
- POST /subscriptions

Rules:
- Clients must send an Idempotency-Key header on every required endpoint.
- The key scope is the combination of caller identity, HTTP method, and path.
- Same key + same payload must return the same outcome (status code and response body) as the original request.
- Same key + different payload must return HTTP 409 with error code DUPLICATE_IDEMPOTENCY_KEY.
- Keys must be unique per logical operation; clients must not reuse keys for unrelated requests.

Idempotency is evaluated against the request payload as received, including JSON body and relevant headers.
