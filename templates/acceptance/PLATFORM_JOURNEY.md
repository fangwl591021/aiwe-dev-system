# Platform Journey Acceptance Checklist

## Scope

Platform route: `/platform`

## Entry

- [ ] Platform admin opens the real platform URL.
- [ ] Platform login page is separate from customer and merchant login.
- [ ] Platform route rejects customer sessions.
- [ ] Platform route rejects merchant sessions.

## Platform Tasks

- [ ] Platform admin can log in.
- [ ] Platform admin can view tenant index or support target.
- [ ] Platform admin can inspect tenant status without exposing secrets.
- [ ] Platform admin can perform intended support action.
- [ ] Platform admin action is logged or auditable if required.

## Boundary Checks

- [ ] Platform API requires platform authorization middleware.
- [ ] Platform redirect logic never sends users to `/store/{slug}` or `/merchant/{slug}` as a login fallback.
- [ ] Platform views do not expose customer personal data beyond product-approved support scope.

## Evidence

- [ ] Admin role recorded.
- [ ] Test tenant recorded without production customer data.
- [ ] Result linked from project status.