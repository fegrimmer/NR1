# NR1 Inteligente – Visão Geral do Projeto

## 1. Introdução

O NR1 Inteligente é um projeto de plataforma SaaS voltado à gestão de riscos psicossociais conforme a NR-01, com foco em melhorar a comunicação com colaboradores, a qualidade do diagnóstico organizacional e a governança técnica e normativa do processo.

O projeto nasce da constatação de que, apesar da evolução normativa e da existência de ferramentas de SST no mercado, ainda existe uma fragmentação significativa da jornada do usuário, especialmente do colaborador avaliado, o que impacta diretamente a adesão, a qualidade dos dados e a efetividade do gerenciamento de riscos.

---

## 2. Problema que o Projeto Endereça

Atualmente, o processo de NR-01 e de avaliação psicossocial costuma apresentar os seguintes problemas:

- múltiplos sistemas desconectados para uma mesma jornada
- sistemas engessados, e sem muitas opções de personalizações (como white Label, e criação de formulários e dashboard dinâmicos, através de interfaces intuitivas de configuração dos mesmos)
- foco excessivo apenas na aplicação de questionários, sem análise de maturidade organizacional
- inexistência de ferramenta para o gerenciamento dos riscos psicossociais, após diagnósticos
- pouca capacidade de cruzamento entre percepção dos colaboradores e indicadores, processos e controles da empresa
- dificuldade operacional para integrar maturidade da empresa e riscos psicossociais identificados aos programas de segurança do trabalho
- dificuldade operacional para integrar riscos psicossociais ao PCMSO e à rotina clínica
- baixa rastreabilidade e governança do processo ao longo do tempo
- falta de camada inteligente, para inferência de laudos sugestivos

Esses fatores reduzem a confiabilidade dos diagnósticos e aumentam o risco normativo para empresas, clínicas e profissionais envolvidos.

---

## 3. Proposta do NR1 Inteligente

O NR1 Inteligente propõe uma abordagem integrada, contínua e orientada a processo, estruturando a NR-01 em três grandes fases complementares:

1. Análise de maturidade organizacional  
2. Identificação dos riscos psicossociais  
3. Gerenciamento e monitoramento contínuo dos riscos  

A plataforma centraliza a experiência do colaborador principalmente por meio de formulários e Dashboards customizáveis, links diretos e interfaces de baixa fricção, enquanto oferece aos profissionais de SST, psicologia, engenharia e medicina do trabalho ferramentas de análise, validação técnica e gestão normativa.

---

## 4. Princípios Norteadores

O projeto é guiado pelos seguintes princípios:

- NR-01 como processo contínuo, não como evento pontual
- separação clara entre percepção subjetiva e evidência organizacional
- apoio à decisão técnica, nunca substituição do profissional
- rastreabilidade, versionamento e auditabilidade como requisitos nativos
- documentação viva como fonte única de verdade
- arquitetura preparada para múltiplos modelos operacionais
- foco em adesão do colaborador e viabilidade operacional

---

## 5. Público-Alvo e Perfis Envolvidos

O NR1 Inteligente atende diferentes perfis, cada um com objetivos distintos:

- contratantes do SaaS, como clínicas de saúde ocupacional, empresas de gestão ocupacional, redes de clínicas e empresas que fazem autogestão
- empresas atendidas, nas quais os serviços de SST e NR-01 são prestados
- colaboradores avaliados
- psicólogos organizacionais e do trabalho
- engenheiros de segurança
- médicos do trabalho
- equipes administrativas e de operação

A plataforma foi concebida para suportar esses diferentes papéis de forma integrada e segregada, conforme boas práticas de governança.

---

## 6. Diferenciais da Abordagem

Entre os principais diferenciais do NR1 Inteligente estão:

- inclusão explícita da análise de maturidade organizacional como etapa fundamental
- cruzamento estruturado entre respostas psicossociais e indicadores tanto relacionados aos resultados e suas estatísticas, quanto ao comportamento do usuário ao preencher os questionários, como por exemplo, timestamp de cada clique, registro de cada interação, mesmo que seja repetida ou que o usuário marque e desmarque opções. Estas informações também são úteis para a avaliação da saúde mental do colaborador
- cruzamento estruturado entre maturidade, controles, processos, e indicadores das empresas, com riscos psicossociais identificados nos questionários preenchidos pelos colaboradores
- papel formal do engenheiro de segurança na validação dos riscos
- integração do risco psicossocial ao PCMSO e à rotina clínica
- motor de formulários flexível, versionado e auditável
- arquitetura preparada para integração com sistemas de SST, como o SOC
- modelo SaaS multi-tenant, preparado para diferentes tipos de contratantes

---

## 7. Escopo Atual do Projeto

Nesta fase, o projeto está focado em:

- definição da especificação funcional
- definição da arquitetura lógica, de dados e de integração
- definição dos fluxos operacionais e casos de uso
- definição do motor de formulários e avaliações
- definição da matriz CRUD
- definição dos requisitos não funcionais

Não fazem parte do escopo atual:
- decisões de stack tecnológico
- implementação de código
- definição de infraestrutura produtiva
- automações avançadas ou gamificação

---

## 8. Relação com a Documentação

Este documento tem caráter introdutório e deve ser lido antes dos demais artefatos.  
Os detalhes funcionais, arquiteturais e técnicos estão distribuídos nos demais documentos do diretório `/docs`, conforme a organização definida no guia de documentação.

---

## 9. Status

Este documento faz parte da versão inicial da documentação do projeto, identificada como **v0.1.0**, e está sujeito a revisões incrementais conforme validações e decisões futuras.
