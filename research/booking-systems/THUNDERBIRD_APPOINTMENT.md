# Thunderbird Appointment

## 專案定位

Thunderbird Appointment is an open-source appointment link product: invite others to grab times on a calendar, choose a date, and manage appointments through subscriber dashboards.

## Repository

- https://github.com/thunderbird/appointment

## 技術棧

- Backend: Python, FastAPI, SQLAlchemy, pytest, Alembic
- Frontend: VueJS with Vite
- Database/cache/dev services: PostgreSQL, Redis, Mailpit through Docker Compose
- Deployment notes reference AWS ECS and Pulumi

## 授權

- MPL-2.0

## 預約流程

1. Subscriber configures availability and appointment settings.
2. Booker opens the public booker page.
3. Booker selects available time and submits appointment details.
4. Subscriber manages bookings and settings.
5. System relies on backend, frontend, database, Redis, and mail services.

## 會員模型

- Subscriber is the scheduling owner.
- Booker is the public attendee/customer.
- Admin access is separated and allow-listed in local setup.
- The backend README notes Mozilla Accounts for deployed internal auth and password auth for self-hosting, which means authentication mode is environment-dependent.

## 服務／人員／資源模型

- The dominant model is subscriber availability plus appointment slots.
- It is not a resource inventory system.
- It is closer to personal appointment links than full merchant storefront booking.

## 多租戶支援程度

- Medium as subscriber-based appointment ownership.
- Not enough by itself for Platform Admin, Merchant Admin, and Customer separation without additional routing and authorization boundaries.

## 可重用模式

- Public booker page plus private dashboard separation.
- Availability setup as a first-class user task.
- Dockerized local acceptance environment.
- Admin allow-list and first-user setup as explicit bootstrap controls.

## 不適合直接搬用的部分

- Do not copy code, migrations, Pulumi, or `.env` values.
- Password registration behavior is not a complete customer registration reference.
- Mozilla Account assumptions are not suitable as a mandatory BookingOS auth dependency.
- Local demo credentials or example secrets from docs must not be copied into AIWE docs as project configuration.

## 對 SaaS 預約系統的啟示

Thunderbird Appointment reinforces that public booker and owner dashboard must be separate journeys. External identity and calendar integrations can help, but they cannot replace the core password-based customer and merchant flows required for BookingOS acceptance.