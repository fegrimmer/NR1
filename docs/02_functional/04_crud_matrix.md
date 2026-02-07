# Matriz CRUD – NR1 Inteligente

## 1. Objetivo

Este documento descreve as operações de Criação (Create), Leitura (Read),
Atualização (Update) e Exclusão (Delete) das principais entidades do
NR1 Inteligente, associando cada operação aos perfis autorizados
e às regras normativas, de segurança e auditoria.

A matriz CRUD deriva diretamente da Especificação Funcional,
dos Fluxos Funcionais e do Motor de Formulários, e serve como base para:
- definição de APIs
- controle de acesso (RBAC)
- testes funcionais
- auditoria e conformidade normativa (NR-01, LGPD)

---

## 2. Convenções Gerais

### 2.1 Multi-tenant
- Todo dado pertence obrigatoriamente a um **Tenant (Contratante do SaaS)**
- Dados de SST pertencem adicionalmente a uma **Empresa Atendida (Cliente SST)**
- Usuários pertencem ao Tenant, não diretamente à Empresa Atendida

### 2.2 Exclusão e histórico
- Exclusão física (hard delete) é evitada
- Preferir soft dele
