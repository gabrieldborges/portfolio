# Estado atual — onde paramos

> **Última atualização:** 2026-09-14
> **Para retomar:** leia este arquivo primeiro. Ele diz o que está pronto, o que foi
> decidido, o que está em aberto e qual é o próximo passo exato.

---

## Visão geral

Dois projetos, em estágios diferentes:

| Projeto | Estado |
|---|---|
| **Currículo em inglês** | ✅ Atualizado para **Full-Stack Developer** (2026-09-14), 1 página |
| **Trilha de aprendizado** | ✅ Concluída (escrita para o alvo Design Engineer; a ordem ainda vale) |
| **Site-portfólio** | 🟢 Timeline construída em `site/index.html` (2026-09-14), estático, aguardando revisão do Gabriel |

**Mudança de 2026-09-14:** alvo passou de Design Engineer para **Full-Stack Developer**
(remoto, empresas estrangeiras). Spec: `docs/superpowers/specs/2026-09-14-timeline-fullstack-design.md`.
Conteúdo de site e CV vive em `docs/timeline.md`.

---

## 1. Currículo — CONCLUÍDO

### Arquivos

```
Gabriel Dantas - Full-Stack Developer - CV.pdf   o entregável atual
Gabriel Dantas - Design Engineer - CV.pdf        versão anterior (histórico)
cv-en.html                                       a fonte do PDF estilizado (barra lateral, foto, laranja)
cv-en-ats.html                                   versão simples de uma coluna, fallback para triagem automática
cv-photo.jpg                                     foto usada no currículo (mesma do site)
docs/timeline.md                                 fonte do conteúdo (datas, feitos, notas)
docs/superpowers/specs/2026-09-14-timeline-fullstack-design.md
                                                 posicionamento atual
docs/superpowers/specs/2026-08-25-curriculo-design-engineer-design.md
                                                 evidência verificada no git, regra de honestidade
```

### Como regenerar o PDF depois de editar o HTML

```sh
cd ~/Desktop/Work/gabrielDev
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless \
  --no-pdf-header-footer \
  --print-to-pdf="Gabriel Dantas - Full-Stack Developer - CV.pdf" \
  "file://$HOME/Desktop/Work/gabrielDev/cv-en.html"
```

Verificado em 2026-09-14: 1 página, 16 links clicáveis (site, e-mail, telefone, LinkedIn, GitHub,
repos do Refund). Os links só saem clicáveis se estiverem em `<a href>`; `<span>` não vira link.
Para a versão ATS, troque `cv-en.html` por `cv-en-ats.html` no comando. Para conferir páginas:

```sh
python3 -c "import re;print(re.findall(rb'/Count (\\d+)',open('Gabriel Dantas - Full-Stack Developer - CV.pdf','rb').read()))"
```

### Pendências do currículo

- [ ] Confirmar período da **Faculdade Méliès** (deduzido 2022–2024 a partir de
      "2 anos, terminou em 2024")
- [ ] Confirmar cargo formal na **Pixel Drone** (assumido Drone Show Engineer)
- [x] Link do portfólio no currículo (2026-09-14)
- [ ] Algum número da **GBS Construtora** (obras, usuários, tempo até produção)
- [ ] Confirmar o título em inglês na **Copesolo** (usado: Software Developer · Technology & Innovation Lead)

### Correção importante já aplicada

**React Native foi removido.** Verificação no git mostrou que Gabriel nunca tocou
`apps/mobile` no FaturaMed (zero commits) e não há React Native em nenhum outro projeto.
O app mobile é inteiramente do sócio. Estava no currículo por suposição — corrigido.

---

## 2. Trilha de aprendizado — CONCLUÍDA

`docs/trilha-de-aprendizado.md` — 4 fases, cada conceito com problema, ideia, onde
aparece no código dele, exercício e sinal de que aprendeu.

Ordem: case study + design tokens → Core Web Vitals → acessibilidade → motion →
(site nasce aqui) → React re-render, observabilidade, CI/CD → Three.js → tempo real → shaders.

---

## 3. Site-portfólio — TIMELINE CONSTRUÍDA

### O que existe (2026-09-14)

```
site/index.html          a página inteira (HTML + Tailwind CDN local + JS do carrossel)
site/assets/             tailwind.js, iconify.js, inter.css + woff2 da Inter (copiados do template)
site/img/                fotos otimizadas (drone-01..05.jpg), logos, ícone do FaturaMed
site/cv.pdf              cópia do currículo atual, linkada nos botões "CV"
```

**Design system usado:** "Canvas" (`temas_escuros/canvas-visual.aura.build`, na pasta de
referências do curso da Asimov). Preservado como está: Inter, fundo #050505, superfície #0A0A0A,
laranja #F97316, bordas white/10, cantos retos, labels mono uppercase, animações fadeSlideIn com
IntersectionObserver, beam borders, floating cards, botão com cantos, botão com beam girando,
grid de métricas, card laranja e marca d'água no footer.

