# Release Gate Checklist

## Product Flow Gate

- [ ] Customer journey passes from real `/store/{slug}` entry.
- [ ] Merchant journey passes from real `/merchant/{slug}` entry.
- [ ] Platform journey passes from real `/platform` entry if included in release scope.
- [ ] Mobile acceptance passes for customer journey.

## Boundary Gate

- [ ] Customer, Merchant, and Platform have separate login pages.
- [ ] Customer, Merchant, and Platform have separate session cookies.
- [ ] Customer, Merchant, and Platform have separate API authorization paths.
- [ ] Redirect logic cannot cross actor surfaces.
- [ ] Authorization middleware rejects wrong actor sessions.

## Technical Gate

- [ ] Tests or manual verification completed.
- [ ] Database migration checked if changed.
- [ ] API checks completed if changed.
- [ ] No real Secret committed.
- [ ] No production customer data committed.

## Documentation Gate

- [ ] `PROJECT_STATUS.md` updated.
- [ ] `CHANGELOG.md` updated.
- [ ] `KNOWN_ISSUES.md` updated if any issue remains.
- [ ] Architecture or decision docs updated if boundary changed.

## Decision

- [ ] Release allowed.
- [ ] Release blocked.
- [ ] Block reason recorded.