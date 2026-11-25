---
status: accepted
---

# 0003: Internal Student Wallet Backed by an Append-Only Double-Entry Ledger

All monetary values are denominated in EGP integer **piasters** and recorded in an append-only double-entry ledger (`LedgerAccount`, `LedgerTransaction`, `LedgerEntry`) with no directly mutable balance columns. Students fund an internal **Wallet** via Paymob (cards, Egyptian mobile wallets, Fawry/Aman kiosks) or Admin-generated **Recharge Codes**, and all Purchases settle instantly and atomically from the Wallet.

## Considered Options

- **Direct per-purchase gateway checkout**: Forces students without bank cards through repeated Fawry/wallet flows for every single lecture and complicates partial or wallet-credit refunds.
- **Mutable balance column on `User` / `TeacherProfile`**: Faster to prototype, but fragile under concurrent requests, webhook retries, commission overrides, refunds, and payout audits.

## Consequences

- Online top-ups are confirmed exclusively via HMAC-verified Paymob webhooks (`PENDING → PAID | FAILED | EXPIRED`), making wallet funding idempotent and safe against client tampering.
- Teachers' net earnings are credited into a **pending** ledger bucket for a configurable window (default 7 days) before becoming **available** for monthly manual payout (bank, InstaPay, or mobile wallet).
- Manual Admin refunds (within 3 days and below the watch threshold) always return funds to the Student's Wallet rather than to cards, reversing the Teacher's pending earning and revoking the Entitlement in a single balanced ledger transaction.
- Recharge Code batches can be tagged to a Teacher for offline center tracking while keeping code issuance strictly Admin-controlled.
