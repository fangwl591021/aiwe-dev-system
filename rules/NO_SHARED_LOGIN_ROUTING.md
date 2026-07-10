# No Shared Login Routing

## Hard Rule

Customer, Merchant, and Platform login routes must remain separate.

## Fixed Routes

- `/store/{slug}` = Customer
- `/merchant/{slug}` = Merchant
- `/platform` = Platform Admin

## Forbidden

- Merchant Login Route changing to Customer Login based on `intent`.
- Merchant Login Route changing to Customer Login based on `next`.
- Customer Login authorizing Merchant API.
- Platform Login accepting Merchant or Customer sessions.
- Shared redirect logic before actor type is validated.

## Required Separation

Customer, Merchant, and Platform must not share:

- Login Page
- Session Cookie
- API
- Redirect Logic
- Authorization Middleware

## Acceptance

A real browser must prove each actor can log in, log out, and return to the correct route without crossing into another actor surface.