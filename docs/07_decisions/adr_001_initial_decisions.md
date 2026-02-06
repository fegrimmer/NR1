# ADR 001 - Decisões Fundamentais do Projeto NR1 Inteligente

## Status
Aceito

## Data
2026-02-06

## Contexto

O projeto NR1 Inteligente nasce a partir da identificação de falhas estruturais nos sistemas atuais de SST, especialmente no que se refere a:

- Fragmentação da jornada do usuário
- Baixa adesão dos colaboradores
- Foco excessivo em coleta de dados e pouco em gestão de risco
- Ausência de análise de maturidade organizacional
- Dificuldade operacional das clínicas de saúde ocupacional
- Fragilidade normativa na condução da NR-01

Foi identificado que a simples aplicação de questionários psicossociais não atende, de forma isolada, aos requisitos técnicos e normativos da NR-01.

Diante disso, tornou-se necessário estabelecer decisões fundacionais claras para orientar todas as escolhas funcionais, arquiteturais e técnicas do projeto.

Este ADR registra essas decisões iniciais e serve como referência permanente para evolução do sistema.

---

## Decisão 1 - Foco exclusivo em NR-01 na fase inicial

### Decisão
O projeto terá foco exclusivo na NR-01 (Riscos Psicossociais) em sua fase inicial.

### Justificativa
- Evita diluição de escopo
- Garante profundidade normativa e técnica
- Permite validação clara de valor antes de expansão
- Reduz risco de complexidade prematura

Funcionalidades que não contribuem diretamente para a NR-01 ficam fora do MVP.

---

## Decisão 2 - Modelo metodológico obrigatório em três fases

### Decisão
A NR-01 será tratada como um processo estruturado em três fases indissociáveis:

1. Análise de Maturidade Organizacional  
2. Identificação dos Riscos Psicossociais  
3. Gerenciamento e Monitoramento dos Ciclos Psicossociais  

### Justificativa
- A percepção do colaborador é subjetiva
- A maturidade organizacional fornece contexto técnico
- A gestão contínua de risco é exigência normativa implícita
- Ferramentas de mercado atuam majoritariamente apenas na fase 2

A aplicação isolada de questionários é considerada insuficiente.

---

## Decisão 3 - Centralidade da análise de maturidade organizacional

### Decisão
A análise de maturidade organizacional é etapa obrigatória do processo NR-01.

### Justificativa
- Permite cruzamento entre percepção e indicadores reais
- Evita inflar riscos inexistentes
- Fundamenta definição de probabilidade e severidade
- Aumenta robustez técnica e defensabilidade normativa

Checklist, entrevistas gravadas, atas e indicadores organizacionais fazem parte dessa fase.

---

## Decisão 4 - Separação clara de papéis técnicos

### Decisão
O sistema deve refletir a separação de responsabilidades entre psicólogo e engenheiro de segurança.

### Definição de papéis
- Psicólogo:
  - Interpretação psicossocial
  - Identificação de fatores e situações sociais
  - Apoio técnico ao diagnóstico

- Engenheiro de segurança:
  - Responsável técnico pela avaliação de risco
  - Definição de probabilidade, severidade e nível de risco
  - Delimitação do escopo normativo
  - Validação técnica e autorização
  - Emissão de documentos e avaliações ergonômicas

### Justificativa
Essa separação garante aderência normativa e clareza de responsabilidade técnica.

---

## Decisão 5 - Integração prioritária com sistemas de SST

### Decisão
O sistema deve integrar prioritariamente com SOC e SGG.

### Justificativa
- São os principais sistemas utilizados pelas clínicas
- Evitam retrabalho operacional
- Permitem aplicação de testes no contexto dos exames
- Garantem viabilidade operacional em escala

O NR1 Inteligente orquestra riscos e testes.
Os sistemas de SST executam os exames.

---

## Decisão 6 - Motor de formulários como núcleo da experiência

### Decisão
Toda interação com o colaborador deve ocorrer por meio de formulários parametrizados e links de acesso.

### Justificativa
- Unifica a experiência do usuário
- Reduz necessidade de treinamento
- Aumenta adesão
- Permite reaproveitamento do motor em múltiplos contextos da NR-01

Independentemente do processo, o ponto de entrada do colaborador é sempre o formulário.

---

## Decisão 7 - Gerenciamento contínuo de riscos psicossociais

### Decisão
A NR-01 será tratada como processo contínuo, e não evento anual.

### Justificativa
- Riscos psicossociais são dinâmicos
- A NR-01 exige monitoramento
- Integração com PCMSO é obrigatória
- Permite ações preventivas e mitigadoras reais

Essa decisão viabiliza:
- matriz risco x testes
- avaliações periódicas
- pré e pós atividades críticas
- monitoramento longitudinal

---

## Decisão 8 - Uso de IA como apoio, não como decisor

### Decisão
A inteligência artificial será utilizada como camada de apoio técnico.

### Justificativa
- Auxilia interpretação de laudos
- Sugere análises e padrões
- Reduz esforço manual
- Não substitui validação humana

Todos os laudos devem ser editáveis e validados por profissionais habilitados.

---

## Decisão 9 - Documentação viva como governança do projeto

### Decisão
O projeto adotará documentação viva, versionada em repositório Git, como fonte única de verdade.

### Justificativa
- Evita perda de contexto
- Facilita evolução incremental
- Garante alinhamento entre negócio, arquitetura e técnica
- Suporta auditoria e rastreabilidade

A especificação funcional é o documento central do projeto.

---

## Consequências

### Positivas
- Alta robustez normativa
- Diferenciação clara frente ao mercado
- Viabilidade operacional
- Clareza de responsabilidades
- Base sólida para escalabilidade futura

### Trade-offs
- Maior esforço inicial de especificação
- MVP mais profundo e menos genérico
- Necessidade de disciplina na governança documental

Esses trade-offs são considerados aceitáveis e desejáveis.

---

## Observações Finais

Este ADR deve ser considerado fundacional.
Alterações futuras devem gerar novos ADRs, mantendo rastreabilidade das decisões.

