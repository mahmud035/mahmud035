<h1 align="center">Md. Mahamudul Hasan Pavel</h1>

<p align="center">AI-native Full-Stack Developer &nbsp;·&nbsp; React · TypeScript · Node · MongoDB</p>

<p align="center">
  <a href="https://mahamudulhasan.vercel.app/"><img src="https://img.shields.io/badge/Portfolio-1D4ED8?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio" /></a>
  <a href="https://www.linkedin.com/in/mahmud035/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="https://drive.google.com/file/d/1XUTioVsxcvO6owju9ZU1BeOAOqpSm4kj/view"><img src="https://img.shields.io/badge/Resume-111827?style=for-the-badge&logo=readdotcv&logoColor=white" alt="Resume" /></a>
  <a href="mailto:mahamudulhasan4148@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <a href="https://x.com/MHPAVEL19"><img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" alt="X" /></a>
</p>

---

## About

Full-stack developer with **2+ years building and shipping production-grade, type-safe web applications** — I architect, build, and operate a live UK e-commerce platform end to end, solo. I care about clean feature-driven architecture, API contracts that break TypeScript at compile time (not runtime), and payment systems resilient enough to survive a forced processor migration with zero downtime.

- **Currently building:** an AI support/knowledge SaaS (RAG over MongoDB Atlas Vector Search + Gemini) and a real-time live-auction platform (Socket.io + Redis)
- **Focus:** React 19 · TypeScript · RAG pipelines · real-time systems · payment architecture
- **Open to:** full-stack roles (local + remote) and freelance work

---

## Featured Projects

### [Halal Aura](https://halalaura.co.uk) — Premium Halal Fragrance E-Commerce (UK)

`React 19` · `TypeScript` · `Node` · `Express 5` · `MongoDB` · `TanStack Query v5` · `Tailwind v4` · `Square` · `Vercel` · `Railway`

- **Architected a provider-agnostic payment layer** that absorbed two processor migrations (Stripe → Mollie → Square) with zero schema changes, containing a forced shutdown to a 4-day driver swap — storefront never down.
- **Built and operate the entire three-service platform solo** — an Express / MongoDB API plus a React storefront and admin dashboard — with subdomain-scoped HTTP-only-cookie auth, guest checkout, and real production orders.
- **Engineered idempotent payment processing** with retrying MongoDB transactions, an in-transaction PAID re-check, and a send-then-mark email pattern to prevent duplicate charges and confirmation emails under webhook replay.
- **Enforced a feature-driven architecture** across all three codebases with frontend types mirroring API responses, so any contract change breaks at TypeScript compile time rather than in production.
- **Achieved Lighthouse Accessibility 100, SEO 100, Best Practices 100** across storefront routes, with desktop Core Web Vitals in Google's "Good" range (LCP 1.94s, INP 88ms, CLS 0.04).

