# External Auth Is Optional

## Hard Rule

LINE, Google, Apple, and other external providers are optional Authentication Providers. They are not the base product identity model.

## Required Baseline

Core product functions must work with basic account registration and login:

- Customer registration.
- Customer login.
- Customer booking.
- Merchant login.
- Merchant booking management.
- Platform admin login.

## Failure Handling

External provider outage, callback error, expired channel setting, or missing provider configuration must not block basic account registration, login, and booking.

## Not Accepted As Completion

- LINE profile fetched.
- Google OAuth token verified.
- Apple callback returns a subject.
- LIFF opens the page.

These prove provider connectivity only. They do not prove the product journey.