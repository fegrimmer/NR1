# Casos de Uso e Fluxos Funcionais – NR1 Inteligente

## Visão Geral

Este documento descreve os principais casos de uso do sistema NR1 Inteligente,
organizados conforme o modelo metodológico da NR-01 em três fases.

Os casos de uso descrevem interações entre usuários, sistema e integrações externas,
servindo como base para desenvolvimento, testes e validação.

---

## FASE 0 – Acesso e Configuração Inicial

### UC-00 – Autenticar Usuário
**Ator:** Usuário do sistema  
**Descrição:** Permite autenticação e acesso ao sistema conforme perfil.  
**Pré-condições:** Usuário cadastrado e ativo.  
**Pós-condições:** Sessão iniciada e perfil carregado.

---

### UC-01 – Selecionar Instituição e Perfil
**Ator:** Usuário  
**Descrição:** Seleciona empresa/unidade e papel de atuação.  
**Pré-condições:** Usuário autenticado.  
**Pós-condições:** Contexto organizacional definido.

---

## FASE 1 – Análise de Maturidade Organizacional

### UC-10 – Executar Checklist de Maturidade
**Ator:** Gestor (RH/QSMS)  
**Descrição:** Preencher checklist de maturidade organizacional.  
**Pós-condições:** Respostas armazenadas e versionadas.

---

### UC-11 – Registrar Entrevistas de Maturidade
**Ator:** Psicólogo / Consultor  
**Descrição:** Registrar entrevistas com lideranças e áreas-chave.  
**Fluxos alternativos:** Inclusão de atas, anexos e observações.  
**Pós-condições:** Evidências da fase 1 registradas.

---

### UC-12 – Consolidar Indicadores Organizacionais
**Ator:** Sistema  
**Descrição:** Consolidar indicadores fornecidos pela empresa.  
**Pós-condições:** Perfil de maturidade disponível para cruzamento.

---

## FASE 2 – Identificação dos Riscos Psicossociais

### UC-20 – Configurar Avaliação Psicossocial
**Ator:** Psicólogo  
**Descrição:** Selecionar instrumentos aceitos pelo CFP e definir público-alvo.  
**Pós-condições:** Avaliação pronta para aplicação.

---

### UC-21 – Convocar Colaboradores para Avaliação
**Ator:** Operação / Sistema  
**Descrição:** Enviar convocações conforme regras definidas.  
**Fluxos alternativos:** Reconvocação automática.  
**Pós-condições:** Convocações registradas.

---

### UC-22 – Responder Avaliação Psicossocial
**Ator:** Colaborador  
**Descrição:** Preencher questionário psicossocial.  
**Pós-condições:** Respostas armazenadas e auditáveis.

---

### UC-23 – Consolidar Resultados da Avaliação
**Ator:** Sistema  
**Descrição:** Normalizar e consolidar respostas por setor e grupo.  
**Pós-condições:** Dataset consolidado disponível.

---

## FASE 2.5 – Cruzamento e Análise Técnica

### UC-25 – Cruzar Percepção com Maturidade Organizacional
**Ator:** Sistema  
**Descrição:** Cruzar respostas com indicadores da fase 1.  
**Pós-condições:** Insumos para avaliação de risco.

---

### UC-26 – Analisar Resultados Psicossociais
**Ator:** Psicólogo  
**Descrição:** Interpretar padrões e fatores psicossociais.  
**Pós-condições:** Recomendações técnicas registradas.

---

## FASE 3 – Gerenciamento e Monitoramento dos Riscos

### UC-30 – Registrar Risco Psicossocial
**Ator:** Psicólogo / Sistema  
**Descrição:** Criar registros de risco por fator, setor ou cargo.  
**Pós-condições:** Riscos registrados com evidências.

---

### UC-31 – Classificar Risco Psicossocial
**Ator:** Engenheiro de Segurança  
**Descrição:** Definir probabilidade, severidade e nível de risco.  
**Pós-condições:** Risco validado tecnicamente.

---

### UC-32 – Emitir Documentos Técnicos
**Ator:** Engenheiro de Segurança  
**Descrição:** Emitir avaliações ergonômicas e documentos NR-01.  
**Pós-condições:** Documentos versionados e assinados.

---

### UC-33 – Definir Plano de Ação
**Ator:** Gestor / Especialista  
**Descrição:** Definir ações mitigadoras associadas aos riscos.  
**Pós-condições:** Plano de ação ativo.

---

### UC-34 – Integrar com PCMSO
**Ator:** Sistema  
**Descrição:** Associar riscos a exames e testes complementares.  
**Integração:** SOC / SGG  
**Pós-condições:** Exames configurados.

---

### UC-35 – Aplicar Avaliações Complementares
**Ator:** Colaborador / Clínica  
**Descrição:** Executar testes conforme matriz risco x testes.  
**Pós-condições:** Resultados registrados.

---

### UC-36 – Gerar Laudos Psicossociais
**Ator:** Psicólogo / Médico  
**Descrição:** Gerar laudos com apoio de IA e validação humana.  
**Pós-condições:** Laudos emitidos e versionados.

---

## FASE TRANSVERSAL – Canais Sensíveis e Operação

### UC-40 – Registrar Manifestação na Ouvidoria
**Ator:** Colaborador  
**Descrição:** Registrar denúncia ou reclamação confidencial.  
**Pós-condições:** Caso registrado com confidencialidade.

---

### UC-41 – Avaliação Pré e Pós Atividade Crítica
**Ator:** Colaborador  
**Descrição:** Preencher formulários pré e pós atividade crítica.  
**Pós-condições:** Evidências para análise de nexo causal.

---

### UC-42 – Validar Atestado Psicossocial
**Ator:** Médico  
**Descrição:** Validar atestado CID F ou G.  
**Fluxos alternativos:** Teleconsulta.  
**Pós-condições:** Atestado validado ou recusado.

---

## Observações Finais

- Casos de uso são incrementais
- Novos casos devem ser adicionados conforme evolução do MVP
- Cada caso pode ser detalhado futuramente com critérios de aceitação
