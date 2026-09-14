# Timeline — Gabriel Dantas

> **Atualizado:** 2026-09-14
> **Para que serve:** fonte única do conteúdo da timeline do site e do currículo. Se um fato
> mudar, muda aqui primeiro; site e CV copiam daqui.
> **Idioma:** o conteúdo é em inglês (idioma do site e do CV). Cada entrada termina com uma
> nota em português dizendo o que ficou de fora e por quê.

**Alvo:** Full-Stack Developer, remoto, empresas estrangeiras.
**Regra:** vender escopo e responsabilidade, nunca volume. Sem contagem de commits ou linhas.

---

## 2024 — Damoda

**3D Technical Artist** · Shenzhen, China · 3-month engagement

- Three-month engagement with a Chinese drone-show manufacturer, working across the
  animation-to-hardware pipeline.

**Stack:** Maya, Blender, proprietary flight tooling.

> **Nota PT.** É a entrada mais curta e mais antiga. Está aqui porque abre a timeline e
> explica de onde vem o "olho de 3D". Não precisa crescer.

---

## 2024 – 2026 — Alok

**Drone Show Engineer**

- Directed and engineered live drone shows: 3D animation choreographed and synchronized
  across fleets of up to 1,600 aircraft, performed for live audiences of 100,000.
- Translated creative concepts into deterministic flight data — procedural design, timing,
  spatial constraints and physical execution in a system where a bug is visible to a stadium.

**Stack:** Unreal Engine, Blender, Maya, procedural animation.

> **Nota PT.** O maior número da timeline (1.600 aeronaves, 100 mil pessoas). Mantido porque
> é o feito mais memorável e é escopo, não volume. Datas ficam só em ano por decisão sua.

---

## 2024 – 2026 — Pixel Drone

**Drone Show Engineer**

- Built and validated show choreography for commercial drone productions, from 3D animation
  through flight-ready output.

> **Nota PT.** Cargo formal ainda não confirmado (assumido Drone Show Engineer). Sobrepõe
> com Alok e com a GBS no tempo, o que é normal para freelance.

---

## Feb 2025 – Nov 2025 — GBS Construtora

**Full-Stack Developer** · freelance · remote (Brazil)

- Led the company's digital transformation as its sole engineer: designed and built a
  proprietary, closed-source production-control system, end to end.
- FastAPI + async SQLAlchemy on PostgreSQL; React + TypeScript + Tailwind frontend.

**Stack:** FastAPI, SQLAlchemy, PostgreSQL, React, TypeScript, Tailwind CSS.

> **Nota PT.** Primeira entrada de software da timeline. É o que prova que o rótulo
> "full-stack" já existia antes da Copesolo. Fica em duas linhas porque o sistema é fechado e
> não há o que mostrar publicamente. Se você tiver um número (usuários, obras, tempo até
> produção), vale adicionar.

---

## Jan 2026 – Present — Copesolo & Concresolo

**Software Developer · Technology & Innovation Lead** · employee · João Pessoa, Brazil

*Largest foundation and geotechnical engineering firm in Northeast Brazil (~100 employees).*

- Own the company's technology and innovation area. Sole engineer of the company-wide
  system covering production tracking, warehouse inventory, machinery control and HR
  (employee and equipment documentation).
- Built a WhatsApp automation that inverted daily reporting: job sites now report to the
  site engineer and the system on their own, instead of her contacting every site each day.
  Production data became constant and reliable.
- Built a two-regime payroll-bonus engine (hourly and per-meter) with row-level locking at
  payroll close, so concurrent requests cannot pay the same work twice.
- Wrote the architecture decision records the project runs on, pinned every runtime (Node,
  Python, Postgres), and generated API contracts from the backend so client and server
  cannot drift apart silently.
- 66 backend tests (pytest), 46 frontend unit tests, 13 Playwright end-to-end suites; ARIA,
  keyboard navigation and screen-reader affordances throughout.

**Stack:** FastAPI, async SQLAlchemy, Alembic, Supabase Postgres, React, TypeScript,
Tailwind CSS, Vitest, Playwright, WhatsApp API.

> **Nota PT.** Entrada principal. Título em inglês é sugestão; alternativa mais modesta:
> "Full-Stack Developer, Technology & Innovation". A contagem de testes fica porque é
> escopo de qualidade, não volume de código. Na spec de agosto, a Copesolo aparecia como
> cliente da GS3 Motion; agora é cargo interno, conforme você descreveu.

---

## Apr 2026 – Aug 2026 — FaturaMed

**Frontend & Design System Engineer** · freelance · remote (Brazil)

*Medical revenue-recovery platform for doctors billing health insurers in Brazil. In
production, with paying customers. The product reads insurer claim forms from photos and
extracts structured data with AI.*

- Owned the entire web frontend: built the design system from brand identity to shipped UI
  — design tokens, typography, light and dark themes, and the shared component layer every
  screen uses.
- Designed and built the responsive application shell: collapsible sidebar (icon rail on
  desktop, drawer on mobile), unified with the topbar by a single height token.
- Built the data-visualization layer (donut, funnel) on @nivo, legible down to phone widths;
  added TanStack Query caching and a persistent shell, replacing per-screen refetches with
  skeleton-driven loading states.
- Established the project's frontend testing environment (Vitest + Testing Library),
  including a test asserting password reset never reveals whether an account exists.

**Stack:** Next.js (App Router), React, TypeScript, Tailwind CSS, TanStack Query, @nivo,
Vitest, Testing Library.

> **Nota PT.** A leitura de guias por IA é do sócio (Igor, backend). Ela aparece como
> descrição do produto, não como bullet seu, para não virar pergunta de entrevista que você
> não consegue responder. Você assina a interface inteira, e isso é dito com "owned the
> entire web frontend".

---

## Jul 2026 – Aug 2026 — Refund (open source)

**Full-stack refund-management system** · solo · public on GitHub · deployed on Railway

- API in FastAPI with Clean Architecture, governed by 11 architecture decision records:
  layered API, typed settings that refuse to boot on bad config, Problem Details errors,
  structured logging, contract testing, coverage, abuse controls, orphan-file sweep, container.
- Two test suites: a fast mocked one that proves the repositories build the right SQL, and
  an integration one against PostgreSQL 18 and MinIO.
- Liveness and readiness split on purpose, so a database outage stops traffic instead of
  restarting every instance in a loop.
- React 19 frontend with TanStack Query, component tests for the shell, theme and
  reduced-motion, and CI on both repositories.

**Links:** github.com/gabrieldborges/Refund-api · github.com/gabrieldborges/Refund ·
independent-fascination-production-feea.up.railway.app

**Stack:** FastAPI, SQLAlchemy, PostgreSQL, S3, Docker, pytest, React 19, TypeScript, Vitest,
GitHub Actions.

> **Nota PT.** Descoberto em 14/09/2026 ao revisar o GitHub: é o único código público que
> prova as práticas atribuídas ao Copesolo. Entra no site (capítulo 05), no currículo (seção
> Open Source) e no README de perfil. READMEs dos dois repos foram traduzidos para inglês.

---

## Ordem de exibição

- **Site (timeline):** cronológica, do Damoda (2024) até a Copesolo (hoje).
- **Currículo:** do mais recente ao mais antigo: Copesolo → FaturaMed → GBS → Alok →
  Pixel Drone → Damoda; Refund em seção própria "Open Source".

## Pendências de fato

- [ ] Cargo formal na Pixel Drone
- [ ] Período da Faculdade Méliès (2022–2024 é dedução)
- [ ] Algum número da GBS (obras, usuários, tempo até produção)
- [ ] Título final em inglês na Copesolo
