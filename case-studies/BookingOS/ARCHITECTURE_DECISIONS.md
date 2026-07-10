# BookingOS Architecture Decisions

## Decision 1: Separate Actor Routes

- Date: 2026-07-11
- Decision: Customer, Merchant, and Platform must use separate route families.
- Routes: `/store/{slug}`, `/merchant/{slug}`, `/platform`.
- Reason: Login and redirect confusion can break real product journeys even when APIs and tokens work.
- Impact: Every task touching auth, routing, sessions, or redirects must include actor-boundary checks.
- Reversible: No, not without reopening the full product journey design.

## Decision 2: External Auth Is Optional

- Date: 2026-07-11
- Decision: LINE, Google, Apple, and other providers are optional authentication providers.
- Reason: Provider outage or misconfiguration must not block basic registration, login, and booking.
- Impact: Baseline account login must exist for core journeys.
- Reversible: Only if Tony explicitly defines the product as provider-only.

## Decision 3: Acceptance Before Migration

- Date: 2026-07-11
- Decision: Product journey acceptance must come before additional identity/session/migration tasks.
- Reason: API 200, token verification, and migration success can hide broken customer or merchant flows.
- Impact: Release gates must include real entry, real device, and complete task checks.
- Reversible: No for core journeys.

## Decision 4: Documentation-Only Reuse

- Date: 2026-07-11
- Decision: BookingOS lessons can be documented in `aiwe-dev-system`, but BookingOS code is not copied here.
- Reason: This repo is a governance and reusable knowledge center, not a product monorepo.
- Impact: Modules remain experimental until verified in more than one product.
- Reversible: No, unless repository purpose is explicitly changed.