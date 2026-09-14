# Trilha de aprendizado — Gabriel Dantas

> **Alvo:** Design Engineer em empresa estrangeira, contractor remoto.
> **Data:** 2026-08-25. Baseada na análise real dos seus repositórios, não em lista genérica.

---

## Como usar esta trilha

Cada conceito aqui segue a mesma estrutura:

- **O problema** — por que esse conceito existe. Ninguém inventou nada por diversão; todo
  conceito é resposta a uma dor concreta.
- **A ideia** — a explicação do conceito em si.
- **No seu código** — onde isso já aparece (ou deveria aparecer) nos seus projetos.
- **Exercício** — o que fazer, no seu projeto real, para aprender de verdade.
- **Sinal de que aprendeu** — o teste honesto. Se você não passa nele, ainda não aprendeu.

**A regra número um:** um conceito por vez, aplicado no mesmo dia, no projeto real. Ler
sobre performance não ensina performance. Medir o LCP do FaturaMed, achar o culpado,
consertar e medir de novo ensina.

**O anti-padrão a evitar:** assistir 12 horas de curso e não escrever nada. Isso dá a
sensação de progresso sem o progresso. Você já sabe disso — seu histórico mostra que você
aprende metodologia e aplica. Mantenha esse instinto.

---

## Fase 0 — O que você já sabe (não estude de novo)

Isso aqui é para você não perder tempo. A análise dos seus repositórios mostra que você
**já domina**:

- Clean Architecture, camadas, injeção de dependência, inversão de dependência
- Validação na borda (Pydantic, Zod) — e o motivo pelo qual ela fica na borda
- Testes de backend com mocks, incluindo mocks assíncronos
- TypeScript com generics e tipos derivados (`z.infer`, `VariantProps`)
- Migrations versionadas, ADRs, runtimes pinados
- Design tokens e theming — **você faz, só não nomeia**
- Testes de frontend (Vitest, Testing Library) e E2E (Playwright)

O `CODING_PROFILE.md` de julho dizia que você não tinha testes de frontend nem
acessibilidade. **Está desatualizado.** Você fechou isso. Não reestude.

---

## Fase 1 — Destrava candidaturas (4 a 8 semanas)

### 1.1 Design System — o vocabulário do que você já pratica

**O problema.** Você construiu, no FaturaMed, um sistema de design inteiro: tokens, tema
dark, tipografia, camada de componentes compartilhados. Mas quando um recrutador procura
"design system engineer", ele filtra por palavras. Se você não usa as palavras, você não
existe na busca — mesmo tendo feito o trabalho.

**A ideia.** Um design system maduro organiza tokens em **três camadas**, e essa é a parte
que a maioria das pessoas erra:

1. **Primitivos** — o valor bruto: `blue-600: #2563eb`, `space-4: 16px`. Não têm significado,
   só existem.
2. **Semânticos** — o *papel* que o valor cumpre: `color-action-primary`, `color-text-muted`,
   `color-surface-raised`. Apontam para um primitivo.
3. **De componente** — o uso específico: `button-bg-primary`, `card-border`. Apontam para um
   semântico.

**Por que isso importa (a parte que ensina):** a camada semântica é *exatamente* o que faz o
tema dark funcionar. Se seu botão usa `blue-600` direto, trocar de tema significa reescrever
o botão. Se ele usa `color-action-primary`, o tema dark só redefine para onde esse nome
aponta — e nenhum componente é tocado. A camada do meio parece burocracia até o dia em que
você precisa de um segundo tema; aí ela é a única coisa que salva o projeto.

Conceitos vizinhos que valem o nome: **component API design** (quais props seu componente
expõe), **composition vs configuration** (`<Card><CardHeader/></Card>` versus
`<Card header="..." />` — e por que composição escala melhor), **headless components**
(Radix: comportamento e acessibilidade sem estilo).

**No seu código.** FaturaMed: `apps/web/app` e `apps/web/components`. Copesolo:
`frontend/src` com `class-variance-authority` e Radix.

**Exercício.** Abra os tokens do FaturaMed e classifique cada um nas três camadas. Você vai
achar tokens que pulam a camada semântica — componentes apontando direto para primitivos.
Conserte dois deles e observe o que muda no tema dark.

**Sinal de que aprendeu.** Você consegue explicar, sem abrir o código, por que trocar a cor
de marca do produto inteiro não deveria exigir tocar em nenhum arquivo de componente.

