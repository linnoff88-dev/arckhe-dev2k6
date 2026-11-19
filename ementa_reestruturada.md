# DEV2K6 - Engenharia de Software com IA Avancada

Formacao completa para devs que querem dominar IA como ferramenta de engenharia, nao como muleta.
3 trilhas, 15 modulos, ~100 topicos, 50+ exercicios praticos.

Filosofia: 60% pratica, 40% conceito. Cada modulo tem exercicios obrigatorios com codigo real, nao cenarios hipoteticos.

---

## Trilha 1 - Fundamentos e Engenharia de Contexto

> De "usar IA pra codar" ate dominar a disciplina que separa amadores de engenheiros.

---

### Modulo 1 - Fundamentos tecnicos de LLMs para engenharia de software
- O que muda quando IA deixa de ser ferramenta de apoio e passa a compor o fluxo de engenharia
- Diferenca entre IA generativa, ML classico e sistemas assistidos por LLM
- Tokens, embeddings, attention, context window, inferencia, temperatura e limites reais dos modelos
- Trade-offs entre qualidade, custo, latencia, previsibilidade e seguranca
- Como escolher modelos: quando usar API, copilotos ou agentes integrados ao editor
- Modelos de referencia em 2026: Claude Opus/Sonnet/Haiku, GPT-5.x, Gemini, modelos open-source

**Exercicios**

- **Lab: Anatomia de um token (30 min)** - Usar tokenizadores (tiktoken, Anthropic tokenizer) para contar tokens de trechos de codigo em Python, TypeScript e Go. Comparar: por que o mesmo codigo tem contagens diferentes? Quanto custa processar 1000 linhas?

- **Lab: Temperatura e determinismo (45 min)** - Executar o mesmo prompt de geracao de codigo 10 vezes com temperatura 0, 0.3, 0.7 e 1.0. Em qual temperatura o codigo e mais previsivel? Em qual e mais criativo? Em qual quebra?

- **Exercicio: Benchmark de modelos (60 min)** - 5 tarefas de engenharia (refatorar funcao, escrever teste, explicar bug, gerar SQL, documentar API) executadas em 3 modelos. Tabela comparativa: qualidade, velocidade, custo, tokens usados.

- **Exercicio: Custo real de um projeto (30 min)** - Calcular custo de API para: 100 code reviews/semana, 50 geracoes de teste/dia, 20 refatoracoes/sprint. Comparar com assinatura de ferramentas (Cursor Pro $20, Claude Max $100, Copilot $10).

---

### Modulo 2 - Prompt Engineering profissional
- Estruturacao de prompts com papel, objetivo, restricoes, contexto e criterios de saida
- Tecnicas para reduzir ambiguidade e alucinacao
- Prompting orientado a tarefas de engenharia: leitura de codigo, refatoracao, documentacao, testes e investigacao de bugs
- Estrategias de validacao de respostas
- Quando prompt engineering resolve e quando ja nao e suficiente
- Chain-of-thought, Structured CoT (SCoT), few-shot e negative space prompting
- TDD Prompting: fornecer o teste primeiro, pedir a implementacao depois
- Prompts como artefatos de codigo: versionamento, testes de regressao, bibliotecas de prompts

**Exercicios**

- **Prompt Kata: Refatoracao (45 min)** - Trecho de codigo legado de 80 linhas com logica misturada. Tres rodadas: (1) prompt ingenuo, (2) prompt com contexto de linguagem/framework/padrao, (3) prompt com SCoT pedindo raciocinio passo a passo. Comparar resultados: tamanho do output, iteracoes, qualidade.

- **Prompt Kata: Debugging (30 min)** - Stack trace real. Tres abordagens: (1) dump direto do erro, (2) code review do codigo que gerou o erro, (3) diagnostico estruturado com contexto + hipotese + codigo + erro. Anotar tentativas de cada abordagem.

- **Prompt Kata: Geracao de testes (60 min)** - Funcao sem testes. Iteracao progressiva: (1) testes basicos, (2) edge cases ("adicione 3 casos limite"), (3) testes negativos explicitamente, (4) testes de integracao separado. Comparar cobertura em cada iteracao.

- **Exercicio: Prompt Debugging (30 min)** - Receber prompts quebrados e diagnosticar: ambiguos demais, sem contexto, contradicoes internas, ruido excessivo. Corrigir cada um e testar.

