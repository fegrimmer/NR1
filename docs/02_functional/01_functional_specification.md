NR1 INTELIGENTE
ESPECIFICAÇÃO FUNCIONAL
Versão 0.2 – Documento Vivo (Fonte Única de Verdade)

================================================================
1. CONTEXTO E OBJETIVO DO DOCUMENTO
================================================================

Este documento consolida a especificação funcional do projeto NR1 Inteligente e deve ser considerado a fonte única de verdade
para todas as decisões de negócio, funcionais e técnicas do projeto.

O conteúdo é incremental, versionado e evolutivo. Nenhuma decisão relevante é considerada válida se não estiver refletida
neste documento.

Esta versão (0.2) consolida todo o entendimento construído até o momento e será utilizada como base para a primeira avaliação
funcional e técnica pelo FAB.

================================================================
2. FOCO E POSICIONAMENTO DO PROJETO
================================================================

Apesar da visão futura de uma plataforma unificada de SST, o foco atual e prioritário do projeto é a NR-01, com ênfase
na gestão de riscos psicossociais.

Todas as funcionalidades, integrações e decisões de escopo devem atender diretamente a NR-01.
Funcionalidades que não contribuem diretamente para a NR-01 ficam fora do MVP.

================================================================
3. PROBLEMA DE MERCADO IDENTIFICADO
================================================================

O principal problema dos sistemas atuais de SST não é a ausência de dados, mas a fragmentação da experiência,
da comunicação e da jornada do usuário.

Atualmente, empresas e colaboradores utilizam múltiplos sistemas e canais para:
- agendamento de exames
- preenchimento de fichas médicas
- envio e validação de atestados
- avaliações psicossociais
- NR-01
- solicitações administrativas

Essa fragmentação gera:
- baixa adesão dos colaboradores
- retrabalho operacional
- dificuldade de gestão
- fragilidade normativa

O projeto NR1 Inteligente nasce para centralizar a experiência do usuário,
utilizando formulários como ponto único de entrada
e fluxos automatizados como ponto único de tratamento.

================================================================
4. MODELO METODOLÓGICO DA NR-01
================================================================

O projeto adota um modelo obrigatório em três fases indissociáveis:

Fase 1 – Análise de Maturidade Organizacional
Fase 2 – Identificação dos Riscos Psicossociais
Fase 3 – Gerenciamento e Monitoramento dos Ciclos Psicossociais

A simples aplicação de questionários aos colaboradores (Fase 2 isolada)
não atende aos requisitos técnicos nem normativos da NR-01.

================================================================
5. FASE 1 – ANÁLISE DE MATURIDADE ORGANIZACIONAL
================================================================

Objetivo:
Criar o contexto técnico e organizacional necessário para a correta interpretação dos dados psicossociais.

Componentes da Fase 1:
- Checklist estruturado de maturidade organizacional
- Levantamento de controles internos existentes
- Coleta de indicadores organizacionais (turnover, absenteísmo, histórico, etc.)
- Entrevistas estruturadas com RH, QSMS e lideranças
- Gravação das entrevistas
- Geração e armazenamento de atas
- Consolidação das variáveis organizacionais

Esta fase permite diferenciar percepção subjetiva de risco real,
fundamentando a definição de probabilidade e severidade.

================================================================
6. FASE 2 – IDENTIFICAÇÃO DOS RISCOS PSICOSSOCIAIS
================================================================

Objetivo:
Coletar a percepção dos colaboradores por meio de instrumentos reconhecidos e aceitos pelo CFP.

Características:
- Questionários psicossociais validados no Brasil
- Aplicação por setor, função e grupos homogêneos
- Registro auditável das respostas

Importante:
As respostas representam percepção subjetiva do colaborador.
Elas devem obrigatoriamente ser cruzadas com a Fase 1
para definição de risco normativo.

================================================================
7. PAPÉIS E RESPONSABILIDADES
================================================================

Psicólogo:
- Interpretação psicossocial dos dados
- Identificação de fatores e situações sociais relevantes
- Apoio técnico à análise de risco

Engenheiro de Segurança:
- Responsável técnico pela avaliação de risco
- Definição de probabilidade, severidade e nível de risco
- Delimitação do escopo normativo
- Validação e autorização técnica
- Emissão de documentos e avaliações ergonômicas