---

### 1.2 Case study técnico — a peça que convence mais que o currículo

**O problema.** Bullet de currículo diz *o que* você fez. Ninguém contrata por isso — todo
mundo "desenvolveu um sistema". Contrata-se por *como você pensa*, e isso só aparece quando
você mostra uma decisão com alternativa descartada.

**A ideia.** A estrutura de um case study que funciona:

1. **Contexto** — que produto, que gente usa, qual era o estado inicial.
2. **Restrição** — o que limitava (prazo, time de um, cliente sem tempo, dados sujos).
   *Restrição é o que torna a decisão interessante.*
3. **Decisão** — o que você escolheu.
4. **Trade-off** — **o que você abriu mão.** É a parte que separa engenheiro de executor.
   Quem não menciona trade-off não entendeu que estava escolhendo.
5. **Resultado** — o que mudou, de preferência observável.

**No seu código.** Você tem dois case studies prontos esperando serem escritos: o design
system do FaturaMed, e a trava de linha no fechamento da bonificação do Copesolo (essa é
excelente — "uma corrida podia pagar o mesmo trabalho duas vezes" é um problema que qualquer
engenheiro entende e respeita).

**Exercício.** Escreva o do Copesolo primeiro. É o mais fácil, porque a decisão é nítida.

**Sinal de que aprendeu.** Seu case study contém pelo menos uma frase começando com "a
alternativa era X, mas...".

---

### 1.3 Inglês técnico falado

**O problema.** Seu inglês escrito já resolve o currículo. O gargalo real é a entrevista:
explicar arquitetura ao vivo, defender uma decisão, discordar educadamente de um
entrevistador. Isso é um músculo separado da fluência.

**A ideia.** Você precisa de vocabulário de *processo*, não de tecnologia: "we ended up
going with...", "the trade-off there was...", "I'd push back on that because...",
"let me walk you through...".

**Exercício.** Grave-se, em inglês, explicando por 5 minutos como funciona o motor de
bonificação do Copesolo. Ouça de volta. Vai ser desconfortável — é o ponto. Repita semanal.

**Sinal de que aprendeu.** Você consegue ser interrompido no meio de uma explicação, responder
a pergunta, e voltar para onde estava.

---

## Fase 2 — Sobe o teto salarial (2 a 4 meses)

Esta fase é a que move você da faixa "Developer" (US$115–160k) para "Engineer"
(US$170–260k). Não é retórica: são literalmente as três competências que o mercado usa
para separar as duas faixas.

### 2.1 Performance web — Core Web Vitals

**O problema.** "O site está rápido" não é afirmação verificável. Empresas medem, e a métrica
tem consequência de negócio. Se você não fala em número, você fala em opinião.

**A ideia.** O Google padronizou três métricas, e vale entender o que cada uma realmente mede:

- **LCP (Largest Contentful Paint)** — quanto tempo até o *maior elemento visível* aparecer.
  Não é "quando a página carregou"; é quando o usuário sente que carregou. Alvo: < 2,5s.
- **INP (Interaction to Next Paint)** — quando o usuário clica, quanto tempo até a tela
  responder. Mede a *thread principal engasgada*. Alvo: < 200ms. Substituiu o antigo FID.
- **CLS (Cumulative Layout Shift)** — quanto a página pula enquanto carrega. É a métrica da
  imagem sem `width`/`height` que empurra o texto pra baixo. Alvo: < 0,1.

Conceitos que sustentam essas métricas:

- **Critical rendering path** — a sequência HTML → CSS → layout → paint. CSS é
  *render-blocking*: o navegador não pinta nada até baixar e processar. Por isso CSS gigante
  destrói o LCP.
- **Bundle budget** — um teto de KB que você se impõe e que o CI reprova se estourar. Sem
  teto, todo bundle cresce para sempre.
- **Code splitting e lazy loading** — quebrar o JS para que a rota inicial não pague pelo app
  inteiro.
- **Tree shaking** — o bundler descarta o que não é importado. Falha silenciosamente quando a
  biblioteca tem efeito colateral no import.
- **Hydration** — o HTML chega pronto do servidor, mas o React precisa "reanexar" os event
  listeners. Até isso terminar, a página *parece* pronta e não responde. É a causa mais comum
  de INP ruim em Next.js. React Server Components existem em boa parte para reduzir isso.

