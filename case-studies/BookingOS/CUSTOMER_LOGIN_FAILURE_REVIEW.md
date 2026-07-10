# Customer Login Failure Review

## Failure Class

Customer journey can fail when routing, redirect, or session logic treats Customer and Merchant login as interchangeable.

## Symptoms

- Customer enters `/store/{slug}` but is sent to merchant-oriented login or dashboard logic.
- Merchant login route changes to customer login based on `intent` or `next`.
- API checks pass but the real customer cannot complete registration, login, and booking.
- Token or migration work appears successful while product journey remains broken.

## Root Cause Pattern

- Shared login page.
- Shared session cookie.
- Shared redirect helper.
- Shared authorization middleware.
- Actor type inferred too late or inferred from query string.

## Required Fix Pattern

1. Define customer journey first.
2. Separate Customer, Merchant, and Platform routes.
3. Issue actor-specific sessions only after actor type is resolved.
4. Keep redirect fallback inside the same actor surface.
5. Validate on real mobile entry, not only API or local route.

## Regression Tests

- Customer `/store/{slug}` login cannot enter merchant dashboard.
- Merchant `/merchant/{slug}` login cannot become customer login due to `intent` or `next`.
- Platform `/platform` rejects merchant and customer sessions.
- External auth provider failure does not block baseline customer login.

## Case Study Boundary

This review does not include BookingOS source code, tenant data, LIFF IDs, secrets, or migration code.