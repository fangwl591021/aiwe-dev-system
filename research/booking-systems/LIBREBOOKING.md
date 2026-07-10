# LibreBooking

## 專案定位

LibreBooking is an open-source resource scheduling solution for organizations that reserve rooms, equipment, shared spaces, or other resources.

## Repository

- https://github.com/LibreBooking/librebooking
- Main development branch: `develop`

## 技術棧

- PHP 8.2+
- MySQL 8+ or MariaDB 10.6+
- Smarty templates
- Bootstrap 5 UI
- Composer dependencies including Monolog, PHPMailer, Google API client, Microsoft Graph, LDAP, Stripe, and iCalendar tooling
- Docker deployment option

## 授權

- GPL-3.0-only

## 預約流程

1. User logs in.
2. User selects schedule/resource/date/time.
3. System checks resource rules, availability, quotas, credits, and conflicts.
4. User creates reservation or joins a waitlist where supported.
5. Admin/resource manager reviews usage, roles, reports, and configuration.

## 會員模型

- User accounts are central.
- Role-based access control separates regular users, admins, and resource managers.
- Integrations include LDAP, OAuth2/SAML notes, and calendar exports/imports.

## 服務／人員／資源模型

- Resource is the core bookable object.
- Schedule groups resources into calendars or resource pools.
- Quotas, credits, waitlists, and usage reports are important resource governance patterns.
- Service/provider concepts are secondary compared with resource reservation.

## 多租戶支援程度

- Medium for organization-level segmentation, low for public SaaS merchant isolation without additional tenant boundaries.
- Strong for internal resource scheduling, not directly a marketplace-style merchant/customer/platform split.

## 可重用模式

- Resource-first booking and conflict checking.
- Waitlist and quota concepts.
- Role-based management surface.
- Reporting and audit mindset.
- iCalendar integration for external calendar tools.

## 不適合直接搬用的部分

- GPL code cannot be copied into AIWE proprietary product repos without legal review.
- Organization/resource assumptions are not the same as merchant service booking.
- Existing roles should not be mapped directly to Customer, Merchant, and Platform without journey validation.
- Database migrations and complete reservation logic must not be imported into `aiwe-dev-system`.

## 對 SaaS 預約系統的啟示

If BookingOS needs rooms, seats, equipment, or capacity management, LibreBooking is the stronger reference than service-provider tools. The reusable lesson is to model conflicts, quotas, and resource ownership explicitly before building UI or authentication migration tasks.