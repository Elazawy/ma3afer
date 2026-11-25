---
status: accepted
---

# 0002: Google OAuth Sign-In with Deferred WhatsApp OTP Verification

All users (Students, Teachers, and Admins) sign in exclusively with Google OAuth in Phase 1, storing provider credentials in a separate `AuthIdentity` table decoupled from `User`. Students provide their phone number and parent phone number during onboarding, but phone verification via WhatsApp Cloud API OTP is deferred until the Student's first monetary action (purchase, wallet top-up, or code redemption).

## Considered Options

- **Phone number + SMS OTP + password at signup**: Familiar in Egypt, but SMS OTP incurs immediate per-signup cost on casual visitors/free-preview browsers and requires SMS sender registration and password-reset flows.
- **Google OAuth without ever verifying phones**: Zero messaging cost, but leaves student phone numbers unverified—allowing fake numbers in watermarks and unlimited multi-account creation to bypass the 2-device limit.

## Consequences

- Zero OTP spend on unauthenticated browsers and free-preview viewers, verified Google emails for free notifications, and nearly universal Android/Google coverage among Egyptian students.
- Enforcing **one verified phone per account** at first purchase prevents a student from spinning up additional Google accounts to multiply their 2-device allowance and ensures the moving video watermark carries a real, traceable phone number.
- Phone uniqueness conflicts (e.g., siblings sharing a phone) are blocked from automatic transfer and resolved manually by Admins.
- Decoupling `AuthIdentity` from `User` lets us add Phone OTP or email/password login in Phase 2 by inserting a new identity row per user without migrating accounts.
- **Operational prerequisite**: Meta Business verification and WhatsApp authentication template approval can take days to weeks and must be initiated well ahead of launch.
