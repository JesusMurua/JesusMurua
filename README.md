# Hi, I'm Jesús Murúa 👋

**Senior Full-Stack Developer & UI/UX** based in Hermosillo, Mexico.
10 years building enterprise systems and SaaS products — backend, frontend, and design, end to end.

---

## What I'm building right now

### FINO — Smart POS for Mexican Small Businesses
A multi-tenant SaaS point-of-sale platform built from scratch as sole developer.
One system that adapts to any business type: restaurants, retail, food trucks, cafés, and more.

- **Landing:** [finomx-landing.vercel.app](https://finomx-landing.vercel.app)
- **App:** [fino-mx.vercel.app](https://fino-mx.vercel.app)

**What I built:**
- Offline-first PWA — POS keeps working through internet outages (Dexie.js + Angular Signals)
- Multi-tenant architecture with JWT-scoped tenant isolation
- Real-time table management with kitchen status and reservation integration
- Split payments, cash register sessions, role-based device modes (cashier / kitchen / tables / kiosk)
- Push notifications via Web Push API (VAPID)
- Bluetooth thermal printer support (WebUSB)
- Barcode scanner integration
- Excel product import with preview and validation
- Promotions engine (percentage, fixed, BOGO, bundles, coupons)
- Full reservation system with availability checks
- Delivery platform webhooks — Uber Eats, Rappi, DidiFood
- Stripe subscription billing with webhook lifecycle management
- Facturapi integration for CFDI 4.0 electronic invoicing (Mexican tax law)
- Complete UI/UX design and brand identity from scratch

**Tech stack:**
```
Backend   │ .NET 10 · ASP.NET Core · EF Core · PostgreSQL · Clean Architecture
Frontend  │ Angular 18 · PrimeNG · Dexie.js (offline-first PWA) · Angular Signals
Infra     │ Vercel · Render · Supabase
Payments  │ Stripe · Facturapi · MercadoPago · Clip
Delivery  │ Uber Eats · Rappi · DidiFood
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
Backend     │ C# · .NET 9/10 · EF Core · SQL Server · PostgreSQL · REST APIs
Frontend    │ Angular 18 · TypeScript · PrimeNG · RxJS · PWA · Signals
Cloud       │ Azure · Azure DevOps · Form Recognizer · Vercel · Render
Patterns    │ Clean Architecture · Repository Pattern · Unit of Work · DDD
Hardware    │ WebUSB (thermal printers) · Web Push API · Barcode scanners
```

---

## Certifications

- Angular Intermediate & Basic — HackerRank (2026)
- C#, ASP.NET, MSSQL, Angular, JavaScript — Verified by Talently (2024)

---

## Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Jesus%20Murua-0077B5?style=flat&logo=linkedin)](https://www.linkedin.com/in/jesus-murua)
[![Email](https://img.shields.io/badge/Email-jesusmuruar%40gmail.com-D14836?style=flat&logo=gmail)](mailto:jesusmuruar@gmail.com)
