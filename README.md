# Site Institucional + Blog — Segurança do Trabalho (SST)
[![Card do Meu Repositório](https://vercel.app)](https://github.com/ivossgh/searchAI)

> **Status:** 🟡 Em planejamento / etapa inicial — arquitetura e escopo definidos, execução ainda não iniciada.

Projeto de site institucional com blog para empresa de Segurança do Trabalho (SST), estruturado com estratégia dupla de SEO tradicional e AEO/GEO (Answer Engine Optimization / Generative Engine Optimization) — otimização para ser citado por assistentes de IA como ChatGPT, Gemini, Perplexity e Google AI Mode, além dos buscadores tradicionais.

## Sumário

- [Problema](#problema)
- [Solução](#solução)
  - [Visão geral da arquitetura](#visão-geral-da-arquitetura)
  - [Stack técnica](#stack-técnica)
  - [Estratégia de conteúdo](#estratégia-de-conteúdo)
  - [Ferramenta de cotação (calculadora)](#ferramenta-de-cotação-calculadora)
- [Critérios de validação](#critérios-de-validação)
- [Roadmap](#roadmap)
- [Status atual](#status-atual)
- [Decisões em aberto](#decisões-em-aberto)

## Problema

Empresas de consultoria em Segurança do Trabalho vivem de indicação e prospecção ativa, com pouca ou nenhuma presença digital estruturada. Isso gera três dores concretas:

1. **Dependência de canais caros ou instáveis** (indicação, prospecção fria) para gerar novos contratos, sem um canal de aquisição orgânico e escalável.
2. **Baixa visibilidade em buscas técnicas** — quando um potencial cliente pesquisa sobre PGR, PCMSO ou uma NR específica, quem aparece geralmente são portais genéricos ou concorrentes com mais investimento em marketing, não necessariamente com mais competência técnica.
3. **Um novo canal de descoberta emergente e ainda não disputado**: assistentes de IA (ChatGPT, Gemini, Perplexity, Google AI Mode) já respondem perguntas sobre compliance trabalhista diretamente ao usuário, citando fontes. Empresas de nicho técnico que não estruturam conteúdo pensando nisso ficam de fora dessa nova camada de descoberta — que tende a crescer.

O desafio do projeto é validar se uma estratégia de conteúdo técnico bem estruturado, combinada com sinais de confiança e otimização para IA, consegue gerar leads qualificados de forma sustentável, sem depender de mídia paga.

## Solução

### Visão geral da arquitetura

A estratégia é organizada em 4 camadas complementares:

| Camada | Objetivo |
|---|---|
| 1. Google Meu Negócio | Presença local e sinais de confiança básicos|
| 2. Conteúdo citável | Páginas-pilar técnicas, estruturadas para responder perguntas reais do público-alvo |
| 3. Sinais técnicos de confiança | Schema markup (JSON-LD), estrutura semântica, autoria técnica visível (E-E-A-T) |
| 4. Distribuição/citação | Monitoramento de aparição em buscadores e IAs, ajuste iterativo |

As camadas 2 e 3 não são sequenciais — a Camada 3 (schema) é embutida no template desde o início, para que toda página nasça com o sinal técnico correto, sem retrabalho.

### Stack técnica

- **Site + Blog:** [Astro](https://astro.build/) (SSG) + CMS headless — geração estática, performance alta, ideal para conteúdo SEO/AEO-first.
- **Formulário de contato:** client-side, sem backend — link direto para WhatsApp via querystring.
- **Ferramenta de cotação (calculadora):** API em Java/Spring Boot — isolada como serviço, entra em fase 2 (ver [seção específica](#ferramenta-de-cotação-calculadora)).

A escolha por uma arquitetura híbrida (site estático + API isolada) evita usar uma stack pesada para servir conteúdo estático, e concentra a lógica de negócio real (regras de precificação) em Java, alinhado aos meus objetivos de aprofundamento técnico em java.

### Estratégia de conteúdo

O MVP de conteúdo é definido por cobertura de tópicos, não por volume:

- 8 a 12 páginas-pilar (cornerstone), uma por serviço/tema central (PGR, PCMSO, laudos técnicos, NRs mais relevantes para o público-alvo).
- Cada página-pilar inclui: FAQ estruturado e extraível, dados concretos, autoria técnica visível.
- Sem meta de "quantidade de posts" — o escopo é considerado coberto quando o mapa de perguntas reais do público-alvo estiver respondido, não quando um número arbitrário de artigos for atingido.

### Ferramenta de cotação (calculadora)

Formulário dinâmico multi-etapas que, ao final, apresenta uma faixa de valor estimada para o serviço (PGR, PCMSO, laudo específico) com base em porte da empresa, número de funcionários e complexidade/grau de risco. O fluxo termina com CTA direto para WhatsApp.

Função dupla:
- Ajuda na jornada de compra, dando transparência de custo antes do contato.
- Filtra leads frios — quem chega ao WhatsApp já passou por uma pré-qualificação de orçamento.

Esta feature está condicionada a uma tabela de precificação validada com o especialista de SST antes da implementação — não entra no MVP inicial.

## Critérios de validação

Checkpoint fixado para o dia 90 após o lançamento, com métricas definidas antes do início (para evitar viés de avaliação):

**Leading indicators (semanas 4–8):**
- Indexação completa das páginas-pilar no Google Search Console.
- Impressões nas queries-alvo.
- Teste manual periódico: verificação se o site é citado em respostas de ChatGPT, Perplexity, Gemini e Google AI Mode para as 10–15 perguntas-alvo do nicho.

**Lagging indicators (semanas 10–16):**
- Sessões orgânicas em queries não-branded.
- Leads via formulário/WhatsApp atribuíveis a tráfego orgânico.

**Piso mínimo para continuar investindo:** ≥30–40% das queries-alvo com alguma citação/menção de IA até o dia 90 **e** pelo menos 1–2 leads qualificados atribuíveis a orgânico no mesmo prazo. Abaixo disso, a estratégia de conteúdo/distribuição é revisada.

## Roadmap

- [ ] Semana 1–2 — Setup do projeto Astro + template com schema markup embutido + Google Meu Negócio
- [ ] Semana 3–8 — Produção das páginas-pilar (mapa de tópicos, redação, validação técnica com especialista SST)
- [ ] Dia 90 — Checkpoint de tração (ver [critérios de validação](#critérios-de-validação))
- [ ] Fase 2 (condicional) — Ferramenta de cotação em Java/Spring Boot, após validação da tabela de precificação

## Status atual

Projeto em fase de planejamento. Arquitetura, stack e critérios de sucesso já estão definidos; execução (setup do repositório, template e primeiras páginas) ainda não foi iniciada.

## Decisões em aberto

- Definição final do mapa de tópicos-chave (perguntas reais do público-alvo que viram páginas-pilar).
- Validação da tabela de precificação para a ferramenta de cotação, junto ao especialista técnico em SST.
- Escolha do CMS headless a ser usado com o Astro.
