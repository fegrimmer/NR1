# Arquitetura Lógica

## 1. Objetivo

Este documento descreve a arquitetura lógica do NR1 Inteligente, apresentando os principais módulos do sistema, suas responsabilidades, fronteiras e interações.

A arquitetura lógica deve suportar a NR-01 como processo contínuo, estruturado em três fases:
1. Análise de Maturidade Organizacional
2. Identificação dos Riscos Psicossociais
3. Gerenciamento e Monitoramento dos Ciclos Psicossociais

O desenho privilegia escalabilidade funcional, rastreabilidade, auditabilidade e integração com sistemas de SST, especialmente SOC e SGG.

---

## 2. Princípios Arquiteturais

- NR1 first: todo o núcleo do sistema deve atender diretamente a NR-01
- Documento vivo e rastreabilidade: auditoria e histórico como requisitos nativos
- Modularidade por domínio: módulos com responsabilidades claras e baixo acoplamento
- Orquestração interna: o NR1 Inteligente orquestra a NR-01 e integra com sistemas externos
- Integração resiliente: filas, reprocessamento e logs completos de integração
- Segurança e LGPD: segregação por empresa, controle de acesso granular, mascaramento de dados sensíveis

---

## 3. Visão de Módulos

A arquitetura lógica é composta pelos seguintes módulos:

### 3.1 Identidade e Acesso (IAM)
Responsável por autenticação e autorização.

Funções:
- login e sessão
- gestão de perfis e permissões (RBAC)
- segregação multiempresa
- trilha de auditoria de acesso

Perfis típicos:
- Administrador do sistema
- Gestor do cliente (RH, QSMS)
- Psicólogo
- Engenheiro de Segurança
- Médico do Trabalho
- Operação administrativa
- Auditor (opcional)

---

### 3.2 Cadastro Organizacional e Hierarquia
Responsável pelo cadastro e gestão da estrutura organizacional.

Entidades:
- Instituição
- Unidade
- Setor
- Cargo
- Hierarquia

Funções:
- CRUD completo
- importação e sincronização com SOC
- associação de colaboradores à hierarquia

---

### 3.3 Módulo de Maturidade Organizacional (Fase 1)
Responsável por executar a fase de análise de maturidade.

Funções:
- checklist de maturidade
- coleta e registro de indicadores organizacionais
- gestão de entrevistas (registro, armazenamento, atas)
- consolidação de variáveis organizacionais
- geração de evidências da fase 1

Saídas:
- perfil de maturidade por empresa e por unidade
- indicadores consolidados para cruzamento com fase 2

---

### 3.4 Motor de Formulários e Instrumentos
Responsável por definir, versionar e executar formulários e instrumentos.

Funções:
- criação e parametrização de formulários
- versionamento de instrumentos
- regras de validação e obrigatoriedade
- publicação por público e contexto (setor, cargo, evento)
- registro auditável de respostas

Observação:
Este módulo sustenta tanto a aplicação de questionários psicossociais quanto formulários operacionais do processo NR-01 (pré e pós atividade crítica, ouvidoria, triagens).

---

### 3.5 Coleta e Aplicação de Avaliações (Fase 2)
Responsável pela execução da fase 2 de identificação.

Funções:
- seleção de instrumentos aceitos pelo CFP
- gestão de convocações e janelas de aplicação
- aplicação por setor, cargo, grupos homogêneos
- coleta de respostas, normalização e consolidação

Saídas:
- datasets consolidados por empresa, unidade, setor e cargo
- evidências auditáveis de aplicação

---

### 3.6 Motor de Análise e Cruzamento (Fase 1 + Fase 2)
Responsável por cruzar percepções com contexto organizacional para sustentar avaliação de risco.

Funções:
- correlacionar respostas com indicadores de maturidade
- identificar discrepâncias (percepção x evidência)
- gerar insumos para classificação de risco (probabilidade e severidade)
- produzir visões por setor e por grupo

Observação:
Este módulo não substitui decisão técnica. Ele gera recomendações e evidências para especialistas.

---

### 3.7 Gestão de Riscos Psicossociais (Registro e Classificação)
Responsável por registrar riscos psicossociais como objetos de domínio.

Funções:
- criação de riscos por fator, setor, cargo ou empresa
- registro de probabilidade, severidade e nível de risco
- justificativas e evidências associadas
- versionamento do risco ao longo do tempo
- associação com plano de ação e monitoramento

---

### 3.8 Validação Técnica e Emissão de Documentos (Engenharia)
Responsável pelo fluxo do engenheiro de segurança.

Funções:
- validação e autorização técnica do diagnóstico
- definição e ajuste de probabilidade e severidade
- formalização do nível de risco
- emissão de documentos técnicos e avaliações ergonômicas
- trilha de auditoria de aprovação e versões

---

### 3.9 Gestão Clínica e PCMSO (Fase 3)
Responsável por conectar riscos psicossociais às rotinas de saúde ocupacional.

