# LinkedIn — texto do perfil

> Atualizado: 2026-09-14. Cada bloco abaixo corresponde a um campo do LinkedIn.
> Limites da plataforma: Headline 220 caracteres · About 2.600 · descrição de cada experiência 2.000.

---

## Headline (220 chars)

```
Full-Stack Developer · Python/FastAPI · TypeScript/React · Design Systems | Sole engineer on production systems for construction & healthcare | Ex-drone-show engineer (1,600 aircraft, 100k audiences) | Remote, UTC−3
```

## About

```
I'm a full-stack developer who ships production systems end to end: Python and TypeScript backends, React frontends, design systems, and the tests that keep them honest.

I came to software from live drone-show engineering. I directed 3D animation synchronized across fleets of up to 1,600 aircraft for audiences of 100,000, in a system where a bug is visible to a stadium. That background shaped how I build software: deterministic, tested, and owned in production.

What I've built since:

• Copesolo & Concresolo (2026–present) — sole engineer of the company-wide system for the largest foundation and geotechnical engineering firm in Northeast Brazil (~100 employees): production tracking, warehouse inventory, machinery control and HR. A WhatsApp automation inverted daily reporting so job sites report to the engineer and the system on their own. A two-regime payroll-bonus engine with row-level locking ensures concurrent requests can't pay the same work twice.

• FaturaMed (2026) — owned the entire web frontend of a medical revenue-recovery platform with paying customers: design tokens, light/dark themes, the shared component layer, data visualization, and the frontend testing environment.

• GBS Construtora (2025) — led the company's digital transformation as its sole engineer, designing and building a proprietary production-control system end to end.

• Refund (2026, open source) — the public one: a full-stack refund-management system with 11 architecture decision records, contract tests, Docker, CI and a live deploy. github.com/gabrieldborges/Refund-api

Stack: Python, FastAPI, SQLAlchemy, PostgreSQL · TypeScript, React, Next.js, Tailwind CSS, TanStack Query · Vitest, Playwright, pytest · Architecture decision records, pinned runtimes, generated API contracts.

Open to remote, contractor roles with US and European teams. Based in João Pessoa, Brazil (UTC−3, full overlap with US hours). English fluent.

Portfolio and CV: [link do site quando publicado]
```

## Experience

### Copesolo & Concresolo

| Campo | Valor |
|---|---|
| Title | Software Developer · Technology & Innovation Lead |
| Employment type | Full-time |
| Location | João Pessoa, Paraíba, Brazil · On-site/Hybrid |
| Start | Jan 2026 |
| End | Present |

```
Largest foundation and geotechnical engineering firm in Northeast Brazil (~100 employees). I own the company's technology and innovation area and am the sole engineer of its company-wide system.

• Built the system covering production tracking, warehouse inventory, machinery control and HR (employee and equipment documentation).
• Built a WhatsApp automation that inverted daily reporting: job sites now report to the site engineer and the system on their own, instead of her contacting every site each day. Production data became constant and reliable.
• Built a two-regime payroll-bonus engine (hourly and per-meter) with row-level locking at payroll close, so concurrent requests cannot pay the same work twice.
• Wrote the project's architecture decision records, pinned every runtime, and generated API contracts from the backend so client and server cannot drift apart.
• 66 backend tests (pytest), 46 frontend unit tests, 13 Playwright end-to-end suites; ARIA, keyboard navigation and screen-reader affordances throughout.

Stack: FastAPI, async SQLAlchemy, Alembic, Supabase Postgres, React, TypeScript, Tailwind CSS, Vitest, Playwright, WhatsApp API.
```

Skills a marcar nessa experiência: Python · FastAPI · PostgreSQL · React · TypeScript · Software Architecture

### FaturaMed

| Campo | Valor |
|---|---|
| Title | Frontend & Design System Engineer |
| Employment type | Freelance |
| Location | Remote (Brazil) |
| Start | Apr 2026 |
| End | Aug 2026 |

