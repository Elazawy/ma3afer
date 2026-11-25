---
status: accepted
---

# 0005: Multi-Cloud Hosting Split Aligned with Recurring vs. One-Time Credits

Production infrastructure is placed strictly on **recurring** credits and free tiers—Cloudflare Workers (OpenNext) for `mo3afer.com` plus DNS/CDN/WAF, Heroku EU Basic dyno ($7/mo) + Postgres Essential-0 ($5/mo) for `api.mo3afer.com` (within the $13/mo recurring student credit), and GCP ($10/mo recurring) for off-site Postgres backups and Cloud Run fallback—while expiring one-time credits (Azure $100, GCP $80) are restricted to staging (`staging.mo3afer.com`) and load testing.

## Considered Options

- **Vercel Free for Next.js**: Rejected because Vercel's Hobby tier prohibits commercial use.
- **Heroku Eco dyno ($5) + Postgres ($5) + Key-Value Mini ($3)**: Rejected because Eco dynos sleep after 30 minutes of inactivity, causing 10+ second cold starts and risking **Paymob payment webhook timeouts** that leave paid top-ups unconfirmed.
- **Deploying production on Azure $100 or GCP $80 one-time credits**: Rejected because expiring one-time credits risk sudden production downtime and forced migration.
- **Splitting API and Postgres across different cloud providers**: Rejected because cross-cloud latency (20–50 ms per query) severely degrades multi-query API endpoints.

## Consequences

- **No Redis in MVP**: Running Basic dyno + Postgres Essential-0 leaves no room for Heroku Key-Value within the $13/mo budget. Background jobs (`pg-boss`), rate limiting, and light caching run on Postgres, which is sufficient for MVP scale and simpler to operate.
- **Cloudflare Workers Free constraints**: Free Workers enforce a 3 MiB compressed bundle limit and 10 ms CPU limit per request. Next.js SSR is therefore restricted to public SEO pages (home, catalog, teacher profiles, course pages), while authenticated dashboards and the video player render client-side, with bundle size checked in CI. If limits are still exceeded, `apps/web` moves to **GCP Cloud Run** (covered by the $10/mo recurring credit) or Workers Paid ($5/mo).
- **Heroku Essential-0 limits**: 1 GB storage and 20 connections require disciplined connection pooling (Prisma + `pg` pool sizing) and keeping media strictly off Postgres/Heroku.
- **Compliance check**: Before public commercial launch, verify commercial-use terms on the Heroku-for-Students and Azure-for-Students credits and upgrade to standard billing if required.
