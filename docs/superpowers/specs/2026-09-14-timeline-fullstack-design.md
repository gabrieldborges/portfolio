# Timeline de feitos + reposicionamento Full-Stack — design

> **Data:** 2026-09-14
> **Substitui:** a seção de posicionamento e a estrutura do site da spec de 2026-08-25.
> A spec de agosto continua valendo para evidência verificada no git, formato do CV e regra
> de honestidade.

---

## 1. Posicionamento

**Alvo:** Full-Stack Developer, remoto, contractor, empresas estrangeiras.

**O que mudou.** Em agosto o alvo era Design Engineer. O Gabriel decidiu atacar full-stack.
O rótulo é defensável porque o histórico real é full-stack de ponta a ponta: sozinho na GBS
Construtora (2025) e sozinho na Copesolo & Concresolo (2026), ambos em produção.

**Risco assumido.** Full-stack é a faixa mais concorrida do mercado remoto. O que
compensa é o que quase nenhum candidato full-stack tem junto:

1. **Ownership solo de sistemas em produção** para empresas reais, com ADRs, testes e
   contratos de API gerados.
2. **Design system entregue** (FaturaMed): o full-stack que também sabe fazer a interface
   ficar bonita e consistente.
3. **Passado em 3D e drone shows**: a história que ninguém esquece na entrevista.

**Regra de honestidade** mantida: escopo e responsabilidade, nunca volume.

## 2. Estrutura das entradas

GS3 Motion sai. Cada empresa é uma entrada própria:

| Período | Empresa | Tipo |
|---|---|---|
| 2024 | Damoda | 3D Technical Artist, 3 meses |
| 2024–2026 | Alok | Drone Show Engineer |
| 2024–2026 | Pixel Drone | Drone Show Engineer |
| Fev–Nov 2025 | GBS Construtora | Full-Stack Developer, freelance |
| Jan 2026–hoje | Copesolo & Concresolo | Software Developer, Technology & Innovation Lead, cargo |
| Abr–Ago 2026 | FaturaMed | Frontend & Design System Engineer, freelance |

Conteúdo completo em `docs/timeline.md`.

**FaturaMed.** O Gabriel assina o frontend inteiro. A leitura de guias por IA foi do sócio e
aparece como descrição do produto, não como feito dele.

## 3. Site

**Uma página de timeline**, cronológica, começando nos drones. As páginas planejadas em
agosto (home com cena 3D, dois case studies, about) ficam fora até segunda ordem.

**Stack decidida (2026-09-14):** site estático, um `index.html` com Tailwind via CDN local, sem
framework. Motivo: o design system escolhido ("Canvas", da pasta de referências da Asimov) é
HTML + Tailwind, e uma página de timeline não justifica Next.js. As escolhas de agosto (Next.js,
R3F, Motion) ficam descartadas para esta versão; Vercel continua boa opção de hospedagem.

**Fotos:** as cinco fotos de drones ficam em um carrossel automático com dots e contador, dentro
do capítulo de drones. GBS, Copesolo e FaturaMed usam logo/ícone individual.

## 4. Currículo

Mesmo layout do `cv-en.html`. Mudanças de conteúdo:

- Título: `Full-Stack Developer · TypeScript, React, Python & Design Systems`.
- Summary reescrito para full-stack, mantendo drones e "sole engineer".
- Experiência na ordem: Copesolo → FaturaMed → GBS → Alok → Pixel Drone → Damoda.
- Skills: Backend e Frontend no topo, Design Engineering em terceiro. Linha de IA reduzida a
  workflows de desenvolvimento assistido.
- PDF novo: `Gabriel Dantas - Full-Stack Developer - CV.pdf`.

## 5. Próximos passos

1. Receber o design system.
2. Escolher a stack do site.
3. Spec visual da timeline e plano de implementação.
