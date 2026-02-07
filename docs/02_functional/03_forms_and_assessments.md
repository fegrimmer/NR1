# Forms and Assessments – Motor de Formulários e Instrumentos

## 1. Objetivo

Este documento define o motor de formulários e instrumentos do NR1 Inteligente, incluindo:
- tipos de formulários suportados
- contextos de aplicação (NR-01, PCMSO, atividades críticas, ouvidoria)
- versionamento e rastreabilidade
- regras de distribuição, acesso e coleta
- tratamento e consolidação de respostas
- suporte a instrumentos psicossociais e testes complementares

O motor de formulários é o núcleo da experiência do usuário, especialmente para o colaborador, e deve viabilizar alta adesão com baixa fricção operacional.

---

## 2. Princípios

- Formulário é a unidade básica de interação com o colaborador
- Todos os formulários devem ser auditáveis e versionados
- Respostas não são editáveis após submissão (salvo exceções formais)
- Instrumentos podem ser longos e exigem suporte a retomada e salvamento parcial (quando aplicável)
- Distribuição deve permitir links de acesso simples, sem exigir app
- Deve existir separação clara entre:
  - template do formulário (definição)
  - instância aplicada (execução)
  - respostas coletadas (dados)
- Dados sensíveis devem obedecer LGPD, sigilo e segregação por perfil

---

## 3. Conceitos e Entidades

### 3.1 Form Template (Definição do Formulário)
Representa a definição do formulário.

Campos principais:
- id
- nome
- descrição
- categoria
- versão
- status (rascunho, publicado, arquivado)
- proprietário (perfil responsável)
- regras de validação
- tags (NR1, PCMSO, ouvidoria, pré-atividade etc.)

### 3.2 Form Version (Versionamento)
Toda alteração relevante gera nova versão.

Regras:
- versões publicadas não são alteradas
- versões novas herdam do template anterior
- histórico deve ser preservado para auditoria e rastreabilidade

### 3.3 Form Instance (Aplicação)
Representa uma instância publicada para um público e contexto específicos.

Campos:
- id
- templateId + versão
- contexto de aplicação
- público alvo (empresa, unidade, setor, cargo, grupo, indivíduo)
- janela de aplicação (início/fim)
- canal de distribuição (link, portal, integração)
- status (ativo, encerrado, cancelado)

### 3.4 Submission (Submissão)
Representa uma resposta completa ou parcial.

Campos:
- id
- formInstanceId
- colaboradorId (quando identificável)
- status (em andamento, submetido, expirado)
- timestamps
- evidências (device, ip, canal, token)

### 3.5 Answer Set (Respostas)
Conjunto de respostas e valores normalizados.

Regras:
- imutável após submissão final
- armazenar valor bruto e valor normalizado (quando aplicável)
- permitir agregação por setor, cargo, grupo e ciclo NR1

---

## 4. Tipos de Formulários

### 4.1 Instrumentos Psicossociais (CFP)
Formulários longos e estruturados, com regras de pontuação e interpretação.

Requisitos:
- suporte a 75–95 perguntas
- salvamento parcial (opcional, conforme instrumento e política)
- validação de preenchimento
- aplicação por grupo homogêneo, setor e cargo
- coleta auditável

### 4.2 Testes Complementares (PCMSO)
Formulários e testes derivados de riscos identificados na NR-01.

Exemplos:
- burnout
- sonolência
- estresse
- triagens específicas

Requisitos:
- matriz risco x teste configurável
- aplicação em contextos:
  - admissional
  - periódico
  - demissional
  - acompanhamento

### 4.3 Checklists de Maturidade Organizacional (Fase 1)
Instrumentos para RH e gestão informarem controles existentes e indicadores.

Requisitos:
- perguntas objetivas e de evidência
- suporte a anexos e links
- versionamento por ciclo

### 4.4 Entrevistas e Atas (Fase 1)
Não é um questionário comum. É um formulário de registro estruturado de entrevistas.

Requisitos:
- campos para roteiro, temas, achados
- upload de gravação (ou referência segura)
- geração e armazenamento de ata

### 4.5 Pré e Pós Atividades Críticas
Formulários rápidos, disparados por evento (exemplo: embarque).

Requisitos:
- execução rápida (baixa fricção)
- aplicação baseada em evento e janela curta
- associação a atividade e local
- uso como evidência para nexo causal

### 4.6 Ouvidoria e Canais Sensíveis
Formulários de denúncia e reclamação.

Requisitos:
- possibilidade de anonimato (quando aplicável)
- segregação de acesso e confidencialidade
- trilha de auditoria
- anexos e evidências

### 4.7 Validação de Atestados
Formulários de upload e dados do atestado para avaliação médica.

Requisitos:
- upload do documento
- captura de metadados
- classificação por CID (F e G)
- fluxo de decisão (validar, solicitar teleconsulta, recusar)

---

## 5. Distribuição e Acesso

### 5.1 Link de Acesso
O sistema deve suportar links para aplicação de formulários com as opções:
- link autenticado (portal)
- link com token seguro (sem login)
- link expirável
- link por campanha (convocação em massa)

### 5.2 Identificação do Colaborador
O sistema deve suportar:
- formulário identificado (vinculado ao colaborador)
- formulário semi-identificado (exemplo: tokens)
- formulário anônimo (ouvidoria, quando permitido)

A escolha depende do tipo de formulário e das políticas de confidencialidade.

### 5.3 Canais
O canal de distribuição pode incluir:
- portal web
- link direto
- integração com SOC (quando aplicável)
- comunicação via mensageria (futuro)

---

## 6. Regras de Pontuação, Pesos e Correção

### 6.1 Regras do Instrumento
Cada instrumento pode definir:
- pesos por pergunta
- escalas
- normalizações
- cálculos de score e subscore

### 6.2 Regras Organizacionais
O sistema deve permitir regras adicionais por:
- setor
- cargo
- unidade
- ciclo NR1

Exemplo:
- ponderações diferentes conforme criticidade da atividade

### 6.3 Correção Subjetiva e Laudos
Para instrumentos e testes que exigem interpretação:
- o sistema calcula e propõe
- o profissional valida, edita e assina
- histórico de edições deve ser preservado

---

## 7. Consolidação e Saídas

O motor de formulários deve produzir saídas para:
- análises por setor, cargo e grupos
- classificação de risco (probabilidade, severidade)
- relatórios populacionais
- relatórios individuais quando permitido
- evidências auditáveis para NR-01

---

## 8. Integração com SOC (Aplicação no Contexto dos Exames)

Quando aplicável:
- formulários e testes complementares podem ser executados no contexto dos exames
- o NR1 Inteligente define o que deve ser aplicado
- o SOC executa o exame e pode disponibilizar link ou fluxo integrado
- resultados retornam para o NR1 Inteligente como evidência

A integração deve evitar cadastros duplicados e respeitar restrições de execução sequencial do SOC.

---

## 9. LGPD, Confidencialidade e Segurança

- Dados de saúde e psicossociais são sensíveis
- Acesso deve ser controlado por perfil e por necessidade
- Respostas devem ser criptografadas em repouso (recomendado) e em trânsito (obrigatório)
- Logs devem mascarar campos sensíveis
- Ou
