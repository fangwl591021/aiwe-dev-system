# Booking System Comparison

## 比較範圍

| System | Best reference for | License | Direct code reuse? |
| ------ | ------------------ | ------- | ------------------ |
| Easy!Appointments | Service-provider appointment flow | GPL-3.0 | No |
| LibreBooking | Resource reservation, quotas, waitlists | GPL-3.0-only | No |
| Cal.diy | Event types, public links, optional integrations | MIT | Not in this docs task |
| Thunderbird Appointment | Booker page plus subscriber dashboard | MPL-2.0 | No |

## 核心差異

- Easy!Appointments is service/provider/customer oriented.
- LibreBooking is resource/reservation oriented.
- Cal.diy is event-type/integration oriented.
- Thunderbird Appointment is subscriber/booker oriented.

## 對 BookingOS 的固定啟示

1. Customer, Merchant, and Platform are separate product surfaces, not roles under one login page.
2. Public booking must be validated through real customer journeys before identity migration tasks.
3. External providers such as LINE, Google, Apple, calendars, and video tools are optional providers, not core product gates.
4. Availability should be modeled from business rules before UI routing is finalized.
5. API success and token validity are technical checks, not product acceptance.

## 可重用模式

- Public booking link or store route.
- Merchant-owned service/event/resource definitions.
- Availability rules plus exceptions.
- Conflict checking before booking creation.
- Notification lifecycle.
- Separate management dashboards.
- Real-device release gates.

## 不可重用方式

- Do not copy GPL/MPL/MIT source code into `aiwe-dev-system`.
- Do not import database migrations.
- Do not merge external project auth flows into BookingOS without journey acceptance.
- Do not assume resource booking, service booking, and event booking share the same domain model.

## AIWE Documentation Rule

Research documents may reference external projects and patterns. They must not become hidden product repositories, code archives, or migration stores.