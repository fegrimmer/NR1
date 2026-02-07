# Guia da Documentação – NR1 Inteligente

## 1. Objetivo

Este documento descreve como a documentação do projeto NR1 Inteligente está organizada,
qual o papel de cada conjunto de artefatos e como ela deve ser utilizada e evoluída
ao longo do ciclo de vida do projeto.

O objetivo é garantir:
- clareza de leitura
- fonte única de verdade
- rastreabilidade de decisões
- evolução incremental sem perda de contexto

---

## 2. Princípios da Documentação

A documentação do NR1 Inteligente segue os seguintes princípios:

- documentação viva, versionada em Git
- separação clara entre visão, funcional, arquitetura e técnica
- decisões explícitas e registradas (ADR)
- evitar duplicidade de informação
- evitar documentos monolíticos
- cada documento tem um propósito claro

Nenhuma decisão relevante deve existir apenas em conversas ou memória das pessoas.

---

## 3. Estrutura Geral do Diretório `/docs`

A documentação está organizada da seguinte forma:

docs/
├── 00_overview
├── 01_business
├── 02_functional
├── 03_architecture
├── 04_technical
├── 05_security_compliance
├── 06_delivery
└── 07_decisions


Cada diretório representa uma visão específica do projeto.

---

## 4. Visão Geral dos Diretórios

### 4.1 `00_overview`
Documentos introdutórios e de contexto.

Usar para:
- entender o projeto rapidamente
- compreender o problema e a proposta
- saber como ler a documentação

Não usar para:
- requisitos
- arquitetura
- decisões técnicas

---

### 4.2 `01_business`
Visão de negócio e escopo.

Usar para:
- objetivos de negócio
- público-alvo
- limites do projeto
- valor entregue

---

### 4.3 `02_functional`
Especificação funcional e operacional.

Usar para:
- requisitos funcionais
- fluxos e casos de uso
- formulários e avaliações
- matriz CRUD

Fonte de verdade para o **comportamento do sistema**.

---

### 4.4 `03_architecture`
Arquitetura do sistema em nível conceitual.

Usar para:
- arquitetura lógica
- arquitetura de dados
- arquitetura de integração

Não contém decisões de stack ou infraestrutura física.

---

### 4.5 `04_technical`
Visão técnica e restrições não funcionais.

Usar para:
- requisitos não funcionais
- contratos de API (conceituais)
- visão técnica geral

Serve como ponte entre arquitetura e desenvolvimento.

---

### 4.6 `05_security_compliance`
Segurança, privacidade e conformidade.

Usar para:
- LGPD
- políticas de acesso
- confidencialidade
- requisitos regulatórios

---

### 4.7 `06_delivery`
Entrega e planejamento.

Usar para:
- definição de MVP
- roadmap
- planejamento incremental

---

### 4.8 `07_decisions`
Decisões arquiteturais e técnicas.

Usar para:
- registrar decisões importantes
- explicar o porquê das escolhas
- manter histórico de alternativas

Cada decisão relevante deve gerar um ADR.

---

## 5. Ordem Recomendada de Leitura

Para novos leitores, recomenda-se a seguinte sequência:

1. `00_overview/01_project_overview.md`
2. `00_overview/02_documentation_guide.md`
3. `02_functional/01_functional_specification.md`
4. `02_functional/02_functional_flows.md`
5. `03_architecture/02_logical_architecture.md`
6. `04_technical/03_non_functional_requirements.md`

Essa ordem reduz ruído e acelera entendimento.

---

## 6. Fonte Única de Verdade

- A documentação em `/docs` é a fonte única de verdade do projeto
- Nenhuma informação relevante deve existir apenas fora do repositório
- Conversas devem resultar em atualização documental quando aplicável

---

## 7. Evolução da Documentação

A documentação evolui de forma incremental:

- ajustes e correções → novos commits
- mudanças relevantes → novas versões
- decisões estruturais → novos ADRs
- versões consolidadas → novas tags Git

Evitar alterações retroativas em versões já tagueadas.

---

## 8. Versionamento

A documentação é versionada via tags Git.

- `v0.x.x` → versões iniciais e evolutivas
- cada tag representa um baseline estável
- versões antigas permanecem acessíveis para rastreabilidade

---

## 9. Boas Práticas

- escrever de forma clara e objetiva
- evitar jargões desnecessários
- não misturar visões em um mesmo documento
- manter consistência de termos
- revisar documentos impactados por mudanças

---

## 10. Considerações Finais

Este guia deve ser respeitado por todos os envolvidos no projeto.
Ele existe para proteger a clareza, a consistência e a qualidade do NR1 Inteligente
ao longo de sua evolução.
