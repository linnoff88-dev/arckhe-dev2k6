# Conteúdo do Curso — Versêo Limpa e Avançada

## Módulo 1 — Fundamentos técnicos de LLMs para engenharia de software
- O que muda quando IA deixa de ser ferramenta de apoio e passa a compor o fluxo de engenharia
- Diferença entre IA generativa, ML clássico e sistemas assistidos por LLM
- Tokens, embeddings, attention, context window, inferência, temperatura e limites reais dos modelos
- Trade-offs entre qualidade, custo, latência, previsibilidade e segurança
- Como escolher modelos e quando usar API, copilotos ou ferramentas integradas ao editor

## Módulo 2 — Prompt Engineering para uso profissional
- Estruturaçêo de prompts com papel, objetivo, restrições, contexto e critérios de saída
- Técnicas para reduzir ambiguidade e alucinaçêo
- Prompting orientado a tarefas de engenharia: leitura de código, refatoraçêo, documentaçêo, testes e investigaçêo de bugs
- Estratégias de validaçêo de respostas
- Quando prompt engineering resolve e quando já nêo é suficiente

## Módulo 3 — Context Engineering
- Como organizar contexto para aumentar precisêo e utilidade das respostas
- Separaçêo entre instruçêo, contexto, memória operacional e artefatos do projeto
- Como montar contexto reutilizável para repositórios grandes e sistemas legados
- Estratégias para preservar padrões de arquitetura, convenções internas e estilo do time
- Limites de contexto e técnicas de particionamento

## Módulo 4 — Vibe Coding vs Desenvolvimento Assistido por IA
- Diferença entre uso casual e uso disciplinado de IA em times reais
- Como usar IA sem perder governança técnica
- Quando aceitar geraçêo rápida e quando exigir processo, evidência e validaçêo
- Como transformar a IA em acelerador de engenharia, e nêo em fonte de débito técnico
- Critérios para uso responsável em código de produçêo

## Módulo 5 — Ferramentas e fluxo de trabalho do dev com IA
- Uso prático de IDEs e assistentes como Cursor, Copilot, Claude Code e ferramentas similares
- Fluxos para implementaçêo guiada, debugging, escrita de testes, revisêo de PR e documentaçêo
- Como combinar ferramentas diferentes sem duplicar custo e sem perder contexto
- Estratégias para produtividade individual e para padronizaçêo em equipe
- Automaçêo de tarefas recorrentes no ciclo de desenvolvimento

## Módulo 6 — MCPs, integraçêo com ferramentas e agentes
- Fundamentos de Model Context Protocol
- Como conectar LLMs a ferramentas, arquivos, terminal, docs e serviços externos
- Estrutura de um servidor MCP e desenho de capacidades
- Quando usar tool calling simples, quando usar agentes, e quando evitar ambos
- Agentes especializados por domínio: implementaçêo, revisêo, documentaçêo, testes e investigaçêo
- Riscos operacionais de agentes com acesso a ferramentas reais

## Módulo 7 — Padrões modernos para uso sustentável de LLMs
- Diferença entre contexto solto, rules, skills, agents.md e padrões reutilizáveis
- Como encapsular comportamento de IA de forma previsível
- Regras, convenções e contratos de uso entre humanos e agentes
- Reutilizaçêo de prompts e contextos em escala
- Trade-offs entre flexibilidade, manutençêo e consistência do comportamento dos agentes

## Módulo 8 — Spec-Driven Development com IA
- Como partir de problema, requisitos e design doc antes de sair gerando código
- Uso de IA para decompor escopo, levantar premissas e identificar riscos
- Transformaçêo de especificaçêo em plano técnico executável
- Geraçêo orientada por contratos, critérios de aceite e invariantes de negócio
- Como usar IA para manter alinhamento entre requisito, design e implementaçêo

## Módulo 9 — Refatoraçêo, legado e evoluçêo arquitetural com IA
- Leitura assistida de bases grandes e sistemas complexos
- Mapeamento de dependências, hotspots e pontos de acoplamento
- Refatoraçêo em massa com segurança
- Uso de IA para modularizaçêo, reorganizaçêo de responsabilidades e melhoria de coesêo
- Feature slice vs vertical slice
- Avaliaçêo de trade-offs com apoio de IA em arquiteturas DDD, Hexagonal e Clean
- Preparaçêo de repositório IA-first para evoluçêo contínua

## Módulo 10 — Qualidade de software com IA no ciclo completo
- Geraçêo e revisêo de testes unitários, integraçêo e contratos
- Crítica automatizada de código e apoio a code review
- Uso de IA para detectar inconsistências, gaps de cobertura e riscos de regressêo
- Guardrails para impedir mudanças frágeis
- Como manter rastreabilidade entre intençêo, implementaçêo e evidência de qualidade

## Módulo 11 — RAG e sistemas com base de conhecimento
- Fundamentos de Retrieval-Augmented Generation
- Quando RAG faz sentido e quando só adiciona complexidade
- Construçêo de pipelines RAG em aplicações
- Indexaçêo, chunking, embeddings, retrieval e re-ranking
- Qualidade de recuperaçêo, precisêo de contexto e avaliaçêo de respostas
- Padrões de uso de RAG em software interno, suporte, documentaçêo e operaçêo

## Módulo 12 — Segurança, governança e uso corporativo
- Vazamento de dados, prompt injection, jailbreaks e superfícies de risco
- Controles para uso de IA em ambientes corporativos
- Anonimizaçêo, escopo mínimo de contexto e separaçêo de dados sensíveis
- Permissões, auditoria e rastreabilidade de agentes
- Políticas de uso para times e empresas
- Como equilibrar velocidade com conformidade e segurança

## Módulo 13 — Estratégia de adoçêo em times de engenharia
- Como sair do uso individual e criar padrêo de time
- Criaçêo de convenções, bibliotecas de contexto e fluxos reutilizáveis
- Métricas de adoçêo, produtividade, qualidade e ROI
- Quais tarefas devem ser assistidas, automatizadas ou permanecer humanas
- Como ensinar a IA a respeitar o modo de trabalho da equipe

## Módulo 14 — Projeto aplicado
- Do design doc à implementaçêo assistida por IA
- Planejamento de uma feature real com especificaçêo, contexto, execuçêo e validaçêo
- Uso combinado de prompting, contexto estruturado, agentes e revisêo
- Aplicaçêo de qualidade, segurança e governança
- Entrega final com documentaçêo técnica e critérios claros de aceite

## Resumo
Essa formaçêo é orientada para engenharia de software assistida por IA em nível avançado, cobrindo fundamentos de LLMs, prompting, contexto estruturado, agentes, MCP, RAG, qualidade, arquitetura, segurança e adoçêo em times reais.
