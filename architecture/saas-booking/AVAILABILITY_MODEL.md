# Availability Model

## Purpose

Availability is the contract between merchant setup and customer booking. It must be computed consistently for both the customer booking page and merchant management surface.

## Inputs

- Merchant business hours.
- Service duration and buffer time.
- Staff working plans.
- Resource capacity and conflicts.
- Date-specific exceptions.
- Existing bookings.
- Cutoff rules, cancellation windows, and booking lead time.
- Timezone.

## Output

Availability output should answer:

- Which dates can be booked?
- Which time slots can be booked?
- Which staff/resource can fulfill the booking?
- Why is a slot unavailable?

## Rules

- Customer UI must not invent availability locally.
- Merchant preview and customer booking must use the same availability source.
- Timezone handling must be explicit.
- Slot reservation or booking creation must re-check conflicts on the backend.
- External calendar sync can reduce availability but must not be the only source of truth for core booking.

## Acceptance Checks

- Merchant changes hours and customer slots update correctly.
- Existing booking blocks conflicting slot.
- Closed day does not show slots.
- Mobile customer booking shows the same available slots as desktop.
- External calendar outage does not break basic merchant-defined availability if the product supports local availability.