Princípio:
O psicólogo identifica e interpreta o risco psicossocial.
O engenheiro de segurança dimensiona tecnicamente o risco
e responde normativamente pela NR-01.

================================================================
8. FASE 3 – GERENCIAMENTO E MONITORAMENTO DOS CICLOS PSICOSSOCIAIS
================================================================

A Fase 3 transforma a NR-01 em um processo contínuo de gestão de riscos psicossociais.

---------------------------------------------------------------
8.1 Integração com Sistemas de SST
---------------------------------------------------------------

Integração prioritária com:
- SOC
- SGG

Objetivos:
- Evitar retrabalho e cadastros duplicados
- Permitir aplicação de testes no contexto dos exames
- Garantir viabilidade operacional para clínicas

O sistema NR1 Inteligente define riscos e testes.
Os sistemas de SST executam os exames.

---------------------------------------------------------------
8.2 Interface com Medicina do Trabalho
---------------------------------------------------------------

- Integração com PCMSO
- Aplicação automática de testes conforme riscos identificados
- Suporte a exames admissionais, periódicos e demissionais

---------------------------------------------------------------
8.3 Avaliações Assistidas e Não Assistidas
---------------------------------------------------------------

- Avaliações realizadas com psicólogo
- Avaliações não assistidas
- Laudos assinados por psicólogos responsáveis
- Suporte a clínicas sem psicólogo presencial

---------------------------------------------------------------
8.4 Laudos Psicossociais com Camada de IA
---------------------------------------------------------------

- Correção automática conforme instrumentos oficiais
- Aplicação de pesos e critérios técnicos
- Análises interpretativas com apoio de IA
- Laudos sempre editáveis pelo profissional
- Laudos individuais e por setor
- Referência de qualidade: modelos similares ao RILI

---------------------------------------------------------------
8.5 Ouvidoria Psicossocial
---------------------------------------------------------------

- Canal dedicado para denúncias e reclamações
- Foco em assédio e situações sensíveis
- Garantia de confidencialidade
- Controle de acesso e auditoria

---------------------------------------------------------------
8.6 Consultas Psicológicas e Psiquiátricas
---------------------------------------------------------------

- Atendimentos de emergência e crise
- Atendimentos periódicos
- Registro como ação mitigadora de risco

---------------------------------------------------------------
8.7 Avaliações Pré e Pós Atividades de Alto Risco
---------------------------------------------------------------

Exemplos:
- Embarque
- Trabalho em altura
- Espaço confinado
- Ambientes críticos

Objetivos:
- Avaliar condição psicológica antes e depois
- Analisar nexo causal em casos de adoecimento
- Apoiar decisões clínicas e organizacionais

---------------------------------------------------------------
8.8 Validação de Atestados Psicossociais
---------------------------------------------------------------

Escopo:
- CID F
- CID G

Funcionalidades:
- Upload do atestado
- Análise médica
- Possibilidade de teleconsulta
- Conformidade com ANAMT

---------------------------------------------------------------
8.9 Análise Organizacional x Análise Individual
---------------------------------------------------------------

- Análises distintas e complementares
- Podem ocorrer em momentos diferentes
- Ambas alimentam a NR-01

---------------------------------------------------------------
8.10 Educação, Treinamentos e Campanhas
---------------------------------------------------------------

Camadas:
- RH
- Lideranças
- Colaboradores

Funcionalidades:
- Envio automatizado de conteúdos
- Associação de conteúdos a riscos identificados
- Registro de participação

---------------------------------------------------------------
8.11 Adesão dos Colaboradores
---------------------------------------------------------------

- Reconhecida dificuldade com questionários extensos
- Gamificação e micro interações como evolução futura
- Fora do MVP inicial

================================================================
9. PRINCÍPIOS DO MVP NR-01
================================================================

O MVP deve obrigatoriamente contemplar:
- As três fases do processo
- Perfis distintos de usuário
- Validação técnica do engenheiro de segurança
- Integração mínima com SOC
- Geração de evidências normativas

Tudo que não apoiar diretamente a NR-01
fica fora da primeira onda do projeto.

================================================================
FIM DO DOCUMENTO
VERSÃO 0.2
================================================================