- **Red Team / Blue Team (45 min)** - Metade da turma escreve prompts ruins intencionalmente, a outra metade corrige. Discussao: o que quebra prompts com mais frequencia?

- **Lab: Biblioteca de Prompts (60 min)** - Criar biblioteca pessoal de 10 prompts testados: code review, geracao de testes, documentacao, refatoracao, debugging, SQL, API design, commit message, PR description, explicacao de codigo. Versionada no git.

---

### Modulo 3 - Context Engineering
- Context engineering como disciplina (nao e so "dar contexto pro modelo")
- As 4 estrategias (Anthropic): Write (persistir), Select (filtrar), Compress (resumir), Isolate (separar)
- CLAUDE.md, .cursorrules, rules files: estruturacao e boas praticas
- Limite pratico: LLMs seguem ~150-200 instrucoes com fidelidade; alem disso, compliance degrada
- Separacao entre instrucao, contexto, memoria operacional e artefatos do projeto
- Skills directories e lazy-loading: contexto ativado por demanda
- Estrategias para repositorios grandes e sistemas legados
- Preservacao de padroes de arquitetura, convencoes internas e estilo do time
- Particionamento de contexto e uso agressivo de /clear entre tarefas
- O paradoxo: mais contexto nem sempre e melhor - filtragem deliberada

**Exercicios**

- **Lab: Autopsia de CLAUDE.md (45 min)** - Tres versoes de CLAUDE.md para o mesmo projeto: (1) vazia, (2) 500+ linhas com excesso de detalhes, (3) ~150 linhas bem estruturada. Executar a mesma tarefa com cada versao. Documentar: diferenca de qualidade, correcoes necessarias, tokens consumidos.

- **Lab: CLAUDE.md para projeto real (90 min)** - Pegar um repositorio open source e escrever CLAUDE.md do zero: (1) arquitetura em 5 frases, (2) comandos essenciais (setup, test, build), (3) restricoes de estilo, (4) armadilhas do projeto ("nunca modifique X diretamente"), (5) testar com 5 tarefas e medir correcoes necessarias.

- **Exercicio: Context Partitioning (60 min)** - Monorepo com frontend, backend e infra: mapear quais contextos isolar, criar CLAUDE.md por pasta vs. raiz, comparar qualidade de output com e sem contexto desnecessario injetado.

- **Lab: Sistema de memoria (120 min)** - Construir mecanismo de memoria persistente: arquivo memory.md com fatos do projeto, script que atualiza apos sessoes importantes, testar se a memoria melhora tarefas subsequentes.

- **Build-Measure-Compare (45 min)** - Mesma tarefa de coding: sem contexto (prompt puro) vs. com CLAUDE.md completo. Cronometrar e documentar a diferenca real em tempo, qualidade e iteracoes.

---

### Modulo 4 - Ferramentas e fluxo de trabalho do dev com IA
- Panorama 2026: Claude Code, Cursor, GitHub Copilot, Windsurf, Codex, Devin
- Claude Code: subagentes paralelos, model overrides, plan mode, 1M tokens de contexto
- Cursor: Composer mode, 8 agentes paralelos, Background Agents, JetBrains support
- GitHub Copilot: Coding Agent (assign Issue -> PR automatico), agent mode no VS Code
- Codex: GPT-5.x, Codex Skills, agentes paralelos, sandbox nativo
- Fluxos para implementacao guiada, debugging, escrita de testes, revisao de PR e documentacao
- Como combinar ferramentas sem duplicar custo e sem perder contexto
- Automacao de tarefas recorrentes no ciclo de desenvolvimento
- Agentmaxxing: multiplos agentes em paralelo em branches separadas

**Exercicios**

- **Lab: Setup completo de ambiente (90 min)** - Configurar Claude Code + CLAUDE.md para um projeto real. Criar regras, testar com 5 tarefas de complexidade crescente, documentar produtividade vs. fazer manual.

- **Lab: Workflow de PR com IA (60 min)** - Fluxo completo end-to-end: (1) receber issue, (2) AI planeja abordagem, (3) implementar com AI, (4) gerar testes, (5) abrir PR com descricao gerada, (6) self-review assistido. Documentar cada passo com prints.

