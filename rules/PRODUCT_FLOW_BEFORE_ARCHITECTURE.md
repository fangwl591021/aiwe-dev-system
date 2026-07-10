# Product Flow Before Architecture

## Hard Rule

Define the complete user journey before Identity, Session, Migration, or framework-level architecture tasks.

## Required Order

1. Define Customer journey from real entry URL to completed booking.
2. Define Merchant journey from real login URL to booking management.
3. Define Platform journey from platform login to tenant support action.
4. Define acceptance criteria on real devices.
5. Then design identity, session, migration, API, and storage changes.

## What Does Not Prove Completion

- API returns 200.
- Token verification succeeds.
- Database migration succeeds.
- OAuth callback returns a profile.
- Admin-only screen can see records.

These are technical checks. Product completion requires the full journey to pass.

## Gate

If any core journey is not passing, do not start the next architecture task. Fix the journey first or explicitly mark it blocked.