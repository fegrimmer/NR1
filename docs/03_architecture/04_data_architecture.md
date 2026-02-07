# Arquitetura de Dados – NR1 Inteligente

## 1. Objetivo

Este documento descreve a arquitetura de dados do sistema NR1 Inteligente, incluindo:
- entidades de domínio
- relacionamentos
- regras de integridade
- diretrizes de versionamento
- integração com o sistema SOC

O modelo utiliza como benchmark o data model do Heali, expandido e adaptado para atender às necessidades específicas da NR-01, especialmente no contexto de riscos psicossociais, maturidade organizacional e gerenciamento contínuo.

---

## 2. Princípios de Modelagem

- Separação clara entre dados organizacionais e dados individuais
- Risco psicossocial tratado como entidade central
- Histórico e versionamento como requisitos nativos
- Integrações externas desacopladas do modelo interno
- Auditoria e rastreabilidade por padrão
- Compatibilidade com LGPD e dados sensíveis

---

## 3. Visão Geral do Domínio

### Macroentidades
- Organização
- Estrutura Organizacional
- Usuário e Perfis
- Avaliação e Diagnóstico
- Riscos Psicossociais
- Programas e Ações
- Integrações Externas (SOC)

---

## 4. Entidades Organizacionais

### 4.1 Instituição
Representa a empresa cliente do sistema.

Atributos principais:
- idInterno
- idSOC
- nome
- razaoSocial
- cnpj
- cnae
- grauRisco
- status
- dataCriacao

Regras:
- Uma Instituição pode possuir múltiplas Unidades
- Código SOC é opcional até sincronização

---

### 4.2 Unidade
Representa uma unidade física ou operacional da instituição.

Atributos:
- idInterno
- idSOC
- nome
- cnpj
- endereco
- status

Relacionamento:
- Pertence a uma Instituição

---

### 4.3 Setor
Representa um setor organizacional.

Atributos:
- idInterno
- idSOC
- nome
- descricao

Relacionamento:
- Pertence a uma Unidade

---

### 4.4 Cargo
Representa uma função exercida pelo colaborador.

Atributos:
- idInterno
- idSOC
- nome
- descricao
- atividadesCriticas

Relacionamento:
- Pertence a um Setor

---

### 4.5 Hierarquia
Entidade lógica que associa Instituição, Unidade, Setor e Cargo.

Uso:
- Base para análises por grupo
- Apoio à definição de grupos homogêneos

---

## 5. Entidades de Usuário e Pessoas

### 5.1 Usuário
Representa um usuário do sistema (gestor, psicólogo, engenheiro, médico).

Atributos:
- idInterno
- nome
- email
- perfil
- status

---

### 5.2 Colaborador
Representa o trabalhador avaliado.

Atributos:
- idInterno
- idSOC
- matricula
- dataAdmissao
- status

Relacionamentos:
- Associado a Cargo
- Associado a Setor
- Associado a Unidade

---

## 6. Entidades de Avaliação e Diagnóstico

### 6.1 Avaliação Psicossocial
Representa a aplicação de instrumentos psicossociais.

Atributos:
- idInterno
- tipoInstrumento
- dataAplicacao
- status
- contexto (admissional, periódico, demissional, pré-atividade, pós-atividade)

Relacionamentos:
- Associada a Colaborador ou Grupo
- Associada a Programa NR1

---

### 6.2 Resposta de Avaliação
Representa as respostas individuais aos instrumentos.

Atributos:
- idInterno
- pergunta
- resposta
- valorNormalizado

---

### 6.3 Diagnóstico Psicossocial
Resultado interpretado da avaliação.

Atributos:
- idInterno
- resumo
- observacoes
- dataEmissao
- profissionalResponsavel

---

## 7. Entidades de Risco Psicossocial

### 7.1 Fator de Risco Psicossocial
Representa fatores como estresse, assédio, insegurança, burnout.

Atributos:
- idInterno
- nome
- descricao
- categoria

---

### 7.2 Risco Psicossocial
Representa o risco avaliado e classificado.

Atributos:
- idInterno
- probabilidade
- severidade
- nivelRisco
- justificativa
- status

Relacionamentos:
- Associado a Fator de Risco
- Associado a Setor, Cargo ou Instituição
- Validado por Engenheiro de Segurança

---

## 8. Programas, Ações e Monitoramento

### 8.1 Programa NR1
Representa um ciclo formal de NR-01.

Atributos:
- idInterno
- periodo
- status
- responsavelTecnico

---

### 8.2 Plano de Ação
Representa ações mitigadoras.

Atributos:
- idInterno
- descricao
- tipo
- prazo
- status

Relacionamento:
- Associado a Risco Psicossocial

---

## 9. Integração com SOC

### 9.1 Controle de Integração
Entidade técnica de controle.

Atributos:
- entidade
- idInterno
- idSOC
- statusSincronizacao
- dataUltimaTentativa
- mensagemErro

---

## 10. Versionamento e Histórico

Diretrizes:
- Avaliações e diagnósticos não são sobrescritos
- Alterações geram novas versões
- Histórico completo deve ser mantido
- Dados sensíveis seguem regras de retenção LGPD

---

## 11. Considerações LGPD

- Separação entre dados identificáveis e analíticos
- Controle de acesso por perfil
- Registro de consentimento quando aplicável
- Auditoria de acesso a dados sensíveis

---

## 12. Considerações Finais

O modelo d
