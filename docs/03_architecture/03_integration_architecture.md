# Arquitetura de Integrações
A arquitetura de integrações deverá ser agnóstica, e prever diferentes possibilidades futuras de integrações com sistemas de terceiros, como o SOC, o SGG, dentre outros.

# Arquitetura de Integração – SOC

## 1. Objetivo da Integração

Este documento descreve a arquitetura de integração entre o sistema NR1 Inteligente e o sistema SOC, líder de mercado em gestão de SST.

A integração tem como objetivo garantir viabilidade operacional, evitar retrabalho em clínicas de saúde ocupacional e permitir que os dados necessários à NR-01 sejam utilizados no contexto dos exames ocupacionais, sem exigir duplicidade de cadastros ou processos paralelos.

O SOC é tratado como um sistema externo especializado na execução de exames e gestão ocupacional, enquanto o NR1 Inteligente atua como orquestrador dos riscos psicossociais, testes e fluxos da NR-01.

---

## 2. Princípios de Integração

- O NR1 Inteligente é o sistema de decisão e orquestração da NR-01.
- O SOC é o sistema executor de exames e agendas ocupacionais.
- Não deve haver duplicidade manual de cadastros.
- As integrações devem ser rastreáveis, auditáveis e resilientes.
- As chamadas aos serviços do SOC devem respeitar as restrições técnicas do fornecedor (execução sequencial).

---

## 3. Entidades Sincronizadas

As principais entidades sincronizadas entre o NR1 Inteligente e o SOC incluem:

- Empresa (Instituição)
- Unidade
- Setor
- Cargo
- Hierarquia
- Funcionário
- Agenda de exames
- Resultados de exames (quando aplicável)

Cada entidade deve possuir:
- Identificador interno do NR1
- Código correspondente no SOC
- Status de sincronização
- Timestamp da última atualização

---

## 4. Serviços SOC Utilizados

### 4.1 WS_Empresa
Responsável pela inclusão, alteração e consulta de empresas no SOC.

Uso no NR1:
- Sincronização de instituições clientes
- Associação de códigos SOC ao domínio interno

---

### 4.2 WS_Unidade
Responsável pela gestão de unidades vinculadas à empresa.

Uso no NR1:
- Estruturação organizacional
- Associação de exames e agendas por unidade

---

### 4.3 WS_Setor
Responsável pelo cadastro de setores organizacionais.

Uso no NR1:
- Agrupamento de riscos psicossociais
- Análises por setor

---

### 4.4 WS_Cargo
Responsável pelo cadastro de cargos.

Uso no NR1:
- Associação de riscos por função
- Apoio à definição de grupos homogêneos

---

### 4.5 WS_Hierarquia
Responsável pela associação entre empresa, unidade, setor e cargo.

Uso no NR1:
- Construção da hierarquia organizacional
- Base para análise de risco coletivo

---

### 4.6 WS_Funcionario
Responsável pela gestão de funcionários.

Uso no NR1:
- Associação de avaliações psicossociais
- Aplicação de testes conforme riscos identificados

---

### 4.7 WS_Agendamento
Responsável pelo agendamento de exames ocupacionais.

Uso no NR1:
- Disparo de exames conforme matriz risco x testes
- Integração com PCMSO

---

### 4.8 WS_ResultadoExame
Responsável pela consulta de resultados de exames.

Uso no NR1:
- Registro de evidências
- Apoio ao monitoramento de riscos psicossociais

---

## 5. Estratégia de Sincronização

A sincronização entre NR1 e SOC pode ocorrer de três formas:

- On-demand: acionada por evento no NR1 (ex.: criação de empresa)
- Agendada: sincronizações periódicas (ex.: atualização noturna)
- Orientada a processo: disparada por fluxos da NR-01 (ex.: necessidade de exame)

Falhas devem ser registradas com possibilidade de reprocessamento.

---

## 6. Segurança e Autenticação

- Uso de WS-Security conforme especificação do SOC
- Credenciais armazenadas de forma segura
- Comunicação criptografada
- Restrições de paralelismo respeitadas
- Logs completos de request e response (com mascaramento de dados sensíveis)

---

## 7. Tratamento de Erros

O sistema deve tratar:
- Erros de validação de dados
- Erros de comunicação
- Erros de autenticação
- Respostas de falha do SOC

Cada erro deve gerar:
- Log técnico
- Status de sincronização
- Alerta operacional quando necessário

---

## 8. Observabilidade e Auditoria

- Registro de chamadas realizadas
- Tempo de resposta
- Resultado da operação
- Associação com processo NR-01 correspondente

Esses registros são essenciais para auditoria normativa e suporte operacional.

---

## 9. Limitações Conhecidas

- Execução sequencial obrigatória das chamadas ao SOC
- Dependência da disponibilidade dos serviços externos
- Necessidade de tratamento de timeout e retentativas

Essas limitações devem ser consideradas no desenho da arquitetura técnica.

---

## 10. Considerações Finais

A integração com o SOC é um pilar fundamental do NR1 Inteligente, garantindo que a gestão de riscos psicossociais esteja integrada à prática real da saúde ocupacional, sem criar sobrecarga operacional para clínicas e empresas.

Qualquer alteração relevante nesta integração deve ser registrada em um ADR específico.