- **Exercicio: Ferramenta certa para cada tarefa (45 min)** - 10 tarefas reais (bug fix, refactor, new feature, migration, doc, test, review, debug, deploy config, API design). Escolher qual ferramenta usar para cada e justificar com trade-offs.

- **Lab: Agentmaxxing (120 min)** - 3 tarefas independentes rodando em paralelo com Claude Code, cada uma em branch separada. Medir throughput total vs. sequencial. Discutir: quando paralelizar funciona e quando cria conflitos de merge.

- **Exercicio: Custo vs. valor (30 min)** - Monitorar uso real de tokens em uma sessao de desenvolvimento de 2h. Calcular custo e comparar com o valor do tempo economizado. A ferramenta se paga?

---

### Modulo 5 - Vibe Coding: da pratica casual a disciplina de engenharia
- Diferenca entre uso casual e uso disciplinado de IA em times reais
- Numeros reais: 80%+ dos devs usam IA; 25% das startups YC W25 com 95%+ codigo gerado por IA
- Riscos quantificados: 45% do codigo gerado por IA tem falhas de seguranca, 2.74x mais vulnerabilidades
- Dados DORA 2025: 90% adocao correlacionou com 9% mais bugs e 91% mais tempo de review
- Como usar IA sem perder governanca tecnica
- Quando aceitar geracao rapida e quando exigir processo, evidencia e validacao
- Criterios para uso responsavel em codigo de producao
- IA e off-limits para: modulos de auth, pagamentos e infra em orgs maduras
- Karpathy 2026: de vibe coding para agentic engineering - a evolucao

**Exercicios**

- **Lab: Vibe Coding controlado (60 min)** - Construir uma feature completa usando APENAS vibe coding: aceitar tudo do AI, sem ler o codigo. Depois: revisar linha a linha. Documentar: funciona? Tem bugs? Tem vulnerabilidades? O codigo e mantivel? Quantos problemas encontrou?

- **Exercicio: Broken Project (90 min)** - Receber um projeto construido com vibe coding puro. Encontrar e corrigir: bugs, code smells, vulnerabilidades de seguranca, logica errada, testes faltando.

- **Exercicio: Mesmo feature, dois modos (120 min)** - Implementar a mesma feature duas vezes: (1) vibe coding puro, (2) spec-driven com review de cada diff. Tabela comparativa: tempo total, qualidade do codigo, bugs encontrados, cobertura de testes, divida tecnica acumulada.

- **Exercicio: Matriz de decisao (30 min)** - Para cada tipo de projeto (MVP, SaaS producao, open source lib, script interno, prototipo de cliente, sistema financeiro), definir: vibe aceitavel, assistido com review, ou 100% humano. Justificar com dados do DORA e riscos reais.

---

## Trilha 2 - Desenvolvimento Agentic e Arquitetura com IA

> Agentes, MCP, RAG e Spec-Driven Development. O kit completo pra construir software com IA de forma estruturada.

---

### Modulo 6 - MCP: Model Context Protocol
- Fundamentos de MCP e por que se tornou infraestrutura (1.864+ servidores registrados)
- Arquitetura: cliente, servidor, transporte
- HTTP como transporte padrao em producao (substituindo stdio)
- MCP Server Cards: .well-known/mcp para descoberta automatica
- Como conectar LLMs a ferramentas, arquivos, terminal, docs e servicos externos
- Estrutura de um servidor MCP: tools, resources, prompts
- Servidores populares: Playwright (browser), GitHub, n8n, Qdrant, databases
- Quando usar tool calling simples, quando usar agentes, e quando evitar ambos
- Riscos operacionais de agentes com acesso a ferramentas reais
- 2026 roadmap: audit trails, SSO, gateways, remote servers

**Exercicios**

- **Projeto: MCP para banco de dados (3h)** - Construir MCP server em Python (FastMCP) que conecta a SQLite. Tools: query_db, list_tables, describe_table, insert_record. Conectar ao Claude e fazer queries em linguagem natural. Meta: perguntar "quais usuarios se cadastraram essa semana?" e obter query SQL + resultado.

- **Projeto: MCP para API externa (2h)** - Wrapar API REST publica (GitHub, OpenWeather, NewsAPI) como MCP server. Mapear endpoints como tools, adicionar rate limiting e cache simples. Discussao: por que documentar bem cada tool e critico pro modelo escolher certo?