Funções:
- matriz parametrizada: risco x testes recomendados x contexto (admissional, periódico, demissional)
- disparo de avaliações complementares conforme riscos
- registro de resultados e evidências
- suporte a clínicas sem psicólogo presencial (laudos assinados)
- integração com SOC e SGG para viabilizar execução no contexto dos exames

---

### 3.10 Laudos e Relatórios (com apoio de IA)
Responsável por produzir relatórios e laudos.

Tipos:
- relatórios populacionais (empresa, unidade, setor, cargo)
- relatórios individuais (quando aplicável e permitido)
- laudos técnicos editáveis por profissionais
- laudos por setor e por grupos

Funções:
- correção automatizada de instrumentos
- aplicação de pesos e critérios
- geração de texto base e análises com apoio de IA
- garantia de edição humana e validação formal
- assinatura e versionamento

---

### 3.11 Ouvidoria e Canais Sensíveis
Responsável por registro e tratativa de denúncias e reclamações.

Funções:
- canal dedicado de ouvidoria
- anonimato quando aplicável
- controle de confidencialidade e segregação de acesso
- fluxo de encaminhamento e acompanhamento
- evidências e auditoria

---

### 3.12 Monitoramento, Planos de Ação e Educação (Fase 3)
Responsável por transformar risco em ação e acompanhar efetividade.

Funções:
- planos de ação associados a riscos
- acompanhamento de status e prazos
- campanhas e treinamentos em três camadas:
  - RH
  - lideranças
  - colaboradores
- disparo de conteúdos conforme risco e contexto (exemplo: pré atividade crítica)
- registro de participação e evidências

---

### 3.13 Operação, SLA e Workflow Interno
Responsável por suporte operacional e controle de execução do processo NR-01.

Funções:
- abertura e gestão de tickets internos
- controle de SLA e filas
- kanban ou lista operacional por processo
- alertas de violação de SLA
- trilha de auditoria operacional

Observação:
O workflow deve ser nativo. Integração com ferramentas externas pode existir como evolução, mas não é premissa.

---

### 3.14 Integrações e Conectores Externos
Responsável por comunicação com sistemas externos.

Integrações prioritárias:
- SOC
- SGG (segunda prioridade)

Integrações complementares:
- OCR (leitura de documentos, quando aplicável)
- Teleconsulta (quando aplicável)
- WhatsApp e canais de comunicação (fases futuras, se aprovado no roadmap)

Funções:
- execução sequencial conforme restrições do SOC
- logs completos e rastreabilidade
- reprocessamento e controle de erros
- proteção de credenciais

---

## 4. Fluxos Lógicos Principais

### 4.1 Fluxo macro NR-01
1. Configuração da empresa e hierarquia
2. Execução da fase 1 (maturidade)
3. Execução da fase 2 (questionários e coleta)
4. Cruzamento e recomendações
5. Registro e classificação de riscos
6. Validação do engenheiro e emissão de documentos
7. Plano de ação, educação e monitoramento
8. Integração com PCMSO e testes complementares
9. Ciclo contínuo de revisão

---

### 4.2 Fluxo clínico (PCMSO)
1. Risco identificado e classificado
2. Matriz risco x testes define quais instrumentos aplicar
3. Disparo de aplicação no contexto dos exames
4. Execução via SOC ou link integrado
5. Retorno e registro de evidências
6. Laudo assistido ou não assistido com assinatura
7. Atualização do monitoramento

---

### 4.3 Fluxo de atividade crítica (pré e pós)
1. Identificação de atividade crítica (exemplo: embarque)
2. Envio de formulário pré atividade
3. Registro do estado do colaborador
4. Envio de formulário pós atividade
5. Registro de variação e evidência para nexo causal
6. Encaminhamentos conforme regra (consulta, ouvidoria, plano de ação)

---

## 5. Pontos de Decisão e Auditoria

Decisões que exigem validação humana explícita:
- fechamento do diagnóstico psicossocial
- definição final de probabilidade, severidade e nível de risco
- emissão de documentos técnicos
- validação e assinatura de laudos

Eventos auditáveis obrigatórios:
- acessos a dados sensíveis
- alterações em riscos e classificações
- aprovação do engenheiro
- emissão e edição de laudos
- integrações com SOC (request, response, status)

---

## 6. Dependências e Trade-offs

Dependências:
- disponibilidade e restrições técnicas do SOC
- governança de dados sensíveis e LGPD
- qualidade dos indicadores da fase 1 fornecidos pela empresa

Trade-offs aceitos:
- maior profundidade no MVP para garantir robustez normativa
- integração SOC mínima no MVP, evoluindo para expansão
- IA como apoio, nunca como decisor final

---

## 7. Próximos Passos

- Detalhar contratos de integração (API, eventos, filas)
- Detalhar matriz risco x testes como artefato formal do MVP
- Criar ADR específico para padrões de integração com SOC e SGG
- Completar requisitos não funcionais e políticas de logs