**No seu código.** FaturaMed usa Next.js App Router — você tem RSC disponível. Copesolo usa
Vite. Ambos nunca foram medidos.

**Exercício.** Rode Lighthouse no FaturaMed em produção. Anote LCP, INP, CLS. Ache o elemento
LCP (o DevTools mostra). Melhore-o. Meça de novo. **Anote os dois números.** Esses números
viram bullet de currículo e resposta de entrevista.

**Sinal de que aprendeu.** Você consegue dizer "o LCP era 3,4s, o culpado era X, ficou 1,9s".

---

### 2.2 O modelo de re-render do React

**O problema.** Você já usa `useMemo`/`useCallback`/`memo` em cerca de 10 arquivos. A pergunta
honesta é: por intuição ou por medição? Memo aplicado sem medir *adiciona* custo — o React
passa a comparar props toda vez, e a comparação não é grátis.

**A ideia.** Um componente React re-renderiza quando: (a) seu estado muda, (b) seu contexto
muda, ou (c) **seu pai re-renderiza** — independentemente das props. O item (c) é o que pega
todo mundo.

`React.memo` interrompe (c) fazendo comparação rasa das props. E aqui entra o conceito que
explica 90% dos memos inúteis: **referential equality**. Em JS, `{} !== {}` e
`() => {} !== () => {}`. Se você passa um objeto ou função criada inline, ela é *nova* a cada
render, a comparação rasa sempre falha, e o memo nunca economiza nada. Por isso
`useCallback`/`useMemo` costumam andar junto de `memo` — eles estabilizam a referência.

Ferramenta: **React DevTools Profiler**, com "Highlight updates" ligado. Você *vê* o que
re-renderiza.

Conceitos modernos que valem conhecer: `useTransition` e `useDeferredValue` — marcam uma
atualização como de baixa prioridade, para o input não travar enquanto uma lista pesada
recalcula. É solução de INP.

**Exercício.** Abra o Profiler no FaturaMed, use a tela de Pagamentos e veja o que
re-renderiza a cada tecla digitada num filtro. Se algo pesado renderiza sem precisar,
conserte — e confirme no Profiler.

**Sinal de que aprendeu.** Você consegue justificar cada `memo` do seu código apontando a
medição que o motivou — ou remove os que não têm.

---

### 2.3 Acessibilidade de verdade

**O problema.** Você usa `aria-*`, `role` e `sr-only` em 66 arquivos. Isso é ótimo como
instinto e perigoso como prática, porque **ARIA mal usado é pior que ARIA nenhum**: ele
sobrescreve a semântica nativa e pode deixar um componente inutilizável para quem usa leitor
de tela. Esse é um dos poucos lugares em frontend onde o esforço sem conhecimento causa dano.

**A ideia.** Comece pela regra que a própria especificação coloca em primeiro lugar:

> **Primeira regra do ARIA: não use ARIA.** Se existe elemento HTML nativo com a semântica
> que você quer, use ele. Um `<button>` já é focável, ativável por Enter e Espaço, e anunciado
> como botão. Uma `<div role="button">` precisa que você reimplemente tudo isso — e você vai
> esquecer alguma coisa.

Conceitos que sustentam o resto:

- **Accessible name computation** — o algoritmo que decide o nome que o leitor de tela
  anuncia. A ordem importa: `aria-labelledby` > `aria-label` > conteúdo > `title`. Botão só
  com ícone e sem nome acessível é um botão mudo.
- **Focus management** — ao abrir um modal, o foco vai para dentro dele; enquanto aberto, o
  Tab não escapa (*focus trap*); ao fechar, o foco **volta para o botão que abriu**. Esse
  retorno é a parte que quase todo mundo esquece, e é a mais sentida por quem navega por
  teclado.
- **Keyboard interaction patterns** — cada componente tem um contrato de teclas esperado
  (tabs andam com setas, menu fecha com Escape). O **ARIA Authoring Practices Guide (APG)** é
  a referência: não invente, consulte.
- **Contraste WCAG AA** — 4.5:1 para texto normal, 3:1 para texto grande e para elementos de
  interface. Isso é diretamente seu trabalho de tokens: um tema dark bonito que reprova em
  contraste é um tema quebrado.
- **Live regions** — `aria-live` para anunciar o que muda sem o usuário agir (um toast, um
  resultado de filtro).
- **`prefers-reduced-motion`** — a preferência do sistema para quem tem enxaqueca vestibular.
  Respeitar isso é obrigatório em qualquer coisa animada.

