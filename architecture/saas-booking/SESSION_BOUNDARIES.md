# Session Boundaries

## Fixed Rule

Customer, Merchant, and Platform must not share:

- Login Page
- Session Cookie
- API
- Redirect Logic
- Authorization Middleware

## Session Design

| Actor | Route | Cookie scope | API family |
| ----- | ----- | ------------ | ---------- |
| Customer | `/store/{slug}` | Customer-only | Customer API |
| Merchant | `/merchant/{slug}` | Merchant-only | Merchant API |
| Platform | `/platform` | Platform-only | Platform API |

## Requirements

- Cookie names must be actor-specific.
- Session validation must include actor type.
- Authorization middleware must reject wrong actor sessions.
- Logout must clear only the relevant actor session unless a full sign-out is explicitly requested.
- Redirect after login must remain inside the same actor surface.

## Failure Examples

- Merchant login reads `next=/store/foo/checkout` and becomes customer login.
- Customer session cookie authorizes merchant dashboard API.
- Platform admin support route accepts merchant token.
- One OAuth callback creates a session before actor type is resolved.

## Acceptance

Session boundary is accepted only after real browser tests prove customer, merchant, and platform sessions cannot cross-authorize each other.