- **Projeto: MCP com permissoes (2h)** - MCP server de filesystem com controle de acesso: apenas leitura em /prod, escrita em /workspace. Implementar e testar. Aprender por que permission scoping e seguranca critica.

- **Lab: Compor 3 MCPs (90 min)** - Conectar 3 MCP servers simultaneamente (filesystem + database + GitHub) ao Claude Code. Executar uma tarefa que exige os tres (ex: ler issue do GitHub, consultar dados no DB, gerar arquivo de relatorio). Observar como o modelo decide qual tool usar.

---

### Modulo 7 - Agentes e orquestracao multiagente
- Agentes especializados por dominio: implementacao, revisao, documentacao, testes, investigacao
- Padroes de orquestracao: hierarquico, orchestrator-worker, pipeline workflow
- Pipeline de producao: Feature Author -> Test Generator -> Code Reviewer -> Architecture Guardian -> Security Scanner -> Human Review -> CI/CD
- Frameworks: Anthropic Agent SDK, OpenAI Agents SDK, Google ADK, LangGraph, CrewAI
- Modelos baratos pra triagem (Haiku, mini), modelos capazes pra raciocinio complexo
- Multi-agente vs single-agent: quando a complexidade compensa
- Loops de controle simples vencem sistemas over-engineered em producao real
- Agent Teams no Claude Code: orquestrador + sub-agentes nativos

**Exercicios**

- **Lab: Agente de code review (4h)** - Construir agente que: recebe PR via GitHub API/MCP, analisa diff, gera comentarios categorizados (bugs, estilo, seguranca, performance), posta no PR. Patterns: tool use, structured output, human-in-the-loop antes de postar.

- **Lab: Orquestracao com sub-agentes (6h)** - Pattern orquestrador-trabalhadores: dado um repositorio, gerar documentacao completa. Orquestrador divide em modulos, sub-agente 1 documenta funcoes/classes, sub-agente 2 gera diagrama Mermaid, sub-agente 3 escreve README com exemplos, orquestrador compila e revisa.

- **Lab: Agente com loop de feedback (3h)** - Agente de bug hunting: (1) executa testes, (2) analisa falhas, (3) propoe e aplica correcao, (4) re-executa testes, (5) itera ate passar ou atingir limite de tentativas. Exercicio critico: definir quando o agente deve parar e pedir ajuda humana.

- **Exercicio: Single vs Multi (60 min)** - Mesma tarefa complexa (refatorar modulo + escrever testes + documentar) feita com: (1) um unico agente, (2) pipeline de 3 agentes especializados. Comparar qualidade, tempo, custo e complexidade de setup.

---

### Modulo 8 - Spec-Driven Development com IA
- Como partir de problema, requisitos e design doc antes de sair gerando codigo
- GitHub Spec Kit: 72.7k stars, suporte a 22+ plataformas de agentes
- Uso de IA para decompor escopo, levantar premissas e identificar riscos
- Transformacao de especificacao em plano tecnico executavel
- Geracao orientada por contratos, criterios de aceite e invariantes de negocio
- Spec como contrato executavel: specs alimentam agentes, testes e validacao de CI simultaneamente
- Test-Driven com IA: agente de testes e agente de codigo nao compartilham contexto de implementacao
- Specification Engineering como evolucao do Prompt Engineering
- Ferramentas: GitHub Spec Kit, Amazon Kiro, Tessl
- Como manter alinhamento entre requisito, design e implementacao

**Exercicios**

- **Spec Kata (60 min)** - Ticket real ("adicionar autenticacao OAuth"): (1) AI expande em spec completa (requirements, edge cases, data model, API contract), (2) spec gera implementacao em etapas, (3) comparar com implementacao feita sem spec. Medir: bugs, iteracoes, aderencia ao requisito.

- **Exercicio: ADR para codigo (45 min)** - Architecture Decision Record existente: extrair restricoes, codificar no CLAUDE.md, testar se o AI respeita as decisoes ao gerar codigo. Ex: ADR diz "usamos PostgreSQL, nunca MySQL" - o AI obedece?

