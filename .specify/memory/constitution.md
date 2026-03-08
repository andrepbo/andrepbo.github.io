<!--
Sync Impact Report
- Version change: template inicial sem versao definida -> 1.0.0
- Modified principles:
  - Placeholder principle 1 -> I. Representacao Profissional Fiel
  - Placeholder principle 2 -> II. Consistencia Entre Paginas
  - Placeholder principle 3 -> III. Clareza e Leitura Escaneavel
  - Placeholder principle 4 -> IV. Site Estatico, Acessivel e Rapido
  - Placeholder principle 5 -> V. Disciplina de Mudanca e Revisao
- Added sections:
  - Padroes de Conteudo e Tom
  - Fluxo de Trabalho e Quality Gates
- Removed sections:
  - Placeholder section 2
  - Placeholder section 3
- Templates requiring updates:
  - ✅ .specify/templates/plan-template.md (alinhado; usa Constitution Check generico)
  - ✅ .specify/templates/spec-template.md (alinhado; requisitos e criterios mensuraveis compativeis)
  - ✅ .specify/templates/tasks-template.md (alinhado; tarefas de validacao, docs e qualidade ja previstas)
  - ✅ .specify/templates/constitution-template.md (nenhuma mudanca necessaria no template base)
- Follow-up TODOs:
  - Nenhum
-->

# Andre Oliveira CV Website Constitution

## Core Principles

### I. Representacao Profissional Fiel
Todo conteudo publicado MUST ser factualmente correto e verificavel com base nas
informacoes profissionais reais do autor. Datas, cargos, empresas, tecnologias,
certificacoes e resultados MUST refletir a experiencia real, sem inflacao de
escopo ou linguagem enganosa.
Rationale: O principal objetivo do projeto e credibilidade profissional.

### II. Consistencia Entre Paginas
Informacoes compartilhadas entre `index.md`, `resume.md`, `projects.md` e
`skills.md` MUST permanecer semanticamente consistentes. `resume.md` MUST ser a
fonte canonica para historico profissional e contatos; qualquer alteracao
nesses dados MUST ser propagada para as demais paginas no mesmo ciclo.
Rationale: Evita contradicoes e melhora manutencao.

### III. Clareza e Leitura Escaneavel
O texto MUST priorizar leitura rapida por recrutadores e liderancas tecnicas:
secoes objetivas, bullets claros e linguagem direta. Conteudo MUST focar
impacto, escopo e tecnologias usadas; jargao excessivo e repeticao SHOULD ser
evitados quando nao agregam sinal.
Rationale: CV online e consumido de forma rapida e comparativa.

### IV. Site Estatico, Acessivel e Rapido
O projeto MUST manter arquitetura estatica com Jekyll e degradacao graciosa sem
JavaScript obrigatorio para leitura do conteudo principal. Alteracoes visuais
MUST preservar semantica HTML, contraste adequado e responsividade em mobile e
desktop. Assets SHOULD permanecer leves para carregamento rapido.
Rationale: O CV precisa abrir rapido e funcionar em qualquer contexto.

### V. Disciplina de Mudanca e Revisao
Cada alteracao de conteudo ou layout MUST incluir revisao de consistencia,
ortografia e regressao visual basica. Quando o ambiente permitir, a mudanca
MUST ser validada com build local (`bundle exec jekyll build`) antes de
finalizacao. Commits MUST explicitar escopo (conteudo, layout, estilo, dados).
Rationale: Reduz erros publicos e facilita rastreabilidade.

## Padroes de Conteudo e Tom

- Idioma principal MUST ser consistente por pagina; mudancas bilinguas devem ser
planejadas por secao completa, nao por frases soltas.
- Dados sensiveis SHOULD ser minimizados; contato deve priorizar canais
profissionais.
- Projetos listados MUST destacar contribuicao, periodo e stack tecnica.
- Certificacoes MUST incluir ano para contexto temporal.
- Informacoes com data em aberto MUST usar formato explicito (ex.: `Aug 2025-Present`).

## Fluxo de Trabalho e Quality Gates

- Toda alteracao MUST iniciar com entendimento do impacto cruzado entre paginas.
- Alteracoes de experiencia profissional MUST atualizar ao menos `index.md` e
`resume.md` no mesmo trabalho.
- Alteracoes em skills/certificacoes MUST verificar coerencia com secoes de
experiencia e projetos.
- Antes de concluir, MUST haver checklist minimo:
  - Coerencia de fatos e datas.
  - Leitura e gramatica.
  - Renderizacao esperada das secoes alteradas.
  - Ausencia de contradicoes entre paginas.

## Governance

Esta constituicao prevalece sobre praticas ad hoc do repositorio para evolucao
do CV online.

- Emendas MUST registrar motivacao e impacto esperado no topo deste arquivo
quando alterarem principios ou gates.
- Versionamento MUST seguir SemVer:
  - MAJOR: remocao/redefinicao de principios ou governanca incompativel.
  - MINOR: novo principio, nova secao mandataria ou expansao normativa material.
  - PATCH: clarificacoes editoriais sem mudanca de obrigatoriedade.
- Revisoes de conformidade MUST ocorrer em toda alteracao relevante de conteudo
profissional, layout estrutural ou processo de validacao.

**Version**: 1.0.0 | **Ratified**: 2026-03-08 | **Last Amended**: 2026-03-08