```
Medical revenue-recovery platform for doctors billing health insurers in Brazil. In production, with paying customers. The product reads insurer claim forms from photos and extracts structured data with AI.

• Owned the entire web frontend: built the design system from brand identity to shipped UI — design tokens, typography, light and dark themes, and the shared component layer every screen uses.
• Designed and built the responsive application shell: collapsible sidebar (icon rail on desktop, drawer on mobile), unified with the topbar by a single height token.
• Built the data-visualization layer (donut, funnel) on @nivo, legible down to phone widths; added TanStack Query caching and a persistent shell, replacing per-screen refetches with skeleton-driven loading states.
• Established the project's frontend testing environment (Vitest + Testing Library), including a test asserting password reset never reveals whether an account exists.

Stack: Next.js (App Router), React, TypeScript, Tailwind CSS, TanStack Query, @nivo, Vitest, Testing Library.
```

Skills: React · Next.js · TypeScript · Design Systems · Tailwind CSS

### GBS Construtora

| Campo | Valor |
|---|---|
| Title | Full-Stack Developer |
| Employment type | Freelance |
| Location | Remote (Brazil) |
| Start | Feb 2025 |
| End | Nov 2025 |

```
Led the company's digital transformation as its sole engineer: designed and built a proprietary, closed-source production-control system, end to end.

Stack: FastAPI, async SQLAlchemy, PostgreSQL, React, TypeScript, Tailwind CSS.
```

Skills: Python · FastAPI · React · PostgreSQL

### Alok

| Campo | Valor |
|---|---|
| Title | Drone Show Engineer |
| Employment type | Contract |
| Start | 2024 |
| End | 2026 |

```
• Directed and engineered live drone shows: 3D animation choreographed and synchronized across fleets of up to 1,600 aircraft, performed for live audiences of 100,000.
• Translated creative concepts into deterministic flight data — procedural design, timing, spatial constraints and physical execution in a system where a bug is visible to a stadium.
```

### Pixel Drone

| Campo | Valor |
|---|---|
| Title | Drone Show Engineer |
| Employment type | Contract |
| Start | 2024 |
| End | 2026 |

```
Built and validated show choreography for commercial drone productions, from 3D animation through flight-ready output.
```

### Damoda

| Campo | Valor |
|---|---|
| Title | 3D Technical Artist |
| Employment type | Contract |
| Location | Shenzhen, China · On-site |
| Start | 2024 |
| End | 2024 |

```
Three-month engagement with a Chinese drone-show manufacturer, working across the animation-to-hardware pipeline.
```

## Projects (seção "Projects" do LinkedIn)

| Campo | Valor |
|---|---|
| Name | Refund — full-stack refund-management system |
| Dates | Jul 2026 – Aug 2026 |
| URL | https://github.com/gabrieldborges/Refund-api |

```
Solo, open-source, deployed on Railway. FastAPI API with Clean Architecture governed by 11 architecture decision records (typed settings, Problem Details errors, structured logging, contract testing, abuse controls, orphan-file sweep, container); mocked and integration test suites against PostgreSQL 18 and MinIO; liveness/readiness split. React 19 + TypeScript + Tailwind 4 frontend with TanStack Query and component tests. CI on both repositories.
```

## Education

| Escola | Curso | Período |
|---|---|---|
| FIAP | Bachelor's, Software Engineering | 2024 – 2028 (expected) |
| Animation Mentor | Character Animation specialization | 2024 |
| Faculdade Méliès | 3D Animation & Design | 2022 – 2024 |

## Skills (Top 5 fixados, nessa ordem)

1. Python
2. TypeScript
3. React
4. FastAPI
5. PostgreSQL

Demais: Next.js · Tailwind CSS · SQLAlchemy · Design Systems · Software Architecture · Playwright · Vitest · Unreal Engine · Blender · Maya

## Languages

Portuguese — Native · English — Full professional proficiency · Spanish — Elementary

## Outros campos

- **Custom URL:** linkedin.com/in/gabriel3dborges (já é)
- **Location:** João Pessoa, Paraíba, Brazil
- **Open to work:** Software Developer, Full Stack Developer, Backend Developer, Frontend Developer · Remote · Contract e Full-time
- **Website no perfil:** o link do site quando publicado
