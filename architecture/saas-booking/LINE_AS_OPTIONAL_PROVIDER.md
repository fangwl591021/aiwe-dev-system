# LINE as Optional Provider

## Principle

LINE is an optional Authentication Provider and communication channel. It is not the product identity model by itself.

## Required Baseline

A booking product must still support core registration, login, and booking if LINE Login, LIFF, or Messaging API is unavailable.

## Allowed Uses

- Optional customer login provider.
- Optional identity linking after baseline account exists.
- Optional notifications and reminders.
- Optional merchant operational alerts.
- Optional LINE OA entry to a customer store route.

## Forbidden Uses

- Blocking basic account registration because LINE is not configured.
- Treating LIFF open success as product acceptance.
- Sharing Customer and Merchant session because both pass through LINE.
- Requiring LINE as the only route to book unless Tony explicitly defines that product constraint.

## Acceptance Checks

- Customer can register and book without LINE.
- Customer can link LINE later if enabled.
- LINE outage does not block basic booking.
- Merchant login does not route through customer LINE flow.
- Platform admin does not depend on LINE authentication.