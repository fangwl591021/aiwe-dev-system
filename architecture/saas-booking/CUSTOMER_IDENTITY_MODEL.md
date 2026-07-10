# Customer Identity Model

## Purpose

Customer identity exists so a person can register, log in, book, review booking status, and receive notifications. It is not merchant identity and not platform identity.

## Required Baseline

A SaaS booking product must support basic account registration and login without external providers:

- Email or phone based registration.
- Password or verified one-time-code flow, depending on product decision.
- Customer session cookie scoped to Customer routes only.
- Booking ownership check before showing customer booking history.

## Optional Providers

LINE, Google, Apple, and other providers may be added as optional authentication providers. They must not replace the baseline customer login unless the product explicitly accepts that dependency.

## Separation Rules

- Customer login page is not merchant login page.
- Customer session does not authorize merchant APIs.
- Customer redirect logic stays within `/store/{slug}` customer routes.
- Customer identity migration is not complete until customer journey acceptance passes on real devices.

## Acceptance Signals

- Customer can register through real store entry.
- Customer can log out and log back in through customer route.
- Customer can create a booking after login.
- Customer can view only their own booking status.
- External provider outage does not block basic customer login and booking.