# BookingOS Case Study

## Purpose

This folder records architecture and acceptance lessons from BookingOS without copying product code, tenant data, secrets, LIFF IDs, migrations, or customer records.

## Scope

BookingOS is used here as a case study for SaaS booking boundaries:

- Customer route: `/store/{slug}`
- Merchant route: `/merchant/{slug}`
- Platform route: `/platform`
- External auth providers are optional.
- Real-device product acceptance is required.

## Files

- `ARCHITECTURE_DECISIONS.md`: durable decisions extracted from the case.
- `CUSTOMER_LOGIN_FAILURE_REVIEW.md`: review of customer login routing failure class.
- `OPEN_SOURCE_REFERENCE_MAP.md`: mapping from researched systems to reusable lessons.
- `REUSABLE_LESSONS.md`: patterns that may inform future AIWE projects.

## Exclusions

Do not add:

- Secret
- LIFF ID
- 正式客戶資料
- BookingOS 原始程式碼
- 正式 Tenant 資料
- 完整 Migration 程式