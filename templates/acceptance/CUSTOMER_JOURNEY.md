# Customer Journey Acceptance Checklist

## Scope

Customer route: `/store/{slug}`

## Entry

- [ ] Customer opens the real store URL.
- [ ] Store slug resolves to the correct merchant.
- [ ] Customer is not redirected to merchant or platform login.
- [ ] Page works on target mobile browser.

## Registration and Login

- [ ] Customer can register with baseline account method.
- [ ] Customer can log in without LINE, Google, or Apple.
- [ ] Customer can log out and log back in.
- [ ] External auth failure does not block baseline login.

## Booking

- [ ] Customer can view services or resources.
- [ ] Customer can select valid date and time.
- [ ] Unavailable slots are hidden or clearly blocked.
- [ ] Customer can submit booking.
- [ ] Customer receives confirmation state.
- [ ] Customer can view only their own booking status.

## Negative Checks

- [ ] Customer session cannot access merchant APIs.
- [ ] Customer session cannot access platform APIs.
- [ ] Customer `next` redirect cannot move into merchant dashboard.

## Evidence

- [ ] Device/browser recorded.
- [ ] URL recorded.
- [ ] Test account type recorded without secret values.
- [ ] Screenshots or screen recording saved outside this repo if needed.