- **Lab: OpenAPI para implementacao (90 min)** - Schema OpenAPI dado: (1) gerar handlers de rota, (2) gerar testes de contrato, (3) gerar tipos/interfaces, (4) conectar ao banco. Avaliar: codigo respeita o contrato? O que precisou correcao manual?

- **Projeto: Feature completa spec-driven (4h)** - Do zero: (1) escrever spec em markdown com criterios de aceite, (2) AI gera plano de implementacao, (3) decompor em tasks, (4) implementar task por task com review humano, (5) validar cada task contra criterios da spec. Nenhum codigo aceito sem passar nos criterios.

---

### Modulo 9 - RAG e sistemas com base de conhecimento
- Fundamentos de Retrieval-Augmented Generation
- Quando RAG faz sentido e quando so adiciona complexidade
- RAG vs Long Context (1M+ tokens): trade-offs reais em 2026
- Chunking inteligente: AST boundaries, nao contagem de linhas
- Recursive character splitting (512 tokens, 50-100 overlap) como default validado
- Two-stage retrieval: vector search -> LLM reranking
- Metadata annotation: tags de linguagem, tipo de funcao, dependencias
- Ferramentas: CodeRAG + MCP, code-graph-rag, CocoIndex, Continue.dev, Tree-sitter
- Vector DBs: pgvector, Weaviate, Qdrant, Pinecone - quando usar cada
- CI/CD event -> re-index -> embeddings atualizados -> MCP serve contexto fresco
- O indice e infraestrutura, nao um script que roda uma vez
- 80% das falhas de RAG estao na ingestao, nao no LLM

**Exercicios**

- **Projeto: RAG do zero sem frameworks (4h)** - Python puro para entender cada peca: (1) carregar arquivos .md e .py do repo, (2) chunking 512 tokens com overlap 50, (3) embedding com OpenAI/Ollama, (4) storage em FAISS/ChromaDB, (5) retrieval por similaridade cosine, (6) generation com contexto recuperado. Pergunta obrigatoria de debrief: "onde o seu RAG falhou e por que?"

- **Projeto: Developer Knowledge Base (8h)** - Indexar documentacao interna real (ADRs, READMEs, wikis, PRs, postmortems). Interface de chat que responde: "por que escolhemos Postgres?", "como funciona o deploy?", "qual foi o incidente de novembro?". Demonstrar casos onde RAG acertou E onde alucionou, propor mitigacao.

- **Lab: RAG em codigo (3h)** - Indexar codebase com tree-sitter para chunking semantico por funcao/classe. Agente que responde: "onde e feita a autenticacao?", "mostre todos os usos da funcao X", "explique o fluxo de checkout". Comparar chunking por funcao vs. por caracteres.

- **Exercicio: Avaliacao quantitativa de RAG (60 min)** - Dataset de 20 perguntas com respostas conhecidas. Medir: precision, recall, fidelidade. Iterar chunking e retrieval strategy ate melhorar metricas. Documentar o que mudou em cada iteracao.

---

### Modulo 10 - Refatoracao, legado e evolucao arquitetural com IA
- Leitura assistida de bases grandes e sistemas complexos
- Mapeamento de dependencias, hotspots e pontos de acoplamento
- Golden tests: gerar testes de caracterizacao ANTES de mexer no codigo
- Strangler Fig pattern com IA: migracao incremental segura
- Refatoracao em massa com seguranca - cada passo e um commit testavel
- Uso de IA para modularizacao, reorganizacao de responsabilidades e melhoria de coesao
- Feature slice vs vertical slice
- Avaliacao de trade-offs com apoio de IA em arquiteturas DDD, Hexagonal e Clean
- Modernizacao de stack: migracao de versao, framework e linguagem assistida
- Preparacao de repositorio IA-first para evolucao continua

**Exercicios**

- **Projeto: Strangler Fig com IA (4h)** - Modulo legado monolitico: (1) AI mapeia dependencias e identifica fronteiras, (2) gerar golden tests que capturam comportamento atual sem alterar nada, (3) refatorar incrementalmente validando contra golden tests, (4) cada passo = commit testavel. Se teste quebrar, rollback.

- **Exercicio: Modernizacao de stack (3h)** - Codigo em versao antiga (jQuery > React, Python 2 > 3, Express 3 > 5): (1) AI analisa e gera plano de migracao com riscos mapeados, (2) humano valida e prioriza, (3) migrar uma funcionalidade por vez, (4) testar cada etapa antes de seguir.

