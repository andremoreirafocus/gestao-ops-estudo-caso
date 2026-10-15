# Planejamento de implementação do TO-BE

## 1. Objetivo e escopo

Implantar no AERA o novo processo de previsão de demanda das etapas 1 e 2:

1. O AERA gera uma proposta inicial de forecast a partir do planejamento financeiro por SKU.
2. Marketing avalia a proposta e solicita ajustes conforme sua percepção realista do mercado.
3. Cada ajuste deve ser material, justificado e comentado, seguindo o limite mínimo e a regra de autorização definidos pelo Supply Chain Global.

As etapas 3 a 5 permanecem como estão. Elas continuarão recebendo o resultado do processo de previsão, sem redesenho de suas atividades.

## 2. Premissas já definidas

- O ciclo de previsão é mensal.
- O planejamento financeiro possui granularidade de SKU e está no SAP Analytics Cloud Planning.
- Cada gerente de Marketing insere sua previsão no AERA.
- O AERA consolida as previsões.
- Supply Chain Local continua realizando o *sanity check* e a análise de viabilidade nas etapas posteriores.
- As métricas de sucesso previstas são nível de D&O e nível de Lost Sales.

## 3. Plano de implementação

+--------------------------------+----------------------------------------------+--------------------------------------------------+------------------------------------------------------------------+
| Fase                           | Atividades                                   | Responsáveis envolvidos                          | Entregável / critério de saída                                   |
+================================+==============================================+==================================================+==================================================================+
| 1. Definição das regras        | Definir o que caracteriza um ajuste          | Marketing; Supply Chain Global; Supply Chain     | Regra de negócio aprovada e pronta para configuração no AERA.    |
|                                | material; estabelecer o limite mínimo;       | Local                                            |                                                                  |
|                                | definir quando há autorização e quem a       |                                                  |                                                                  |
|                                | realiza no Supply Chain Global; padronizar o |                                                  |                                                                  |
|                                | texto mínimo de justificativa e comentário.  |                                                  |                                                                  |
+--------------------------------+----------------------------------------------+--------------------------------------------------+------------------------------------------------------------------+
| 2. Definição das métricas      | Registrar a definição de D&O e Lost Sales:   | Marketing; Supply Chain Local; Supply Chain      | Ficha de indicadores aprovada.                                   |
|                                | fórmula, granularidade, fonte,               | Global; Financeiro                               |                                                                  |
|                                | periodicidade, responsável, baseline e meta. |                                                  |                                                                  |
+--------------------------------+----------------------------------------------+--------------------------------------------------+------------------------------------------------------------------+
| 3. Preparação dos dados        | Validar a disponibilidade do planejamento    | Financeiro; unidade de negócio; responsável pelo | Dados de planejamento financeiro por SKU validados para          |
|                                | financeiro por SKU para uso na proposta      | AERA a designar                                  | carga/consulta.                                                  |
|                                | inicial do AERA; definir o período de        |                                                  |                                                                  |
|                                | referência e os campos necessários.          |                                                  |                                                                  |
+--------------------------------+----------------------------------------------+--------------------------------------------------+------------------------------------------------------------------+
| 4. Configuração do AERA        | Configurar a geração da proposta inicial por | Responsável pelo AERA a designar; Marketing;     | Ambiente configurado e trilha de alterações disponível para      |
|                                | SKU; tela/fluxo de solicitação de ajuste;    | Supply Chain Global                              | teste.                                                           |
|                                | campos de justificativa e comentário;        |                                                  |                                                                  |
|                                | registro de valor original, valor solicitado |                                                  |                                                                  |
|                                | e decisão; regra de limite mínimo e          |                                                  |                                                                  |
|                                | autorização.                                 |                                                  |                                                                  |
+--------------------------------+----------------------------------------------+--------------------------------------------------+------------------------------------------------------------------+
| 5. Teste integrado             | Testar um ciclo mensal completo: proposta do | Marketing; Supply Chain Local; Supply Chain      | Casos de teste aprovados e pendências críticas corrigidas.       |
|                                | AERA, avaliação de Marketing, ajuste,        | Global; Financeiro; responsável pelo AERA a      |                                                                  |
|                                | aplicação da regra de materialidade,         | designar                                         |                                                                  |
|                                | autorização e consolidação da previsão.      |                                                  |                                                                  |
|                                | Conferir que a saída continua utilizável     |                                                  |                                                                  |
|                                | pelo *sanity check* de Supply Chain.         |                                                  |                                                                  |
+--------------------------------+----------------------------------------------+--------------------------------------------------+------------------------------------------------------------------+
| 6. Preparação das pessoas      | Orientar gerentes de Marketing sobre a       | Marketing; Supply Chain Global; Supply Chain     | Materiais de orientação e responsáveis treinados.                |
|                                | proposta inicial, solicitação de ajuste,     | Local                                            |                                                                  |
|                                | justificativa e comentário; orientar Supply  |                                                  |                                                                  |
|                                | Chain Global sobre a autorização; divulgar a |                                                  |                                                                  |
|                                | mudança no ciclo mensal.                     |                                                  |                                                                  |
+--------------------------------+----------------------------------------------+--------------------------------------------------+------------------------------------------------------------------+
| 7. Entrada em operação         | Executar o primeiro ciclo mensal no novo     | Marketing; Supply Chain Local; Supply Chain      | Primeiro ciclo concluído no AERA pelo novo processo.             |
|                                | fluxo; manter acompanhamento reforçado das   | Global                                           |                                                                  |
|                                | solicitações e decisões.                     |                                                  |                                                                  |
+--------------------------------+----------------------------------------------+--------------------------------------------------+------------------------------------------------------------------+
| 8. Monitoramento e             | Acompanhar D&O e Lost Sales conforme a ficha | Marketing; Supply Chain Local; Supply Chain      | Avaliação do ciclo e decisões de estabilização registradas.      |
| estabilização                  | de indicadores; revisar ajustes,             | Global; Financeiro                               |                                                                  |
|                                | justificativas e autorizações; corrigir      |                                                  |                                                                  |
|                                | regras ou configuração quando houver desvio  |                                                  |                                                                  |
|                                | operacional.                                 |                                                  |                                                                  |
+--------------------------------+----------------------------------------------+--------------------------------------------------+------------------------------------------------------------------+

