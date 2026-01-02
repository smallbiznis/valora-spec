
# Valora Spec

**Valora Spec** is the authoritative, language-agnostic **API contract repository** for the Valora billing ecosystem.

It defines the **public and stable interface** of Valora: resources, schemas, request/response models, error contracts, and versioning guarantees.

This repository is the **single source of truth** for:

- SDK generation
- External integrations
- Public documentation
- Compatibility enforcement

---

## Why Valora Spec Exists

Billing systems fail when **contracts drift from implementation**.

Valora Spec exists to ensure that:

- Clients integrate against **stable, explicit contracts**
- Implementations evolve **without breaking consumers**
- SDKs and documentation stay **mechanically consistent**
- Billing correctness is not coupled to transport or language

Valora Spec separates **what Valora promises** from **how Valora is implemented**.

---

## Scope

This repository defines:

- OpenAPI specifications (HTTP APIs)
- Canonical resource models(meters, products, pricing, subscriptions, invoices, usage)
- Request / response schemas
- Error models and pagination contracts
- Authentication and authorization expectations
- Backward-compatibility rules

Nothing in this repository executes at runtime.

---

## Explicit Non-Goals

Valora Spec does **not** define:

- Billing algorithms or rating logic
- Scheduler or batch execution behavior
- Database schemas or migrations
- Payment execution or provider integrations
- Infrastructure, deployment, or SLOs

Those concerns belong to implementation and operations layers.

---

## Contract Authority

In case of conflict between:

- Valora OSS behavior
- SDK implementations
- Documentation
- Client assumptions

**Valora Spec is authoritative.**

All implementations **must conform** to this repository.

---

## Versioning & Compatibility

Valora Spec follows **semantic versioning**:

- **PATCH** — clarifications, documentation, non-functional changes
- **MINOR** — backward-compatible additions
- **MAJOR** — breaking contract changes

Implementations must explicitly declare:

- which spec version they implement
- their supported compatibility range

---

## Consumers

Valora Spec is consumed by:

- Official Valora SDKs (one repository per language)
- Valora Cloud
- External partners and integrators
- Documentation and portal tooling

SDKs must be **generated from or validated against** this spec.

---

## Design Principles

- Contract-first, implementation-agnostic
- Deterministic and auditable schemas
- Low ambiguity over convenience
- Long-term stability over short-term velocity

---

## Repository Boundaries

- `valora-oss` — billing engine implementation
- `valora-cloud` — hosted platform and operations
- `valora-spec` — **contract authority**

This separation is intentional and enforced.

---

## License

Released under an open-source license.
See `LICENSE` for details.
