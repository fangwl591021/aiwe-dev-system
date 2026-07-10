# Booking Domain Model

## Core Objects

- Tenant: SaaS ownership container.
- Merchant: business operator.
- Store: public booking surface.
- Customer: booking user.
- Service: what can be booked.
- Staff: person assigned to service delivery.
- Resource: room, equipment, seat, or capacity object when needed.
- Availability Rule: recurring rule defining when booking is possible.
- Availability Exception: date-specific override.
- Booking: confirmed or pending appointment/reservation.
- Booking Event: lifecycle record such as created, confirmed, cancelled, rescheduled, no-show.

## Minimum Booking Flow

1. Resolve store from `/store/{slug}`.
2. Show merchant-owned services or resources.
3. Resolve availability from rules, exceptions, conflicts, and capacity.
4. Authenticate or collect required customer identity.
5. Create booking under tenant and store ownership.
6. Notify customer and merchant.
7. Allow customer and merchant to view the booking through their own surfaces.

## Domain Rules

- Service booking and resource booking are related but not identical.
- Availability is not just UI slots; it is a backend rule and conflict decision.
- Booking ownership must include tenant, merchant/store, and customer identifiers.
- Booking state transitions should be explicit and auditable.

## Acceptance Boundary

A booking model is not accepted until it can create, view, cancel or reschedule through real Customer and Merchant journeys, not only through direct API calls.