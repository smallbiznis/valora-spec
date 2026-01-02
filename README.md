# Valora Spec

**Valora Spec** is the authoritative, language-agnostic **API contract repository** for the Valora billing ecosystem.

This repository defines the **public surface area** of Valora: request/response schemas, resource models, error contracts, and versioning guarantees.
It is the single source of truth for SDK generation, documentation, and integration stability.

---

## Purpose

Valora Spec exists to **separate contracts from implementation**.

- Valora OSS implements billing logic
- Valora Cloud operates and hosts the system
- **Valora Spec defines what clients can rely on**

No runtime behavior lives here — only contracts.

---

## Scope (What This Repo Contains)

- OpenAPI specifications (HTTP APIs)
- Resource schemas (meters, products, pricing, subscriptions, invoices, usage)
- Error and pagination models
- Authentication and authorization expectations
- Backward-compatibility and versioning rules

---

## Explicit Non-Goals

Valora Spec does **not** contain:

- Business logic or billing rules
- Scheduler behavior or batch semantics
- Database schemas or migrations
- Payment execution or provider logic
- Infrastructure or deployment configuration

Those concerns belong to implementation repositories.

---

## Consumers

This repository is consumed by:

- Official Valora SDKs (per language, per repository)
- Valora Cloud
- External integrators and partners
- Documentation and portal tooling

All SDKs **must** be generated or validated against this spec.

---

## Versioning Policy

- Spec versions follow **semantic versioning**
- Minor versions may add backward-compatible fields
- Major versions may introduce breaking changes
- Implementations must declare which spec version they support

---

## Contract Authority

If there is a discrepancy between:

- SDK behavior
- Valora OSS behavior
- Documentation

**Valora Spec is the source of truth.**

Implementations must conform to this repository — not the other way around.

---

## Design Principles

- Deterministic contracts
- Low-ambiguity schemas
- Explicit error models
- Long-term compatibility over short-term convenience

---

## Relationship to Other Repositories

- `valora-oss` → billing engine implementation
- `valora-cloud` → hosted platform & operations
- `valora-spec` → **contract authority**

This separation is intentional and non-negotiable.

---

## License

Valora Spec is released under an open-source license.
See `LICENSE` for details.