**Ferramentas.** axe DevTools (extensão), VoiceOver no Mac (`Cmd+F5`), e o teste mais
barato de todos: desconecte o mouse.

**Exercício.** Navegue o FaturaMed inteiro só pelo teclado, com VoiceOver ligado. Anote tudo
que quebra. Vai quebrar mais do que você espera — é normal, e a lista vira seu roteiro.

**Sinal de que aprendeu.** Você abre um modal, opera, fecha, e o foco volta sozinho para o
botão que o abriu — sem mouse, sem olhar.

---

### 2.4 Motion e interação — seu maior ativo não explorado

**O problema.** Você passou anos fazendo animação de personagem e coreografia de drone. Esse
conhecimento **não está aparecendo em nenhum lugar do seu trabalho web**, e é justamente o
que a maioria dos design engineers não tem.

**A ideia — e aqui está a ponte.** O que você chama de *timing* e *spacing* na animação
clássica é literalmente o que a web chama de *duration* e *easing*. Os 12 princípios da
animação continuam valendo; só mudou a runtime.

Conceitos a nomear:

- **Easing** — a curva de aceleração. Movimento linear parece robótico porque nada no mundo
  físico acelera de forma constante. `cubic-bezier` é a mesma curva de velocidade que você
  edita no graph editor do Maya.
- **Spring physics vs duration-based** — em vez de "leve 300ms", você descreve uma mola:
  `stiffness` (rigidez), `damping` (amortecimento), `mass` (massa). A grande vantagem é
  **interruptibilidade**: se o usuário clica de novo no meio, a mola continua de onde está,
  com a velocidade que tinha. Animação baseada em duração precisa reiniciar, e isso é o que
  faz interface parecer "dura".
- **Orchestration e stagger** — atrasar elementos em sequência para criar leitura. Você já
  faz isso com drones: é a mesma ideia de defasagem.
- **FLIP (First, Last, Invert, Play)** — a técnica para animar mudança de layout sem animar
  propriedades caras: você mede a posição inicial e a final, aplica um transform que
  "desfaz" a diferença, e anima esse transform até zero.
- **Orçamento de 60fps** — você tem **16,6ms por frame**. Propriedades baratas são as que a
  GPU compõe sem recalcular layout: `transform` e `opacity`. Caras são as que forçam layout:
  `width`, `height`, `top`, `left`. Animar `left` em vez de `translateX` é a causa clássica
  de animação travada.

**Ferramentas.** Motion (ex-Framer Motion) para React; GSAP quando precisar de timeline
complexa.

**Exercício.** Pegue uma transição do FaturaMed feita com duração e refaça com spring.
Interrompa-a no meio clicando duas vezes. Sinta a diferença — é ela que você vai vender.

**Sinal de que aprendeu.** Você consegue explicar por que uma animação de 300ms pode parecer
mais lenta que uma de 400ms, dependendo da curva.

---

## Fase 3 — Diferenciação: 3D no browser (contínuo)

Esta fase é o que fecha a lacuna que identificamos: você tem 3D de sobra, mas nenhum
código 3D que um recrutador consiga abrir.

### 3.1 Fundamentos de 3D em runtime

**O problema.** Você domina 3D em ferramenta de artista. No browser, você não clica — você
descreve a cena em código, e roda 60 vezes por segundo.

**A boa notícia:** quase todo conceito abaixo você já entende. O que muda é o nome e a
sintaxe, não a ideia.

- **Scene graph** — a hierarquia pai/filho de objetos, com transformações que se acumulam.
  É o outliner do Blender, em código.
- **Camera** — perspective (com FOV, near, far) ou orthographic. Igual ao que você já usa.
- **Geometry, Material, Mesh** — malha = geometria + material. Também igual.
- **Render loop** — a diferença real. Em vez de renderizar um frame e salvar, você tem uma
  função chamada a cada frame via `requestAnimationFrame`. Tudo que se move, se move ali.
- **PBR materials, lighting, shadow maps, UV** — mesmos conceitos do seu mundo, com custo de
  performance explícito: cada luz com sombra é caro em tempo real, ao contrário do render
  offline.

### 3.2 Performance em tempo real — onde sua experiência vira vantagem

**Preste atenção nesta seção**, porque ela é literalmente a sua história profissional
traduzida:

- **Draw call** — cada comando que a CPU envia à GPU. Muitos objetos separados = muitas draw
  calls = gargalo na CPU, não na GPU.