- **Exercicio: Debt Discovery (45 min)** - AI audita codebase e gera relatorio de divida tecnica: duplicacao de logica, funcoes com responsabilidades multiplas, dependencias circulares, codigo morto. Comparar com ferramentas tradicionais (CodeScene, SonarQube). Discutir falsos positivos.

- **Lab: Mapeamento de codebase desconhecido (60 min)** - Repo de 50+ arquivos que o aluno nunca viu. Usar AI para mapear arquitetura em 30 min: diagrama Mermaid, modulos principais, entrypoints, pontos de risco. Depois comparar com explorar manualmente. Quanto tempo economizou? Acertou a arquitetura?

---

## Trilha 3 - Qualidade, Seguranca e Adocao em Escala

> De codigo individual pra padrao de time. Qualidade, governanca e metricas que importam.

---

### Modulo 11 - Padroes modernos para uso sustentavel de LLMs
- Diferenca entre contexto solto, rules, skills, agents.md e padroes reutilizaveis
- Como encapsular comportamento de IA de forma previsivel
- Regras, convencoes e contratos de uso entre humanos e agentes
- Reutilizacao de prompts e contextos em escala
- Skills como unidades reutilizaveis de capacidade do agente
- Trade-offs entre flexibilidade, manutencao e consistencia do comportamento dos agentes
- CLAUDE.md/rules como assets de time, versionados e revisados
- Padronizacao cross-team: formato unico na organizacao

**Exercicios**

- **Lab: Skill builder (90 min)** - Criar 3 skills reutilizaveis para Claude Code: (1) skill de code review com checklist customizado, (2) skill de geracao de testes seguindo padrao do time, (3) skill de documentacao com template especifico. Testar cada uma em 3 cenarios diferentes.

- **Exercicio: Prompt Library versionada (60 min)** - Biblioteca de 15 prompts para o time: cada um com nome, descricao, template, exemplos de uso e criterios de validacao. Tudo no git com CHANGELOG. Revisar em pair como se fosse codigo.

- **Exercicio: Contrato humano-agente (45 min)** - Definir por escrito: quais decisoes o agente pode tomar sozinho, quais precisam de aprovacao, quais sao proibidas. Implementar como guardrails no CLAUDE.md. Testar: o agente respeita os limites?

- **Lab: Convencoes do time para rules (90 min)** - Pegar style guide e architecture docs existentes, traduzir em regras que o AI segue automaticamente. Testar com 5 tarefas e medir aderencia (% de outputs que seguem as regras sem correcao).

---

### Modulo 12 - Qualidade de software com IA no ciclo completo
- Geracao e revisao de testes unitarios, integracao e contratos
- Critica automatizada de codigo e apoio a code review
- AI code review em producao: CodeRabbit (2M+ repos), PR-Agent, Anthropic Code Review, Snyk Code
- Uso de IA para detectar inconsistencias, gaps de cobertura e riscos de regressao
- Guardrails para impedir mudancas frageis
- Rastreabilidade entre intencao, implementacao e evidencia de qualidade
- Times que shipam mais rapido mas quebram mais: o custo oculto sem review/testes
- IA no CI/CD: pipelines self-correcting que re-implementam em vez de so falhar
- Mutation testing + AI: medir robustez real dos testes

**Exercicios**

- **Lab: Test-Driven AI (60 min)** - Workflow invertido: (1) spec da funcao em linguagem natural, (2) AI gera testes ANTES do codigo, (3) revisar testes (ponto critico!), (4) usar testes como spec para gerar implementacao, (5) iterar ate todos passarem. Licao: qualidade dos testes depende da qualidade da spec.

- **Exercicio: Security scan com IA (45 min)** - Codigo com vulnerabilidades intencionais (SQL injection, credenciais hardcoded, XSS, auth quebrada). AI identifica e corrige. Depois rodar Semgrep/Bandit. Comparar: o que cada um pegou que o outro nao pegou? Licao: AI nao substitui ferramentas deterministicas de seguranca.

- **Lab: Pipeline de code review (90 min)** - Configurar em cada PR: AI para revisao semantica (logica, architecture smells) + linters para revisao sintatica + report combinado. Em 5 PRs reais, documentar o que a IA encontrou que o linter nao encontraria e vice-versa.

