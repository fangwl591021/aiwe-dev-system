# Real Device Acceptance Required

## Hard Rule

A core journey is not accepted until it passes through the real entry, real device class, and complete task.

## Required Acceptance Inputs

- Real customer URL, for example `/store/{slug}`.
- Real merchant URL, for example `/merchant/{slug}`.
- Real platform URL, for example `/platform`.
- Mobile device or mobile browser for customer flows.
- Desktop browser for merchant/platform flows when those are operational surfaces.

## What Does Not Count Alone

- API 200.
- Token verification.
- Migration success.
- Local-only direct route testing.
- Admin seeing raw data.
- Screenshot of only the first page.

## Gate

If any core journey is not passing, do not enter the next architecture task. Record the failed journey, reproduction path, expected result, actual result, and owner.