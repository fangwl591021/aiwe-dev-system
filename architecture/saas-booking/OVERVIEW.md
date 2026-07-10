# SaaS Booking Architecture Overview

## 定位

This folder defines reusable SaaS booking architecture patterns for AIWE projects. It is not BookingOS product code and must not contain migrations, runtime modules, secrets, tenant data, or customer records.

## Fixed Route Ownership

| Route | Actor | Purpose |
| ----- | ----- | ------- |
| `/store/{slug}` | Customer | Public customer-facing merchant booking surface |
| `/merchant/{slug}` | Merchant | Merchant login, setup, services, resources, bookings, staff |
| `/platform` | Platform Admin | AIWE/platform operations, tenant review, support, governance |

## Non-Sharing Rule

Customer, Merchant, and Platform must not share:

- Login Page
- Session Cookie
- API
- Redirect Logic
- Authorization Middleware

## Acceptance-First Principle

Architecture is not complete until a real user can finish the intended task from the real entry URL on the real target device. API 200, token verification, or migration success are supporting checks only.

## File Map

- `ROUTING_MODEL.md`: route ownership and redirect boundaries.
- `TENANT_MODEL.md`: tenant, merchant, store, platform boundaries.
- `CUSTOMER_IDENTITY_MODEL.md`: customer account and session rules.
- `BOOKING_DOMAIN_MODEL.md`: booking domain objects.
- `AVAILABILITY_MODEL.md`: slot and conflict rules.
- `SESSION_BOUNDARIES.md`: cookie/session isolation.
- `LINE_AS_OPTIONAL_PROVIDER.md`: LINE as optional auth provider only.