- **Exercicio: Mutation testing (60 min)** - Gerar suite de testes com AI, rodar mutation testing (Stryker/Pitest). Quantos mutantes sobrevivem? Iterar com AI para matar sobreviventes. Meta: mutation score > 80%.

- **Build-Measure-Compare: Testes (45 min)** - Mesma funcao: escrever testes manualmente vs. gerar com AI. Comparar cobertura, edge cases capturados, tempo gasto. Tabela final mostrando onde cada abordagem ganha.

---

### Modulo 13 - Seguranca, governanca e uso corporativo
- Prompt injection: o vetor de ataque definidor de 2026
- Memory poisoning: informacao maliciosa persistente na memoria do agente
- Embedding-level injection: envenenamento de pipelines RAG
- Tool misuse e agent-to-agent attack vectors
- Governance-containment gap: 58% monitoram, so 37% contem
- EU AI Act: fases de enforcement rolando em 2025-2026
- "Rules fail at the prompt, succeed at the boundary" (MIT Tech Review)
- Input/output validation, sandboxing e permission scoping
- Anonimizacao, escopo minimo de contexto e separacao de dados sensiveis
- Politicas de uso para times e empresas

**Exercicios**

- **Lab: Prompt injection ofensivo/defensivo (60 min)** - Construir chatbot com system prompt. Metade da turma ataca (injecao direta, indireta, via dados), outra metade defende. Rodadas de 10 min com rotacao. Documentar: quais ataques funcionaram, quais defesas seguraram.

- **Exercicio: Auditoria de seguranca de agente (45 min)** - Agente com acesso a filesystem, banco de dados e API externa. Mapear TODOS os riscos (leitura indevida, escrita destrutiva, exfiltracao de dados). Definir permissoes minimas. Implementar guardrails. Testar se os guardrails seguram.

- **Exercicio: Politica de uso para time (60 min)** - Escrever politica completa: o que pode ir para API, o que nao pode, classificacao de dados (publico/interno/confidencial/restrito), tarefas AI-appropriate vs. human-required, como auditar, como medir compliance.

- **Lab: Data classification pipeline (90 min)** - Construir filtro pre-API que analisa codigo antes de enviar: detecta secrets (.env, tokens, passwords), credenciais, PII. Se encontrar: bloqueia ou anonimiza. Implementar como git pre-commit hook. Testar com 10 arquivos reais.

- **Exercicio: Incident response com AI (45 min)** - Cenario: agente cometeu codigo com credencial vazada em PR publico. Simular: (1) detectar, (2) revogar credencial, (3) limpar historico git, (4) post-mortem, (5) implementar controle para nao repetir.

---

### Modulo 14 - Estrategia de adocao em times de engenharia
- Numeros de marco 2026: 92% dos devs usam IA, 41% do codigo e gerado por IA
- Produtividade medida: 3.6h/semana economizadas, +60% PRs mergeados, -24% cycle time
- Quality tradeoffs: codigo IA-assisted aumenta issues 1.7x sem governanca adequada
- Metricas: DORA + SPACE + DX Core 4 + Flow metrics
- O modelo que funciona: read-only primeiro, write depois
- Como sair do uso individual e criar padrao de time
- Criacao de convencoes, bibliotecas de contexto e fluxos reutilizaveis
- Quais tarefas devem ser assistidas, automatizadas ou permanecer humanas
- Onboarding que ensina context engineering, nao so "como usar Copilot"
- O bloqueio real: skill gap, nao tecnologia (Deloitte 2026)

**Exercicios**

- **Exercicio: Plano de adocao em 90 dias (90 min)** - Plano completo para time de 8 devs: semana 1-4 (read-only: explicacao, doc, testes), semana 5-8 (assistido com review obrigatorio), semana 9-12 (agentes com guardrails definidos). Metricas de sucesso para cada fase. Criterios de go/no-go entre fases.

- **Lab: Onboarding kit completo (120 min)** - Montar kit para novo dev: CLAUDE.md padrao do time, biblioteca de prompts testados, lista de do/don't, fluxo de trabalho documentado passo a passo, checklist de review para codigo gerado por IA, FAQ com erros comuns.

