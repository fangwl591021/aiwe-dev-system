# Merchant Journey Acceptance Checklist

## Scope

Merchant route: `/merchant/{slug}`

## Entry

- [ ] Merchant opens the real merchant URL.
- [ ] Merchant slug resolves to the correct tenant.
- [ ] Merchant is not redirected to customer login.
- [ ] Merchant is not redirected to platform login.

## Login and Session

- [ ] Merchant can log in through merchant login page.
- [ ] Merchant can log out and log back in.
- [ ] Merchant session cookie is separate from customer cookie.
- [ ] Merchant redirect logic remains inside `/merchant/{slug}`.

## Management Tasks

- [ ] Merchant can view dashboard.
- [ ] Merchant can create or edit service/resource.
- [ ] Merchant can configure availability.
- [ ] Merchant can view bookings for own tenant only.
- [ ] Merchant can update booking status if product scope allows it.

## Negative Checks

- [ ] Merchant session cannot access customer-only booking history.
- [ ] Merchant session cannot access platform admin APIs.
- [ ] Merchant Login Route does not switch to Customer Login because of `intent` or `next`.

## Evidence

- [ ] Browser/device recorded.
- [ ] Tenant/store slug recorded without customer data.
- [ ] Acceptance result linked from project status.