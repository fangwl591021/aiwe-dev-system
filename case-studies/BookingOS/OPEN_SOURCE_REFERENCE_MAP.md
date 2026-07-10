# Open Source Reference Map

## Easy!Appointments

- Useful reference: service, provider, duration, booking wizard, notification lifecycle.
- BookingOS lesson: keep customer booking simple and separate from merchant administration.
- Do not copy: GPL code, database schema, UI implementation.

## LibreBooking

- Useful reference: resource reservation, quotas, waitlists, role-based resource management.
- BookingOS lesson: if resource/capacity booking is needed, model conflicts and ownership explicitly.
- Do not copy: GPL code, migrations, organization roles as-is.

## Cal.diy

- Useful reference: event types, public scheduling links, optional integrations.
- BookingOS lesson: integrations are useful but must not drive first customer acceptance.
- Do not copy: monorepo code, env setup, integration implementation.

## Thunderbird Appointment

- Useful reference: public booker page, subscriber dashboard, availability setup, Dockerized acceptance environment.
- BookingOS lesson: booker and owner dashboard are separate product journeys.
- Do not copy: MPL code, example credentials, deployment config, migrations.

## Combined Lesson

BookingOS should reuse architecture patterns, acceptance gates, and domain vocabulary. It should not import external project implementation or treat any one project as a complete SaaS booking blueprint.