# Hi, I'm Jesús Murúa 👋

**Senior Full-Stack Developer & UI/UX** based in Hermosillo, Mexico.
10 years building enterprise systems and SaaS products — backend, frontend, and design, end to end.

---

## What I'm building right now

### FINO — a point of sale that starts on a phone and grows with the business

A multi-tenant SaaS POS for small and mid-size businesses in Mexico, built from scratch as sole
developer. Four commerce engines on one codebase — **quick service, full-service restaurants,
retail, and services** (memberships, appointments, access control) — configured per business type,
so the same product fits a food counter, a store, a gym or a salon without a custom build.

Designed to be adopted with zero upfront investment: it runs on the phone the owner already has,
keeps selling offline and syncs when connectivity returns, and scales on the same system — more
devices, a kitchen display, a kiosk, additional branches — without migrating. Product setup is meant
to need no training: every configuration flow is measured in taps and seconds against production,
and those numbers are tracked so they only go down.

- **Landing:** [finomx-landing.vercel.app](https://finomx-landing.vercel.app)
- **App:** [fino-mx.vercel.app](https://fino-mx.vercel.app)

<p align="center">
  <img src="assets/fino-pos.gif" width="300" alt="FINO point of sale on a phone: pick two products, choose a size, charge, change due — nine seconds">
</p>

**Point of sale**
- Offline-first PWA — sales keep flowing through outages (Dexie.js + Angular Signals), then sync
- A counter model that survives real streets: device → register → cash drawer → shift, so three
  phones on one drawer count the money once; blind cash count; PIN as the shift key
- Split payments, held orders, kitchen display (KDS), waiter mode, table map with reservations,
  kiosk self-service — seven device modes on the same codebase, SignalR for the real-time parts
- Promotions engine (percentage, fixed, buy-X-get-Y, bundles, coupons), volume pricing, loyalty points

**Inventory that calibrates itself**
- Recipes per product *and per size*: the large serving consumes 80 ml, the small one 40 — one
  table, no duplicated modifier groups
- Production runs with yield, purchase unit vs. consumption unit (buy by kilo, consume by gram),
  cost rates with decimals so cheap bulk goods never cost "0"
- The end-of-shift close asks up to three inventory questions (blind, seconds each), records the
  count, and after five counts **proposes** a recipe correction with the evidence — accept in one
  tap, undo any time
- Reorder alerts in days ("runs out Thursday — prepare 800 ml tomorrow"), not in pieces

**Money & tenants**
- Multi-tenant isolation through EF Core global query filters, scoped from the JWT
- SaaS billing with four doors: complimentary (with an end date), manual rails (bank transfer /
  cash, with grace period and automatic block/unblock on payment), Stripe & OXXO Pay, and free —
  one state machine for all of them
- Card terminals and webhooks: Stripe, MercadoPago, Clip · Delivery webhooks: Uber Eats, Rappi, DiDi Food
- Business-type modules: QR access control, memberships, appointments, work orders, commissions,
  supplier returns, inter-warehouse transfers, Excel product import with preview
- A separate operations console (tenants, subscriptions, invoices, feature matrix, impersonation)

**Hardware**
- Thermal printing two ways: Web Bluetooth straight from the browser, and a Windows bridge
  service (.NET 8, ESC/POS over USB/serial) for the counter PC that already exists
- Barcode scanners, cash drawer kick, Web Push notifications (VAPID)

**How it's engineered**
- Six repositories (API, POS app, operations console, landing, Windows bridge, shared contracts)
  with **contract fixtures run by both sides**: a rule that must live in two repos is written once
  as JSON and asserted by both test suites
- **3,784 API integration tests against a real PostgreSQL** (no mocked repositories),
  3,657 Angular specs in the app + 290 in the console, 35 Playwright end-to-end flows against an
  ephemeral API, 485 tests over the shared gates
- **28 cross-repo gates and ratchets**, each answering one question about the tree (does every API
  route have a caller? does every generated copy match its source? was a query written twice?) —
  measured debt can only go down, and a finding closes with a machine, never with a document
- **Mutation testing on the money path**: 22 declared regions of the sync engine are each mutated
  and run against the whole suite; a region nobody notices is a finding
- Protected `main`, PR-only, CI on self-hosted runners, deploys verified by commit against
  `/api/health`; zero `npm audit` advisories after the Angular 22 / PrimeNG 22 major
- Complete UI/UX and brand identity from scratch; every product change ends with a walkthrough on
  production, counting taps

**Tech stack:**
```
Backend   │ .NET 10 · ASP.NET Core · EF Core · PostgreSQL (Supabase) · SignalR · Clean Architecture
Frontend  │ Angular 22 · PrimeNG 22 · TypeScript 6 · Angular Signals · Dexie.js (offline-first PWA)
Landing   │ Next.js 16
Hardware  │ Web Bluetooth · ESC/POS · .NET 8 Windows bridge · Web Push
Infra     │ Vercel · Render · Supabase · GitHub Actions (self-hosted runners)
Payments  │ Stripe · OXXO Pay · MercadoPago · Clip
Delivery  │ Uber Eats · Rappi · DiDi Food
Testing   │ xUnit + real PostgreSQL · Karma · Playwright · Vitest · contract fixtures · mutation probe
```

---

## Previous work — Xemble Technologies (2021–2026)

### CleanPRO — Enterprise Facility Management for CBRE
Government and commercial clients: hospitals, military bases, schools, office buildings.
Stack: .NET 9 · Angular 18 · SQL Server · Azure

**Key achievements:**

- **97% performance improvement** — Diagnosed and resolved BUG-5900: floor care plan generation went from ~1 hour to ~2 minutes for datasets of 3,597+ rooms by redesigning the in-memory object generation strategy, eliminating catastrophic Gen2 garbage collection pauses that were the actual bottleneck (not I/O)
- **40% reduction in production data payloads** — Replaced full entity eager-loading with targeted projections across critical endpoints
- **Floor Care Planner** — Designed the complete UX mockup from scratch, then led the full implementation: complex reschedule logic (by date, by team, by shift), team capacity algorithms, holiday-aware task regeneration, real-time polling
- **Legacy migration** — Led the full migration from outdated .NET and Angular versions to .NET 9 + Angular 18, establishing coding standards and CI/CD pipeline adopted by the team
- **Azure Document Intelligence** — Integrated Form Recognizer + OCR to automate data extraction from scanned field forms, with confidence-threshold validation for human-in-the-loop review
- **i18n** — Full internationalization across 8+ modules (facilities, floor care, area assignment, access control, quality control, service insight)
- **UI/UX modernization** — Redesigned legacy screens to enterprise-grade interfaces with consistent design system, responsive layouts, and accessibility improvements
- Mentored junior developers on backend and frontend

---

## Tech I work with

```
Backend     │ C# · .NET 8/9/10 · EF Core · SQL Server · PostgreSQL · REST APIs · SignalR
Frontend    │ Angular 22 · TypeScript 6 · PrimeNG · RxJS · Signals · PWA · Next.js
Cloud       │ Azure · Azure DevOps · Form Recognizer · Vercel · Render · Supabase · GitHub Actions
Quality     │ Integration tests on real databases · Playwright · contract testing · mutation testing · ratchets & gates
Patterns    │ Clean Architecture · Repository Pattern · Unit of Work · DDD · offline-first sync
Hardware    │ Web Bluetooth · ESC/POS · Web Push API · Barcode scanners
```

---

## Certifications

- Angular Intermediate & Basic — HackerRank (2026)
- C#, ASP.NET, MSSQL, Angular, JavaScript — Verified by Talently (2024)

---

## Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Jesus%20Murua-0077B5?style=flat&logo=linkedin)](https://www.linkedin.com/in/jesus-murua)
[![Email](https://img.shields.io/badge/Email-jesusmuruar%40gmail.com-D14836?style=flat&logo=gmail)](mailto:jesusmuruar@gmail.com)
