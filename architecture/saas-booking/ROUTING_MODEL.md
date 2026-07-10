# SaaS Booking Routing Model

## Fixed Routes

- `/store/{slug}` = Customer
- `/merchant/{slug}` = Merchant
- `/platform` = Platform Admin

## Route Ownership

### Customer Route

`/store/{slug}` is the public customer route. It may show merchant profile, services, availability, booking form, customer login/register, booking status, and customer-facing confirmation.

### Merchant Route

`/merchant/{slug}` is the merchant route. It may show merchant login, dashboard, services, staff, resources, availability, bookings, reports, and merchant settings.

### Platform Route

`/platform` is the platform route. It may show tenant review, support tools, platform-level configuration, audit views, and operational checks.

## Forbidden Routing Behavior

- Merchant Login Route must never redirect to Customer Login based on `intent`, `next`, query string, or stale session state.
- Customer Login Route must never authorize Merchant Admin functions.
- Platform routes must never accept Merchant or Customer sessions.
- Shared callback handlers must resolve actor type before issuing sessions.
- Redirect fallback must return to the same actor surface, not a generic home page.

## Acceptance Checks

- A customer entering `/store/{slug}` can complete the customer journey without touching `/merchant/{slug}`.
- A merchant entering `/merchant/{slug}` can log in and manage bookings without being sent to customer login.
- A platform admin entering `/platform` cannot be authorized by customer or merchant cookies.