- **Instancing (`InstancedMesh`)** — desenhar **milhares de cópias do mesmo objeto em uma
  única draw call**, cada uma com sua própria matriz de transformação.
- **LOD (Level of Detail)** — trocar por versões mais simples conforme a distância.
- **Frustum culling** — não desenhar o que está fora da câmera.
- **Frame budget** — 16,6ms para tudo.

**A ponte:** renderizar 1.600 entidades sincronizadas no espaço, cada uma com posição própria
e timing próprio, dentro de um orçamento de tempo real — **é exatamente o que você já faz com
drones.** Você não vai *aprender* esse problema; vai aprender a API que o resolve no browser.
É por isso que essa fase é seu diferencial e não sua dificuldade.

### 3.3 Shaders — deixe por último

- **Pipeline** — vertex shader (move vértices) → fragment shader (pinta pixels).
- **GLSL** — a linguagem. `uniforms` (valores iguais para todos), `attributes` (por vértice),
  `varyings` (interpolados do vertex para o fragment).
- **Por que é difícil:** o shader roda em paralelo para milhões de pixels e não tem `console.log`.
  Você depura pintando cores.

**Aviso honesto:** é a parte mais lenta de aprender e a que menos destrava vaga no começo.
Não comece por aqui.

### 3.4 React Three Fiber

Como o R3F mapeia Three.js para JSX, e onde a abstração vaza: dentro do `useFrame` você
**não** deve chamar `setState` (isso re-renderizaria o React 60 vezes por segundo). Mutação
direta via `ref` é o padrão correto ali — e essa é a exceção que confunde todo mundo que vem
do React de produto.

---

## Fase 4 — Lacunas de engenharia que ainda valem fechar

### 4.1 Observabilidade

**O problema.** Seu próprio perfil de código aponta `print()` e `console.log()` como única
forma de debug. Isso funciona no seu laptop e falha em produção, onde você não está olhando.

**A ideia.** **Logging estruturado** — logar objeto, não string, para que seja pesquisável
(`{"event": "payment_closed", "userId": 12, "durationMs": 340}`). **Níveis** (debug/info/
warn/error) para filtrar por gravidade. **Correlation ID** — um identificador que acompanha
uma requisição por todos os serviços, permitindo reconstruir o que aconteceu. **Error
tracking** (Sentry) com **source maps**, para que o stack trace do bundle minificado volte a
apontar para o seu código.

### 4.2 CI/CD

**O problema.** Você já roda `typecheck`, `lint`, `test` e `build` — na mão. Isso significa
que o dia em que você esquecer, quebra.

**A ideia.** Uma pipeline que roda o mesmo conjunto a cada push, com **gates** (não faz merge
se reprovar) e **preview deploys** (cada branch ganha uma URL — o cliente do Copesolo
consegue ver a tela antes de ir pra produção). O runtime pinado que você já configurou é
exatamente o que faz a pipeline reproduzir a sua máquina.

---

## A curva — ordem sugerida

```
Semana 1–2    Case study do Copesolo + design tokens em 3 camadas
Semana 3–4    Core Web Vitals: medir, consertar, medir de novo
Semana 5–6    Acessibilidade: teclado + VoiceOver no FaturaMed
Semana 7–8    Motion: spring, easing, orquestração
              → aqui o site-portfólio já pode nascer
Mês 3         React re-render + Profiler · Observabilidade · CI/CD
Mês 4–5       Three.js fundamentos + R3F
Mês 6+        Performance em tempo real (instancing, LOD)
              → a peça de creative coding que fecha a lacuna
Depois        Shaders
```

**Por que essa ordem.** As quatro primeiras semanas produzem material que entra no
portfólio *imediatamente*. Performance e acessibilidade vêm antes de 3D porque são o que
muda sua faixa salarial agora. 3D vem depois porque é diferenciação, e diferenciação só vale
depois que o básico está comprovado.

---

## Como saber que a trilha está funcionando

Não é "terminei o curso". É:

1. Você consegue **explicar o conceito para outra pessoa** sem consultar nada.
2. Existe **código seu, em projeto real**, usando o conceito.
3. Você consegue dizer **o que você abriu mão** ao usá-lo. Todo conceito tem custo; quem só
   sabe o benefício ainda não entendeu.

Se os três valem, aprendeu. Se algum falha, ainda não — e tudo bem, volta um passo.
