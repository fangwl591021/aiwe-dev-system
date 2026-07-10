# Reusable Lessons

## Acceptance Lessons

- Real customer entry matters more than direct API success.
- Real mobile device checks are required for customer booking.
- Token verification and migration success are not product completion.
- External auth success is provider connectivity, not full journey acceptance.

## Architecture Lessons

- Customer, Merchant, and Platform require separate route families.
- Login page, session cookie, API, redirect logic, and authorization middleware must be actor-specific.
- Store slug is not enough for authorization; backend ownership must be checked.
- Availability must be computed from merchant rules, exceptions, conflicts, capacity, and timezone.

## Reuse Candidates

- Actor-separated release gate checklist.
- SaaS booking domain vocabulary.
- Availability model checklist.
- External auth optional-provider rule.
- Open-source booking research map.

## Not Yet Production-Reusable

No BookingOS runtime module is production reusable from this case study yet. Any module must be verified in at least two products before being marked reusable.