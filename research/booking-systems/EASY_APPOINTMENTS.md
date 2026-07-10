# Easy!Appointments

## 專案定位

Easy!Appointments is a self-hosted appointment scheduling platform for businesses that need public booking pages, customer records, service/provider setup, availability rules, notifications, and calendar sync.

## Repository

- https://github.com/alextselegidis/easyappointments
- Official site: https://easyappointments.org

## 技術棧

- PHP 8.2+
- MySQL
- JavaScript asset pipeline with Gulp
- Bootstrap, FullCalendar, jQuery, flatpickr, Select2
- Google Calendar API, PHPMailer, Monolog, iCalendar libraries
- Docker Compose for development

## 授權

- Code: GPL-3.0
- Content: CC BY 3.0 per project README

## 預約流程

1. Customer opens a booking page.
2. Customer selects service and provider.
3. System filters available dates and time slots from provider working plans and booking rules.
4. Customer enters contact details.
5. System creates appointment, sends notifications, and can sync with Google Calendar.
6. Admin/provider manages appointment and customer records.

## 會員模型

- Customer identity is lightweight and booking-oriented.
- Admin/provider identities are management users.
- Customer booking does not need to imply access to merchant administration.

## 服務／人員／資源模型

- Service is the bookable offering.
- Provider is the person who performs the service.
- Availability is mostly derived from provider schedules and service duration.
- Resource modeling is not the primary domain; it is better suited to service-provider appointments than room/equipment reservation.

## 多租戶支援程度

- Low to medium for SaaS reuse.
- Good for one business or one deployment per business.
- Not a direct model for one platform hosting many merchants unless tenant isolation is added above the app.

## 可重用模式

- Public booking wizard separated from admin management.
- Service-provider-duration model.
- Working plan plus exceptions as availability source.
- Appointment confirmation and notification lifecycle.
- Calendar sync as integration, not core identity.

## 不適合直接搬用的部分

- GPL code cannot be copied into proprietary or mixed-license product code without legal review.
- Single-install assumptions do not directly satisfy multi-tenant SaaS isolation.
- Existing UI and database shape should not be imported as BookingOS code.
- Provider/customer assumptions may not fit merchant/customer/platform route separation.

## 對 SaaS 預約系統的啟示

A SaaS booking product should keep customer booking flow simple while treating provider/admin capabilities as a separate authenticated surface. Reuse the domain pattern, not the code: service, provider, duration, working plan, appointment state, and notification events.