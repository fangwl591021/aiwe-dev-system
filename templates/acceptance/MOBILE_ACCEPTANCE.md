# Mobile Acceptance Checklist

## Scope

Use this checklist for customer-facing journeys and any merchant journey expected to work in mobile browser or LINE in-app browser.

## Device Coverage

- [ ] iPhone Safari or iOS WebView checked if target users include iOS.
- [ ] Android Chrome checked if target users include Android.
- [ ] LINE in-app browser checked only when LINE entry is part of product scope.
- [ ] Desktop-only assumptions are documented.

## Journey

- [ ] Real entry URL opens correctly.
- [ ] Login/register form is usable on mobile.
- [ ] Keyboard does not block required actions.
- [ ] Date/time picker is usable.
- [ ] Booking confirmation is visible.
- [ ] Error messages are readable.
- [ ] Back/refresh behavior does not lose completed booking state.

## External Provider Failure

- [ ] Baseline login works when LINE is unavailable.
- [ ] Baseline login works when Google/Apple is unavailable.
- [ ] Provider error returns user to same actor surface.

## Evidence

- [ ] Device model or browser recorded.
- [ ] Date/time of acceptance recorded.
- [ ] Known mobile limitations recorded in `KNOWN_ISSUES.md`.