**Estrutura da página:** nav → hero (título "Full Stack", frase "From drone show engineering
to full-stack development", carrossel "Projects and Clients" com 6 slides, coluna de stats) →
about (manifesto + métricas + lista de empresas) → timeline (5 capítulos: Drones 2024–26 com
carrossel · GBS 2025 · Copesolo 2026 · FaturaMed 2026 · Refund 2026 open source) → footer
(e-mail, links, card de download do CV). Há um CTA fixo no rodapé da tela ("Explore the
timeline") que some enquanto a timeline está visível.

**Carrossel dos drones:** scroll-snap nativo + JS. Avança sozinho a cada 5s, com dots, contador
"01 / 05", setas, barra de progresso, pausa no hover/foco/toque e fora da tela, setas do teclado,
e desliga o autoplay com `prefers-reduced-motion`. Fotos verticais aparecem inteiras sobre uma
cópia desfocada de fundo, em vez de cortadas.

**Dependência externa mantida do template:** o fundo animado é o Unicorn Studio, carregado da
CDN jsdelivr com o project id do template. Sem internet o fundo fica preto liso, sem quebrar nada.
Se quiser remover, apague o bloco `aura-background-component` no topo do body.

### Como ver e como publicar

```sh
npm run dev            # serve site/ em http://localhost:4173
open site/index.html   # ou direto no navegador, sem servidor
```

**Estrutura de deploy (2026-09-14):** a pasta raiz é o repositório git. `package.json` tem
`start: serve -s site -l ${PORT:-4173}`; `railway.json` aponta o start command e o healthcheck
em `/`. Na Railway: New Project → Deploy from GitHub repo. Ela roda `npm install` e `npm start`,
e `site/index.html` responde na raiz. Verificado localmente: `/`, `/cv.pdf`, `/img/eu.jpg` e o
fallback de SPA respondem 200. O `README.md` da raiz tem o passo a passo.

**Foto pessoal:** `site/img/eu.jpg` (recorte quadrado de `~/Downloads/Dev images/eu_1.1.1.JPG`),
no about, card à direita com `rounded-lg` e `rotate-[4deg]`, atrás do texto no desktop e acima
do texto no celular.

O `.gitignore` deixa de fora `node_modules/` e o PDF antigo de 11 MB
("Gabriel Dantas Resume 2026 EN.pdf").

### Pendências do site

- [ ] Gabriel revisar visual e textos (legendas das fotos são deduções: "Fig. 01 — Pre-show
      fleet layout", "Fig. 02 — Fleet in flight, Shenzhen", "Fig. 03 — Shenzhen TV feature",
      "Fig. 04 — Damoda, Shenzhen", "Fig. 05 — Night test")
- [x] Publicado em **https://gabrieldantas.up.railway.app** (repo github.com/gabrieldborges/portfolio, Railway, 2026-09-14)
- [ ] **Domínio.** Recomendação mantida: domínio pessoal, separado de `gsmotion.com`
- [x] Link do site no currículo, README do perfil e textos do LinkedIn (2026-09-14)
- [ ] Publicar os textos do LinkedIn (`docs/linkedin-profile.md`, campo a campo). O README do GitHub já está no ar.

## 3b. GitHub — feito em 2026-09-14

- Arquivados 15 repositórios de exercício (Local-Turistico, Page-News, Formulario-Matricula,
  LPatins, Convert, fogefoge, AdvancingC, pet, animated-broccoli, hairday, support-tickets,
  RealTimeNotifications, bank-api-mvc, pedidos-mvc-jwt, gallery-plus-template). Reversível.
- Descrição, tópicos e homepage (Railway) em Refund, Refund-api, HairdayFullApp, mvc_pets_api.
- Dependabot do Refund resolvido (npm audit fix + vitest 4.1.11); 485 testes, typecheck, lint e build passando.
- READMEs do Refund e do Refund-api reescritos em inglês, links cruzados corrigidos, URLs ao
  vivo no topo. README de perfil ganhou a linha do Refund e perdeu os `[site]`.
- **Pendente, precisa do Gabriel:** bio/empresa/site do perfil (o `gh` não tem o escopo `user`;
  rodar `gh auth refresh -h github.com -s user` e repetir), e os fixados (não há API: fixar
  Refund-api, Refund, HairdayFullApp, mvc_pets_api; tirar gallery-plus-template).

## 4. Contexto que não está em nenhum outro arquivo

**Sobre Next.js.** Gabriel domina React; usou Next.js como roteador. Medido: `apps/web` do
FaturaMed tem 42 arquivos em `app/` e **51 com `'use client'`**, zero route handlers, um
único `'use server'`. Ou seja, é um app React client-side vestindo Next.js. O que ele não
exercitou: Server Components, fronteira client/server, server actions, cache/revalidação,
streaming com Suspense. São ~1 semana de trabalho focado, e o site é o veículo.

**Sobre os cursos da Rocketseat.** Recomendação dada:
- **React Native: não fazer agora.** Não serve ao alvo escolhido, e títulos de mobile nativo
  estão entre os que mais desaparecem no mercado.
- **Next.js: não precisa do curso inteiro.** A lacuna é estreita e específica; aprender
  construindo o site cobre ela e ainda produz artefato.

**Sobre WebGL.** Ele nunca escreveu uma linha. Mas domina os *conceitos* de 3D (scene graph,
câmera, materiais, luz) — que é a maior parte da carga. O novo é a API e a disciplina de
tempo real. Isso o coloca muito à frente de um dev frontend comum aprendendo Three.js.
