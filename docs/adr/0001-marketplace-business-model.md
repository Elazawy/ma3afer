---
status: accepted
---

# 0001: Marketplace Business Model with Per-Lecture, Package, and Content Code Sales

Ma3afer operates as an open teacher marketplace where independent teachers set prices for individual Lectures and teacher-curated Packages, and the platform retains a configurable commission (global default with per-teacher overrides). This matches how Egyptian General Secondary students follow individual teachers ("مستر") and pay per lecture or per month, and allows many teachers to onboard without upfront salary risk.

## Considered Options

- **Platform-wide subscription**: Students pay one monthly fee for all teachers, who are paid salaries or watch-time shares. Rejected because top Egyptian teachers expect direct pricing control and students typically follow one preferred teacher per subject rather than browsing a catalog like Netflix.
- **Hybrid (subscription + premium courses)**: Rejected for MVP due to revenue-split complexity and unclear positioning.
- **Time-based 30-day subscriptions for monthly packages**: Rejected in favor of Teacher-defined Packages grouping specific Lectures, which unifies "monthly packages" (e.g., November lectures) and revision bundles under one mechanism and avoids prorating or recurring billing failures.

## Consequences

- Teachers also sell offline in physical centers, so the model includes Teacher-generated **Content Codes** that unlock a Lecture or Package directly. Because Ma3afer never collects the student's cash on Content Codes, the platform deducts its commission upfront (from available earnings or prepaid credit) when the Teacher generates the batch.
- Buying a Package grants an Entitlement to the Package itself (not a frozen lecture list): adding lectures to a Package grants them to existing buyers, while removing a lecture from a Package with existing sales is blocked.
- Purchasing a Package when the Student already owns some of its Lectures charges full price (with a clear warning); automatic overlap discounting is deferred post-MVP to keep commission and refund accounting simple.
- Ratings and reviews are excluded from the MVP to avoid early manipulation and abuse.
