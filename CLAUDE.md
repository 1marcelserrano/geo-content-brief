# CLAUDE.md — geo-content-brief

## O que é este repo

Uma skill do Claude distribuída como repositório público no GitHub. A única
fonte de verdade do comportamento é `skills/geo-content-brief/SKILL.md`. Toda
mudança de comportamento começa por lá.

A skill estrutura conteúdo para a era da busca generativa (GEO/AEO/LLMO):
transforma um keyword num brief que faz a página ranquear no Google e ser
citada por AI Overviews, ChatGPT, Perplexity, Gemini e Copilot. Bimodal —
modo ESTRATÉGIA (brief do zero) e modo PRODUÇÃO (otimizar o que já existe).
O repo é uma vitrine: o README é uma landing page, não só documentação.

## O que editar

| Arquivo | O que controla |
|---------|----------------|
| `skills/geo-content-brief/SKILL.md` | Comportamento — triggers, modos, módulos, gate, prompts. PT-BR, canônico. |
| `skills/geo-content-brief/README.md` | Resumo por-skill voltado pra humano. |
| `README.md` (raiz) | Porta de entrada do produto. Otimizar pra quem quer ser citado por IA. |
| `assets/social-preview.html` | Instância do gabarito DS V3.0 (motivo geo) do social card. |
| `page/index.html` | Página-vitrine interativa publicada na Vercel. |

## O que NÃO editar

- Não edite a skill canônica no monorepo privado `mscs-skills` a partir daqui —
  este repo é um espelho publicado. Mudanças de comportamento fluem pelo `skills-sync`.
- Mantenha o frontmatter do SKILL.md (`name`, `description`, `metadata`) intacto.
- Não fabrique métricas. Os números do método vêm da pesquisa citada e são
  direcionais — nunca os apresente como garantia de posição ou de citação.
- Nunca commite `.env`, tokens ou credenciais.

## Convenções

- Idioma: README/skill em PT-BR; voz Tradutor, frases curtas, voz ativa, zero floreio.
  Sem léxico inflado, sem paralelismo negativo. Termo proprietário aterrissa na 1ª menção.
- A skill é vendor-neutral. Não amarrar a um nicho, marca ou fornecedor específico.
- Commits: Conventional Commits. Push só com SHA verificado (local = remote).

## Licença

MIT. Método baseado em pesquisa pública (Princeton GEO, Google Search Central,
estudos de AI Overviews). Ver NOTICE.md. Contribuições bem-vindas — ver CONTRIBUTING.md.
