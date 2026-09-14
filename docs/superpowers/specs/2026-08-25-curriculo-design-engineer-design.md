# Currículo em inglês — Gabriel Dantas (Design Engineer)

> **Data:** 2026-08-25
> **Objetivo:** conteúdo do currículo em inglês para aplicar em vagas remotas de empresas
> estrangeiras, e base para o site-portfólio que vem depois.

---

## 1. Posicionamento

**Alvo:** Design Engineer / Product Engineer.
**Diferencial de assinatura:** background em 3D e engenharia de shows de drone.
**Modelo de contratação:** contractor remoto (não visto/relocação).

### Por que esse alvo

O mercado de frontend em 2026 está partido em dois. "Developer" — traduzir design em
componente — está sob pressão direta de ferramentas de IA e paga US$115–160k. "Engineer" —
arquitetura, performance e **ownership de design system** — paga US$170–260k e continua
contratando. A evidência de produção do Gabriel cai inteira do lado "Engineer".

O nicho creative/WebGL foi considerado e descartado como *primeiro* alvo: a ordem de
grandeza é de dezenas de vagas abertas globalmente, a média americana é US$58/h (abaixo de
um design engineer de produto), e o ingresso é um portfólio nível Awwwards que leva meses.
Ótimo diferencial, péssimo ponto de partida.

O funil nearshore LatAm está em alta forte (70% das empresas de tecnologia americanas já
contratam na região), mas procura senioridade — entrar como "júnior full-stack genérico"
significa competir com ~800 mil devs brasileiros no pior terreno possível. Daí a
necessidade de um rótulo específico.

### Lacuna conhecida

**Zero código WebGL/Three.js no browser.** O lado criativo vive em Unreal, Maya, Blender e
nos shows — ferramentas de artista, não código que um recrutador abre. O site-portfólio é a
peça que fecha essa lacuna.

### Regra de honestidade

Vender **escopo e responsabilidade, nunca volume**. Nada de "127 mil linhas" ou
"252 commits": o desenvolvimento é assistido por IA, e o número vira armadilha na entrevista.
"Sole engineer on a production system" é verdade, é defensável e impressiona mais.

---

## 2. Evidência verificada (autoria conferida no git)

| Projeto | Contribuição real |
|---|---|
| **FaturaMed / RecebeMed** | 49 de 162 commits, **100% em `apps/web`**. Gabriel é o design engineer/frontend; o sócio Igor é o backend. Em produção, clientes pagantes. |
| **Copesolo / Concresolo** | **252 de 252 commits — sozinho, full-stack.** Cliente: maior empresa de fundação e geotécnica do Nordeste; sistema para ~100 funcionários. |

O `CODING_PROFILE.md` de julho/2026 apontava lacunas (sem testes de frontend, sem a11y, sem
otimização React) que **já foram fechadas** — o documento está desatualizado a favor dele.

**Problema aberto:** o GitHub público (`gabrieldborges`) mostra só CRUDs de estudo
(`jwt`, `mongoDb`, `redis`, `mvc_pets_api`, `User-Authenticator`, `FastAPI`). Os dois sistemas
fortes são privados ou vivem na conta do sócio. O site-portfólio precisa carregar os case studies.

---

## 3. Formato

Uma página, ATS-friendly: sem colunas exóticas, sem ícones no lugar de texto, sem tabelas de
layout. Inglês americano. O PDF passa pelo filtro; o site carrega a profundidade.

---

## 4. Conteúdo final do currículo

### Header

```
GABRIEL DANTAS
Design Engineer · Product UI, Design Systems & Real-Time 3D
João Pessoa, Brazil (UTC−3 — full overlap with US hours)
gabrieldantas1404@icloud.com · +55 83 99130-6309
linkedin.com/in/gabriel3dborges · github.com/gabrieldborges · [portfolio]
```

> O `UTC−3 — full overlap with US hours` responde, no header, a objeção número um de quem
> contrata fora do país.

### Summary

> Design engineer who ships product interfaces end to end — design systems, responsive
> shells, data visualization, and the tests that keep them honest. I came to software from
> live drone-show engineering, directing 3D animation synchronized across fleets of up to
> 1,600 aircraft for audiences of 100,000. Founder of GS3 Motion, a software studio with
> products in production for paying customers.

### Experience

**GS3 Motion — Founder & Design Engineer** · Nov 2024 – Present · Remote (Brazil)
*Software studio building production systems for healthcare and construction clients.*

**FaturaMed** — medical revenue-recovery platform for doctors (in production, paying customers)

- Own the entire web frontend: built the design system from brand identity to shipped UI —
  design tokens, typography, light and dark themes, and the shared component layer every
  screen uses.
- Designed and built the responsive application shell — collapsible sidebar (icon rail on
  desktop, drawer on mobile), unified with the topbar by a single height token.
- Built the data-visualization layer (donut, funnel) on @nivo, legible down to phone widths;
  added TanStack Query caching and a persistent shell, replacing per-screen refetches with
  skeleton-driven loading states.
- Established the project's frontend testing environment (Vitest + Testing Library),
  including a test asserting password reset never reveals whether an account exists.