**[Live →](https://halalaura.co.uk)** &nbsp;·&nbsp; **[Case Study →](https://github.com/mahmud035/halal-aura)** _(case study — source private)_

### [রাঁধুনি (Recipe-Note)](https://recipe-note-app.vercel.app) — AI Recipe Extractor

`React 19` · `TypeScript` · `Google Gemini` · `Express 5` · `Mongoose` · `Zod` · `Docker` · `GitHub Actions`

- **Shipped a full-stack AI app end-to-end** — React + Express / MongoDB API — that turns Bengali YouTube cooking videos into editable, structured recipes via Google Gemini, for a real non-technical user on a $0 inference budget.
- **Designed a fault-tolerant asynchronous job pipeline** (fire-and-forget + client polling) with wall-clock timeouts, status-gated race guards, and startup orphan-recovery, so a hung or rate-limited AI call can never crash the server.
- **Anchored the system on a single Zod schema serving four consumers** (AI response, Mongoose model, API envelope, and client type), so backend changes break the frontend at compile time, not runtime.
- **Owned split-origin deployment:** multi-stage Docker image → GitHub Actions → GHCR → self-hosted box behind a Cloudflare Tunnel, with auto-deploying CI/CD, an atomic daily-budget guard, and per-IP rate limiting.

**[Live →](https://recipe-note-app.vercel.app)** &nbsp;·&nbsp; **[Code →](https://github.com/mahmud035/recipe-note)** &nbsp;·&nbsp; **[Infra Docs →](https://github.com/mahmud035/devops-lab)**

### [Mini ERP](https://mini-erp-client-app.vercel.app) — Role-Based Inventory & Sales Management

`React 19` · `TypeScript` · `Express 5` · `MongoDB` · `TanStack Query v5` · `Socket.IO` · `Zod` · `Tailwind v4` · `Vercel` · `Railway`

- **Engineered a fully DB-driven RBAC layer** resolved per request behind a single authorization guard with zero hardcoded role names, so editing a role's permission set takes effect on the user's next request — no re-login, no redeploy.
- **Made multi-line sales transactional and race-safe** with a Mongoose session and a guarded atomic stock decrement per line item, so two sales racing for the last unit resolve all-or-nothing with server-computed totals — a failed line rolls the entire sale back, never a phantom decrement.
- **Solved first-party cookie auth across two different-origin deployments** (Vercel + Railway) with a same-origin `/api/*` proxy and a single-flight refresh interceptor that queues concurrent 401s and replays each once — then authenticated the WebSocket, which can't ride that proxy, with an in-memory access token: one auth model, two transports.
- **Delivered real-time low-stock alerts over Socket.IO** scoped to a permission-gated room only `product:update` holders join, with the broadcast isolated from the committing sale transaction so a socket failure can never delay or roll back a sale.

**[Live →](https://mini-erp-client-app.vercel.app)** &nbsp;·&nbsp; **[Code →](https://github.com/mahmud035/mini-erp-client)**

### [Aston CS Research Portal](https://aston-cs-research-portal.vercel.app/) — Research Discovery Platform

`React 19` · `TypeScript` · `Express 5` · `MongoDB` · `TanStack Query v5` · `Zod`

- **Modeled co-authorship as an interactive force-directed collaboration graph** over a computed aggregation — deduping mirror author-pairs by a sorted canonical key and weighting each edge by shared-publication count.
- **Structured a feature-driven full-stack architecture** mirroring frontend features 1:1 to backend modules with a shared typed API contract, so any response-shape change breaks TypeScript at compile time, not runtime.
- **Wired debounced keyword search** spanning faculty and publications in a single round-trip, with case-insensitive backend matching, Zod-validated params, and highlighted matches showing why each result surfaced.

**[Live →](https://aston-cs-research-portal.vercel.app/)** &nbsp;·&nbsp; **[Code →](https://github.com/mahmud035/aston-cs-research-portal)**

> More shipped work, live demos, and case studies on my **[portfolio →](https://mahamudulhasan.vercel.app/)**

---

## Tech Stack

**What I use**

- **Frontend:** React 19 · TypeScript · Tailwind CSS v4 · TanStack Query v5 · React Hook Form · Axios · Vite · Motion
- **Backend:** Node.js · Express 5 · MongoDB · Mongoose · REST APIs · JWT (HTTP-only cookies) · Zod
- **Payments / Media / AI:** Square · Stripe · Mollie · Cloudinary · Google Gemini
- **DevOps & Tools:** Docker · GitHub Actions (CI/CD) · Git · Vercel · Railway · Postman · Figma · Linux
- **Testing:** Vitest · React Testing Library

**Also worked with:** PostgreSQL · Prisma · Python · Firebase · Supabase

---

## GitHub Stats

<p align="center">
  <img height="145" src="https://github-readme-stats-mahmud035.vercel.app/api?username=mahmud035&show_icons=true&theme=tokyonight&count_private=true&hide=contribs&hide_border=true" alt="Md. Mahamudul Hasan Pavel's GitHub stats" />
  <img height="145" src="https://streak-stats.demolab.com?user=mahmud035&theme=tokyonight&hide_border=true" alt="GitHub streak" />
</p>

<!-- <p align="center">
  <img src="https://github-readme-stats-mahmud035.vercel.app/api/top-langs/?username=mahmud035&langs_count=10&layout=compact&theme=tokyonight&hide_border=true" alt="Most used languages" />
</p> -->

<p align="center">
  <img src="https://github-stats-extended.vercel.app/api/top-langs?username=mahmud035&layout=compact&langs_count=10&theme=tokyonight&hide_border=true" alt="Most used languages" />
</p>
