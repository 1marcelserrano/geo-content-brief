# geo-content-brief

**Conteúdo que a IA cita. Não só conteúdo que o Google ranqueia.**

Uma skill do Claude que transforma um keyword num brief de conteúdo para a era da busca generativa (GEO/AEO/LLMO): uma página que ranqueia no top-10 do Google **e** é citada dentro das respostas de AI Overviews, ChatGPT, Perplexity, Gemini e Copilot. Um arquivo markdown. Sem servidor, sem dependência, vendor-neutral.

[Instalar](#instalar) · [O que ela entrega](#o-que-ela-entrega) · [Quando usar](#quando-usar) · [Os dois modos](#os-dois-modos) · [Exemplo](#exemplo) · [FAQ](#faq) · [Página](https://geo-content-brief-page.vercel.app)

---

A busca não termina mais num link. Termina numa resposta. Você pergunta, e o AI Overview já responde no topo — com três fontes citadas e um punhado de links que quase ninguém clica. SEO clássico te faz *clicável*. Isso não basta mais. O que decide se você aparece na resposta é ser *citável*.

As duas coisas se acumulam. Top-10 orgânico é pré-requisito — cerca de 52% das citações de AI Overview saem do top-10. Mas estar no top-10 não garante citação. O que ganha citação é estrutura: resposta direta no topo, seções que se sustentam sozinhas, dado próprio, prova de autoridade. É isso que esta skill estrutura.

Ela **diagnostica e estrutura** — não escreve a página inteira. Entrega o brief que torna a página inevitável; a redação fina fica para o escritor, humano ou outra skill.

## O problema

Você publica um artigo bom. Ele até ranqueia. E mesmo assim a IA cita o concorrente. O motivo raramente é o assunto — é a forma. O texto aquece por três parágrafos antes de responder. Os subtítulos não respondem nada sozinhos. Não tem um dado que a IA possa extrair e atribuir. Falta a marca de quem viveu aquilo.

O crawler de IA lê seções isoladas, resume os primeiros 30% da página e prefere conteúdo com fonte, número e citação. Quem não dá isso de mão beijada fica de fora da resposta — não importa a posição no ranking.

## O que ela entrega

Um brief pronto para o redator, com oito campos que tiram a página da prateleira da commodity:

| Campo | O que resolve |
|-------|---------------|
| **keyword** | O termo ou pergunta que a página vai dominar |
| **core question** | A única pergunta que a página responde — sem dispersão |
| **answer block** | 100–150 palavras de resposta direta no topo, citáveis verbatim |
| **H2 map** | Cada pergunta real (People Also Ask) vira um H2 autocontido |
| **reader (ICP)** | Quem digita aquilo — quanto mais específico, melhor o edge |
| **edge** | O que a página entrega que o top-5 não entrega, e como provar |
| **CTA** | A única ação que a página pede |
| **E-E-A-T signal** | A citação, o dado ou a prova de experiência que sustenta a autoridade |

Mais a camada técnica (LLMO): `FAQPage` JSON-LD inline, entrada de `llms.txt` e o gate de pré-publicação de cinco pontos.

## Quando usar

**Use quando:**
- Você tem um keyword na mão e vai escrever uma página do zero
- Seu artigo ranqueia mas não é citado por AI Overviews nem por ChatGPT/Perplexity
- Você quer estruturar conteúdo para aparecer em busca generativa, não só no link azul
- Precisa de um brief que o redator (ou outra skill) executa sem adivinhar a intenção

**Não use quando:**
- Você quer que a skill escreva a página inteira → ela estrutura, não redige a peça final
- Não há nenhum diferencial real para oferecer → sem edge, a página é só mais uma
- O objetivo é manipular ranking com truque técnico → ela otimiza estrutura honesta, não burla

## Os dois modos

A skill detecta o modo pelo material que você traz.

| Modo | Quando | Output |
|------|--------|--------|
| **ESTRATÉGIA** (default) | Keyword na mão, página ainda não existe. "Preciso de um brief", "como otimizar X para IA" | Brief de 8 campos pronto para o redator |
| **PRODUÇÃO** | Já existe rascunho ou URL. "Otimiza esse artigo", "ele vai ser citado?", "roda o gate" | Answer block reescrito + H2 map + schema + relatório do gate |

No modo ESTRATÉGIA ela trabalha cinco módulos em ordem: **The Answer Block** (a resposta direta) · **The Structure** (PAA → H2 autocontidos) · **The Edge** (o diferencial defensável) · **The Brief Output** (o entregável) · **The Pre-Publish Check** (o gate). No modo PRODUÇÃO ela diagnostica o que já existe e corrige sem reescrever o que funciona.

## Exemplo

**Pedido:** brief para a keyword *"como precificar consultoria B2B"*, ICP *consultor solo que cobra por hora e quer migrar para valor*.

**Trecho do brief (campo answer block):**

> *Precificação por valor em consultoria B2B é o modelo em que o preço reflete o resultado entregue ao cliente, não as horas trabalhadas. Em vez de multiplicar tempo por taxa, você ancora o valor no impacto — receita destravada, custo evitado, risco reduzido. Para um consultor solo, a virada começa por trocar a pergunta "quanto custa minha hora?" por "quanto vale o problema que eu resolvo?".*

**E o edge marcado:** *"esta página traz uma tabela com três faixas de preço por tamanho de problema — que o top-5 atual, todo genérico, não tem. Prova: cálculo reproduzível, com fonte."*

Resposta direta no topo, primeira frase no padrão definicional, um dado extraível, um ângulo que o top-5 não cobre. É o que a IA cita.

Método completo em [`skills/geo-content-brief/SKILL.md`](./skills/geo-content-brief/SKILL.md).

## Instalar

```bash
# Via skills CLI (recomendado)
npx skills add 1marcelserrano/geo-content-brief

# Ou manualmente — faça backup antes se a pasta já existir:
# mv ~/.claude/skills/geo-content-brief ~/.claude/skills/geo-content-brief.backup
git clone https://github.com/1marcelserrano/geo-content-brief.git
cp -r geo-content-brief/skills/geo-content-brief ~/.claude/skills/
```

**Verifique:** abra uma sessão nova do Claude e rode `/skills` (ou pergunte "que skills você tem?"). `geo-content-brief` deve aparecer. Se não, confira que `~/.claude/skills/geo-content-brief/SKILL.md` existe e reinicie a sessão.

**Sem terminal?** Baixe [`geo-content-brief.skill`](./geo-content-brief.skill) e suba no Claude (Cowork / claude.ai → Skills).

**Testar sem instalar:** abra [`SKILL.md`](./skills/geo-content-brief/SKILL.md), copie o conteúdo inteiro, cole numa conversa nova e em seguida descreva seu keyword e sua audiência.

## FAQ

**Isso é SEO ou é outra coisa?** As duas. SEO clássico te faz clicável e é pré-requisito — sem top-10, não há citação. GEO/AEO/LLMO te faz citável dentro da resposta gerada. A skill cuida da camada que decide a citação: estrutura, answer block, dado, schema.

**Funciona pra qualquer assunto ou marca?** Sim. A skill é vendor-neutral e genérica — serve para qualquer pessoa, marca ou negócio. Ela calibra o brief pelo seu ICP e pela sua voz, não por um nicho fixo.

**Precisa de API key, conta paga ou servidor?** Não. É um arquivo markdown que o Claude carrega. Roda onde o Claude roda.

**Os números do método são garantia?** Não. As correlações vêm de estudos (Princeton GEO e medições de citação de AI Overviews) e ordenam prioridade — não são lei. Onde a decisão é cara, valide na fonte primária. A skill é direcional, não promete posição.

**Ela escreve a página por mim?** Não. Ela diagnostica e estrutura: entrega o brief, o answer block e o gate. A redação fina fica para o escritor, humano ou outra skill.

**E a voz da marca?** Tem precedência. Otimização para busca nunca justifica diluir voz — é a primeira regra operacional da skill.

---

Uma skill do **[MSCREATIVE.SYSTEMS™](https://fronteirista.substack.com)**. Método baseado em pesquisa pública sobre Generative Engine Optimization — Aggarwal et al. (Princeton GEO, arXiv:2311.09735, SIGKDD 2024), Google Search Central e estudos de citação de AI Overviews. Ver [`NOTICE.md`](./NOTICE.md). Licença MIT — use, modifique, redistribua. Mantenha os créditos.
