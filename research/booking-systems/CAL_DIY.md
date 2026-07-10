# Cal.diy

## 專案定位

Cal.diy is the community-driven open-source edition of Cal.com for self-hosted scheduling infrastructure. The project states it is intended for individuals and self-hosters, with commercial/enterprise features removed.

## Repository

- https://github.com/calcom/cal.diy
- Historical redirect: https://github.com/calcom/cal.com

## 技術棧

- Next.js
- React
- tRPC
- Tailwind CSS
- Prisma
- PostgreSQL
- Yarn workspaces and Turborepo
- Integration-oriented architecture for calendars, conferencing, embeds, and app-store style extensions

## 授權

- MIT for Cal.diy according to the project README.

## 預約流程

1. Host configures event types, availability, calendar connections, and booking rules.
2. Booker opens a public scheduling link.
3. Booker selects date/time based on host/event availability.
4. System creates booking and coordinates calendar/conferencing integrations.
5. Host manages bookings, event types, and connected apps.

## 會員模型

- Host/account identity is central.
- Booker/customer can complete a booking through a public link with limited identity requirements.
- Teams, organizations, SSO/SAML, and enterprise features are removed from Cal.diy, so SaaS team features must not be assumed from this edition.

## 服務／人員／資源模型

- Event type is the key bookable product.
- Host availability and calendar conflicts determine slot availability.
- Integrations can enrich the booking but should not become required for core booking.

## 多租戶支援程度

- Medium as a self-hosted scheduling platform pattern.
- Not a direct reference for AIWE merchant/customer/platform separation because Cal.diy explicitly removes organization and enterprise features.

## 可重用模式

- Event type as a reusable booking definition.
- Public booking link as customer entry.
- Host dashboard separated from public booking.
- Calendar and video integrations as optional providers.
- Strong acceptance need around env setup and integration failure modes.

## 不適合直接搬用的部分

- Large monorepo and integration surface are too heavy for first BookingOS architecture tasks.
- Removed enterprise features mean it should not be treated as a complete multi-tenant SaaS reference.
- MIT license is permissive, but code should still not be copied into `aiwe-dev-system` or BookingOS during this documentation task.

## 對 SaaS 預約系統的啟示

Use Cal.diy as a reference for public scheduling links, event types, host availability, and optional integrations. Do not let integration architecture drive the first customer journey. The customer must still be able to register, log in, and book without external auth or calendar providers.