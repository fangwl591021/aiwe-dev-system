# SaaS Booking Tenant Model

## Core Entities

- Platform: owns the SaaS operating layer.
- Tenant: billing/support/governance container for one merchant organization.
- Merchant: business account operating one or more stores or booking surfaces.
- Store: public customer-facing booking surface identified by `{slug}`.
- Customer: person booking or managing their own appointments.

## Boundaries

Tenant ownership must be explicit on every merchant-managed object:

- Services
- Staff
- Resources
- Availability rules
- Bookings
- Customer relationship records
- Notifications
- Payment or billing references

## Multi-Tenant Requirements

- Every Merchant API must resolve tenant before reading or writing data.
- Every Customer booking route must resolve store/merchant before showing services or slots.
- Platform Admin may cross tenant boundaries only through platform authorization.
- Tenant data must not be selected by UI slug alone; backend authorization must enforce ownership.

## Anti-Patterns

- Treating tenant as only a display slug.
- Sharing merchant and customer sessions because they point to the same tenant.
- Using migration success as proof that tenant isolation is correct.
- Letting a customer account become merchant admin through route confusion.