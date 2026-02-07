# Requisitos Não Funcionais – NR1 Inteligente

## 1. Objetivo

Este documento define os requisitos não funcionais do NR1 Inteligente,
estabelecendo critérios de qualidade, segurança, desempenho, conformidade
e operação necessários para suportar um sistema SaaS regulado,
com dados sensíveis e obrigações normativas relacionadas à NR-01.

Os requisitos aqui descritos são transversais a todo o sistema
e complementam a Especificação Funcional, a Arquitetura e a Matriz CRUD.

---

## 2. Segurança da Informação

### 2.1 Controle de Acesso
- O sistema deve implementar controle de acesso baseado em papéis (RBAC)
- O acesso deve ser sempre condicionado ao Tenant ativo
- Operações sobre dados de SST exigem escopo adicional da Empresa Atendida
- Permissões devem seguir o princípio do menor privilégio

### 2.2 Autenticação
- Autenticação obrigatória para usuários internos
- Tokens com tempo de expiração configurável
- Revogação imediata de acessos em caso de desativação
- Links de formulários devem utilizar tokens seguros e expiráveis

### 2.3 Proteção de Dados Sensíveis
- Dados psicossociais, de saúde e ouvidoria são classificados como sensíveis
- Tráfego de dados deve usar criptografia em trânsito
- Recomenda-se criptografia em repouso para dados sensíveis
- Logs não devem armazenar conteúdo sensível em texto claro

---

## 3. LGPD e Privacidade

### 3.1 Princípios
- Finalidade, necessidade e minimização de dados
- Acesso restrito por necessidade funcional
- Transparência sobre coleta e uso de dados

### 3.2 Direitos do Titular
- Possibilidade de anonimização quando aplicável
- Exclusão lógica quando permitida por política e legislação
- Preservação de dados normativos e legais, mesmo após desligamento

### 3.3 Segregação
- Separação lógica entre:
  - dados de negócio
  - identidade e acesso
  - formulários e respostas
  - auditoria
  - logs técnicos

---

## 4. Auditoria e Rastreabilidade

### 4.1 Eventos Auditáveis
Devem ser auditados obrigatoriamente:
- acessos a dados sensíveis
- leitura de respostas psicossociais
- alterações em diagnósticos, riscos e laudos
- aprovações técnicas (engenharia e clínica)
- integrações externas (SOC, SGG)

### 4.2 Características da Auditoria
- Logs append-only
- Imutáveis
- Com timestamp, usuário, tenant e empresa
- Não deletáveis

---

## 5. Disponibilidade e Confiabilidade

### 5.1 Disponibilidade
- O sistema deve ser projetado para alta disponibilidade
- Falhas parciais não devem comprometer dados já coletados
- Operações críticas devem ser idempotentes

### 5.2 Continuidade
- Backups regulares e segregados por domínio
- Planos de recuperação devem priorizar dados normativos
- Formulários em andamento não devem perder dados sem aviso

---

## 6. Performance e Escalabilidade

### 6.1 Performance
- O sistema deve suportar picos de acesso durante campanhas de avaliação
- Leitura agregada deve ser otimizada para relatórios e análises
- Escrita de formulários deve priorizar confiabilidade sobre latência extrema

### 6.2 Escalabilidade
- Escala horizontal para múltiplos tenants
- Isolamento lógico para evitar impacto entre tenants
- Capacidade de crescimento sem refatoração estrutural

---

## 7. Usabilidade e Experiência do Usuário

### 7.1 Princípios
- Baixa fricção para colaboradores
- Interfaces claras e objetivas
- Fluxos simples para formulários críticos

### 7.2 Formulários
- Suporte a formulários longos
- Feedback visual de progresso
- Validação clara de erros
- Retomada quando permitido pelo instrumento

---

## 8. Integrações Externas (SOC, SGG)

### 8.1 Princípios de Integração
- Integrações devem ser desacopladas do core
- Falhas externas não devem comprometer o sistema interno
- Reprocessamento controlado de falhas

### 8.2 Modelo do SOC
- O modelo de tenant/base do SOC permanece em aberto
- A arquitetura deve permitir múltiplos cenários sem refatoração
- Integrações devem ser sempre contextualizadas

---

## 9. Observabilidade e Operação

### 9.1 Logs Técnicos
- Logs separados de logs de auditoria
- Retenção configurável
- Sem dados sensíveis em texto claro

### 9.2 Monitoramento
- Monitoramento de integrações
- Alertas para falhas críticas
- Métricas de SLA interno

---

## 10. Manutenibilidade e Evolução

### 10.1 Código e Arquitetura
- Arquitetura modular por domínio
- Baixo acoplamento entre módulos
- Evolução incremental sem quebra de contratos

### 10.2 Documentação Viva
- Toda mudança relevante deve atualizar a documentação
- Decisões arquiteturais devem ser registradas via ADR
- Especificações devem permanecer como fonte de verdade

---

## 11. Conformidade Normativa

- O sistema deve suportar evidências para NR-01
- Documentos e laudos devem ser versionados
- Histórico deve ser preservado para auditoria
- Decisões técnicas devem ser rastreáveis

---

## 12. Critérios de Aceitação Não Funcionais (Resumo)

- Segurança: RBAC, segregação, criptografia
- LGPD: minimização, anonimização, rastreabilidade
- Auditoria: completa, imutável, confiável
- Performance: suportar campanhas massivas
- Escalabilidade: multi-tenant sem impacto cruzado
- Usabilidade: foco no colaborador
- Integração: resiliente e desacoplada

---

## 13. Observações Finais

Este documento não define tecnologia específica.
As decisões técnicas de stack devem respeitar estes requisitos
e podem ser detalhadas posteriormente na Arquitetura Técnica.