- **Exercicio: Matriz de decisao por tarefa (45 min)** - Para cada tipo de tarefa do time (bug fix, feature, refactor, migration, doc, test, review, deploy, incident response), classificar: AI-appropriate, human-required, ou hibrido. Justificar cada decisao com dados e riscos.

- **Exercicio: ROI real (60 min)** - Calcular ROI com dados reais ou simulados: custo das ferramentas + tokens vs. horas dev economizadas + bugs evitados + tempo de review reduzido. Montar apresentacao de caso de negocio para lideranca tecnica em 5 slides.

- **Lab: Retrospectiva de AI adoption (45 min)** - Simular retrospectiva de time apos 3 meses usando IA: o que funcionou, o que nao funcionou, o que surpreendeu, o que deve mudar. Template estruturado com dados quantitativos.

---

### Modulo 15 - Projeto aplicado integrador (Capstone)
- Do design doc a implementacao assistida por IA
- Planejamento de uma feature real com especificacao, contexto, execucao e validacao
- Uso combinado de prompting, contexto estruturado, agentes, MCP e revisao
- Aplicacao de qualidade, seguranca e governanca
- Pipeline multiagente completo: spec -> code gen -> test gen -> review -> deploy
- Entrega final com documentacao tecnica e criterios claros de aceite

**Opcoes de Capstone (escolher 1)**

- **Opcao A: AI Dev Toolkit Pessoal (2 semanas)** - Assistente de desenvolvimento pessoal combinando: MCP server para seu repo principal, RAG sobre documentacao interna, agente de code review customizado, sistema de memoria com checkpoints. Entrega: ferramenta real que o aluno vai usar no dia a dia, nao exercicio descartavel.

- **Opcao B: Pipeline de modernizacao automatizado (2 semanas)** - Sistema que, dado repo legado: (1) analisa e mapeia codebase (agente de discovery), (2) gera relatorio de divida tecnica com priorizacao, (3) propoe plano de migracao em etapas, (4) executa primeira etapa com supervisao humana, (5) gera testes de regressao automaticamente.

- **Opcao C: Dev Knowledge Assistant para equipe (2 semanas)** - RAG + agentes para time real: indexa documentacao, PRs, ADRs, postmortems. Interface via Slack ou Telegram. Responde perguntas tecnicas com citacao de fontes. Sabe quando nao sabe e diz isso. Aprende com feedback (thumbs up/down).

**Criterios de avaliacao**
- Funciona e resolve um problema real (nao e toy project)
- Codigo revisado (nao vibe coded)
- Testes automatizados com cobertura minima 70%
- Documentacao tecnica: ADR, README, diagramas
- Seguranca e governanca aplicadas (sem secrets, com permissoes)
- Apresentacao de 15 minutos explicando decisoes tecnicas e trade-offs

---

## Resumo

| | Trilha 1 | Trilha 2 | Trilha 3 |
|---|---|---|---|
| **Tema** | Fundamentos e Contexto | Agentic e Arquitetura | Qualidade e Escala |
| **Modulos** | 5 | 5 | 5 |
| **Foco** | Dominar a base | Construir com IA | Produzir em time |
| **Perfil** | Dev que quer usar IA direito | Dev que quer arquitetar com IA | Tech lead / eng manager |
| **Exercicios** | ~20 | ~20 | ~18 |

**Total: 3 trilhas, 15 modulos, ~100 topicos, 55+ exercicios praticos**

Orientacao: 60% pratica, 40% conceito. Codigo real, nao hipotetico. Dados atualizados para marco de 2026.

---

## Referencias

- Anthropic: Context Engineering for AI Agents, Claude Code Best Practices, Agent SDK
- DORA 2025 Report: AI adoption metrics and quality tradeoffs
- Thoughtworks: Spec-Driven Development (2025)
- Gartner: Context Engineering definition
- Deloitte: State of AI in the Enterprise 2026
- ACM: Structured Chain-of-Thought for Code Generation (2026)
- Karpathy: Vibe Coding (2025), Agentic Engineering (2026)
- MCP Roadmap 2026, Microsoft MCP for Beginners
- RAG Chunking Strategies Benchmark Guide 2026
- GitHub Spec Kit, Amazon Kiro
- CodeRabbit, PR-Agent, Snyk Code
- MIT Tech Review: AI Security boundaries
- EU AI Act enforcement timeline