**Copesolo** — production tracking and payroll-bonus system for the largest foundation and
geotechnical engineering firm in Northeast Brazil (~100 employees)

- Sole engineer, full stack: FastAPI + async SQLAlchemy + Alembic on Supabase Postgres;
  React + TypeScript + Tailwind frontend.
- Built a two-regime bonus engine (hourly and per-meter) with row-level locking at payroll
  close, so concurrent requests cannot pay the same work twice.
- Wrote the architecture decision records the project runs on, pinned every runtime (Node,
  Python, Postgres), and generated API contracts from the backend so client and server
  cannot drift apart silently.
- 66 backend tests (pytest), 46 frontend unit tests, 13 Playwright end-to-end suites; ARIA,
  keyboard navigation and screen-reader affordances throughout.

**Alok — Drone Show Engineer** · 2024 – 2026

- Directed and engineered live drone shows: 3D animation choreographed and synchronized
  across fleets of up to 1,600 aircraft, performed for live audiences of 100,000.
- Translated creative concepts into deterministic flight data — procedural design, timing,
  spatial constraints and physical execution in a system where a bug is visible to a stadium.

**Pixel Drone — Drone Show Engineer** · 2024 – 2026

- Built and validated show choreography for commercial drone productions, from 3D animation
  through flight-ready output.

**Damoda — 3D Technical Artist** · Shenzhen, China · 2024

- Three-month engagement with a Chinese drone-show manufacturer, working across the
  animation-to-hardware pipeline.

### Technical Skills

```
Design Engineering  design systems, design tokens, theming (light/dark), responsive layout,
                    data visualization, accessibility (ARIA, keyboard, screen readers)
Frontend            TypeScript, React, Next.js (App Router), Tailwind CSS, TanStack Query,
                    React Hook Form + Zod, Radix UI, Vite
Backend             NestJS, FastAPI, SQLAlchemy, Prisma, PostgreSQL, Redis/BullMQ, S3, REST
Testing & Quality   Vitest, Testing Library, Playwright, pytest, architecture decision
                    records, pinned runtimes
AI-Assisted Eng.    Anthropic Claude SDK (vision OCR, structured extraction),
                    AI-driven development workflows
3D & Real-Time      Unreal Engine, Blender, Maya, procedural animation, drone choreography
```

### Education

```
FIAP                 B.Sc. Software Engineering · 2024 – 2028 (expected)
Animation Mentor     Character Animation specialization · USA · 2024
Faculdade Méliès     3D Animation & Design · 2022 – 2024
```

### Languages

Portuguese (native) · English (fluent) · Spanish (beginner)

---

## 5. O que fica de fora do CV e vai para o site

- **Case study do FaturaMed:** o design system inteiro — da identidade aos tokens, do tema
  dark ao shell responsivo. Antes/depois das telas.
- **Case study do Copesolo:** ownership solo, os 5 ADRs, o motor de bonificação e a trava de
  linha, a pirâmide de testes.
- **Duração do FaturaMed:** de zero a produção com clientes pagantes em menos de dois meses.
  Forte demais para o papel (soa a "produto minúsculo"), ótimo para conversa.
- **Reel de drone shows:** vídeo do show de 100.000 pessoas.
- **Uma cena WebGL/Three.js**, contida — a peça que fecha a lacuna de creative coding.

---

## 6. Caminho de melhoria acordado

**Fase 1 — destrava candidaturas (4–8 semanas)**
1. Site-portfólio como peça de design engineering, com *uma* cena WebGL contida.
2. Os dois case studies escritos.
3. Inglês técnico falado — explicar arquitetura ao vivo é o gargalo real.

**Fase 2 — sobe o teto salarial (2–4 meses)**
4. Performance web mensurável: Core Web Vitals, bundle budget, rendering.
5. Acessibilidade formal: WCAG, teclado, screen reader, auditoria.
6. Motion craft: Framer Motion / GSAP, spring physics, orquestração.

**Fase 3 — diferenciação (contínuo)**
7. React Three Fiber / Three.js com foco em performance — instancing, draw calls, LOD.
   Sincronizar centenas de entidades no espaço é literalmente o que ele já faz com drones.

**Não investir agora:** mais backend, mais clean architecture, mais um CRUD. O lastro já existe.

---

## 7. Correções aplicadas

- **React Native removido (2026-08-25).** Verificado no git: Gabriel nunca tocou `apps/mobile`
  no FaturaMed (zero commits) e não há React Native em nenhum outro projeto dele. O app mobile
  é inteiramente do sócio. Estava no currículo por suposição minha a partir do monorepo — erro corrigido.
- **Next.js calibrado.** O `apps/web` tem 42 arquivos em `app/` e 51 com `'use client'`, zero route
  handlers e um único `'use server'`: é uma aplicação React client-side usando Next.js como roteador.
  "Next.js (App Router)" segue verdadeiro (ele entregou dentro dele), mas não implica domínio de RSC.

---

## 8. Pendências

- Ano exato de conclusão do Animation Mentor confirmado como 2024; Méliès inferido como
  2022–2024 a partir de "2 anos, terminou em 2024" — confirmar.
- Cargo formal na Pixel Drone assumido como Drone Show Engineer — confirmar.
- URL do portfólio, a definir quando o site existir.