## 4. Fluxo futuro a ser implantado

1. Planejamento financeiro por SKU é disponibilizado para o AERA.
2. AERA gera proposta inicial de forecast.
3. Gerente de Marketing avalia a proposta.
4. Se não houver ajuste, a previsão segue para consolidação.
5. Se houver ajuste, Marketing registra valor solicitado, justificativa e comentário.
6. A regra de materialidade é aplicada.
7. Quando aplicável, Supply Chain Global realiza a autorização conforme a regra definida.
8. A previsão consolidada segue para o *sanity check* já existente de Supply Chain Local.

## 5. Decisões pendentes antes da configuração

1. Definição formal de D&O e Lost Sales, inclusive baseline e meta.
2. Critério numérico para classificar um ajuste como material.
3. Regra exata de autorização acima do limite: responsável, prazo e tratamento de rejeição ou devolução.
4. Forma de disponibilização do planejamento financeiro por SKU ao AERA.
5. Responsável técnico pelo AERA e pelo suporte após entrada em operação.

## 6. Riscos e controles

+--------------------------------+---------------------------------------------------------+------------------------------------------------------------------+
| Risco                          | Consequência                                            | Controle proposto                                                |
+================================+=========================================================+==================================================================+
| Planejamento financeiro por    | O AERA não consegue gerar proposta inicial confiável.   | Validar os dados antes da configuração e aprovar critério de     |
| SKU indisponível, incompleto   |                                                         | qualidade.                                                       |
| ou inconsistente               |                                                         |                                                                  |
+--------------------------------+---------------------------------------------------------+------------------------------------------------------------------+
| Limite de materialidade        | Excesso de autorizações ou ajustes relevantes sem       | Testar a regra em casos representativos e revisar após os        |
| inadequado                     | controle.                                               | primeiros ciclos.                                                |
+--------------------------------+---------------------------------------------------------+------------------------------------------------------------------+
| Justificativas genéricas       | Perde-se a rastreabilidade pretendida pelo TO-BE.       | Padronizar campos mínimos e revisar uma amostra de solicitações  |
|                                |                                                         | no início.                                                       |
+--------------------------------+---------------------------------------------------------+------------------------------------------------------------------+
| Atraso de autorização          | O ciclo mensal pode atrasar.                            | Definir responsável, prazo e fluxo de tratamento de pendências   |
|                                |                                                         | antes da entrada em operação.                                    |
+--------------------------------+---------------------------------------------------------+------------------------------------------------------------------+
| D&O e Lost Sales sem definição | Não será possível demonstrar resultado esperado.        | Aprovar a ficha de indicadores antes do primeiro ciclo no novo   |
| ou baseline                    |                                                         | fluxo.                                                           |
+--------------------------------+---------------------------------------------------------+------------------------------------------------------------------+

## 7. Evidências de implantação

- Regra de materialidade e autorização aprovada.
- Registro de testes do ciclo completo.
- Material de orientação das equipes.
- Primeiro ciclo mensal executado no novo fluxo.
- Painel ou relatório inicial de D&O e Lost Sales, conforme definição aprovada.
