# geo-content-brief

**Engine de briefing para conteúdo da era-IA: briefs que ranqueiam no Google e são citados por AI Overviews, ChatGPT, Perplexity, Gemini e Copilot.**

`geo-content-brief` é uma skill para diagnosticar e estruturar conteúdo otimizado para busca generativa (GEO/AEO/LLMO). Ela transforma um keyword num brief acionável — answer block, estrutura de H2 autocontidos, edge defensável e camada técnica (schema, llms.txt) — e fecha com um gate de pré-publicação. Ela estrutura; não escreve a página inteira. É vendor-neutral: serve a qualquer pessoa, marca ou negócio.

A diferença que ela ataca: SEO clássico te faz **clicável**; GEO/AEO te faz **citável**. As duas se acumulam — top-10 orgânico é pré-requisito de citação, mas não basta. O que ganha citação é estrutura.

---

## Quando usar

Use quando você tem um keyword e vai escrever uma página, ou quando já tem um rascunho que ranqueia mas não é citado pela IA. Funciona bem para artigos, páginas institucionais, bases de conhecimento e landing pages que precisam aparecer dentro da resposta gerada, não só no link azul.

| Bom alvo | Mau alvo |
|---|---|
| Keyword na mão, página a ser escrita | Pedido para a skill redigir a peça final inteira |
| Artigo que ranqueia mas não é citado por IA | Conteúdo sem nenhum diferencial real para oferecer |
| Estruturar conteúdo para AI Overviews / ChatGPT / Perplexity | Truque técnico para manipular ranking |
| Brief que o redator (ou outra skill) executa | Voz de marca que não pode ser respeitada |

---

## Os dois modos

A skill detecta o modo pelo material que você traz.

| Modo | Quando | Output |
|---|---|---|
| **ESTRATÉGIA** (default) | Keyword na mão, página ainda não existe | Brief de 8 campos pronto para o redator |
| **PRODUÇÃO** | Rascunho ou URL já existe; "otimiza esse artigo", "roda o gate" | Answer block reescrito + H2 map + schema + relatório do gate |

No modo ESTRATÉGIA, cinco módulos em ordem: **The Answer Block** · **The Structure** · **The Edge** · **The Brief Output** · **The Pre-Publish Check**.

---

## O brief (modo ESTRATÉGIA)

```text
keyword:        {termo-alvo}
core question:  {a pergunta única}
answer block:   {resposta 100–150 palavras}
H2 map:         {PAA Q1→H2 ... Q4→H2}
reader (ICP):   {quem lê — específico}
edge:           {diferencial único + como provar}
CTA:            {a única ação}
E-E-A-T signal: {citação / dado / prova de experiência}
```

---

## O gate (cinco binárias)

Todas SIM = libera para produção. Qualquer NÃO = volta ao módulo correspondente.

1. Os primeiros 150 palavras respondem a core question direto?
2. Cada H2 mapeia uma pergunta real (People Also Ask)?
3. Cada seção se sustenta sozinha?
4. ≥1 dado citado por seção?
5. Há insight humano que o resumo da IA não entrega?

---

## Instalar

### Testar agora, sem instalar

Abra [`SKILL.md`](./SKILL.md), copie o conteúdo inteiro e cole numa conversa nova com seu modelo de IA. Em seguida, descreva seu keyword e sua audiência:

```text
Use esta skill. Preciso de um brief GEO para o keyword "{keyword}", ICP "{quem lê}".
```

### Instalar no Claude Code / Cowork

```bash
SKILL=geo-content-brief
mkdir -p ~/.claude/skills/$SKILL
curl -sL https://raw.githubusercontent.com/1marcelserrano/geo-content-brief/main/skills/$SKILL/SKILL.md \
  -o ~/.claude/skills/$SKILL/SKILL.md
```

Depois reinicie a sessão do Claude. A skill dispara quando o pedido envolve brief de conteúdo, otimização para AI Overviews, GEO/AEO/LLMO, ser citado por IA, llms.txt ou schema para IA.

---

## Como pedir

```text
Monta um brief GEO pra "como precificar consultoria B2B", pra consultor solo.
```

```text
Esse artigo ranqueia mas a IA não cita. Roda o gate e me diz o que corrigir.
```

```text
Reescreve o topo dessa página pra ser citável e gera o FAQPage schema.
```

---

## Estrutura

```text
geo-content-brief/
├── SKILL.md
└── README.md
```

---

## Princípio

> A busca não termina mais num link. Termina numa resposta. Quem é citado, existe.

A skill diagnostica e estrutura. A voz da marca tem precedência — otimização para busca nunca justifica diluir voz. E o edge é inegociável: sem diferenciação real, a página é mais uma.

---

## Base do método

Baseada em pesquisa pública sobre Generative Engine Optimization: Aggarwal et al. (Princeton GEO, arXiv:2311.09735, SIGKDD 2024), Google Search Central e estudos de citação de AI Overviews. As estatísticas são direcionais, não garantias. Ver [`NOTICE.md`](../../NOTICE.md).

---

<sub>Forjado na [MSCREATIVE.SYSTEMS™](https://mscreative.systems) — Barcelona</sub>
