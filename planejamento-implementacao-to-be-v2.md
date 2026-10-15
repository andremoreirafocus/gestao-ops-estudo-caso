# Planejamento de implementação do TO-BE — v2

Esta versão substitui `planejamento-implementacao-to-be.md`. Ela foi revisada contra a definição atual do TO-BE em `quadro-cenario-problema-farmaceutica-v3.md`.

## 1. Objetivo e fronteira da mudança

Implantar no AERA as novas etapas 1 e 2 do processo mensal de previsão de demanda:

1. Gerar proposta inicial de forecast a partir do planejamento financeiro por SKU.
2. Permitir que Marketing avalie a proposta e solicite ajustes conforme sua percepção do mercado.
3. Exigir justificativa e comentário em toda solicitação de ajuste.
4. Aplicar a regra de autorização baseada no limite mínimo previamente definido pelo Supply Chain Global.
5. Reter no AERA todas as solicitações — aprovadas ou negadas — para consulta, auditoria e análise posterior.
6. Consolidar os dados alterados e gerar métricas de Lost Sales e D&O, com análises de risco e de assertividade do forecast frente ao planejamento financeiro.

As etapas 3 a 5 permanecem inalteradas. O forecast consolidado continuará alimentando o *sanity check* de Supply Chain Local, o planejamento global/fabril e a logística existentes.

## 2. Governança de implantação

+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Papel                          | Responsabilidade na implantação                            | Fundamentação                                                          |
+================================+============================================================+========================================================================+
| Marketing                      | Avalia a proposta do AERA, solicita ajustes com            | Etapa 2 do TO-BE.                                                      |
|                                | justificativa e comentário e valida a experiência de uso.  |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Supply Chain Global            | Define e aprova o limite mínimo da regra de autorização e  | Etapa 2 do TO-BE.                                                      |
|                                | valida a regra configurada.                                |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Supply Chain Local             | Valida que o forecast consolidado continua apto ao *sanity | Etapa 3, que permanece inalterada.                                     |
|                                | check* e ao envio de volumes.                              |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Financeiro e unidade de        | Disponibilizam a versão aprovada do planejamento           | Plano financeiro e etapa 1 do TO-BE.                                   |
| negócio                        | financeiro por SKU.                                        |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Responsável técnico pelo AERA  | Configura/desenvolve, testa, publica, monitora e dá        | Necessário para viabilizar a implantação.                              |
|                                | suporte ao AERA. A pessoa ou equipe deve ser designada no  |                                                                        |
|                                | Gate 0.                                                    |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Decisor de aprovação/rejeição  | Executa a decisão quando a regra exigir decisão humana.    | Lacuna de responsabilidade a fechar no Gate 0.                         |
|                                | Deve ser designado pelo Supply Chain Global no Gate 0,     |                                                                        |
|                                | pois o TO-BE exige registros de solicitação aprovada ou    |                                                                        |
|                                | negada, mas não nomeia o decisor.                          |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+

## 3. Gate 0 — especificação funcional aprovada

Nenhuma configuração começa sem as definições abaixo, aprovadas por Marketing, Supply Chain Global, Financeiro/unidade de negócio e responsável técnico pelo AERA.

+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Decisão                                            | Definição que precisa ser aprovada                                                             |
+====================================================+================================================================================================+
| Limite mínimo                                      | Valor, unidade, granularidade — por SKU, período e país, se aplicável —, regra para igualdade  |
|                                                    | com o limite e vigência da configuração.                                                       |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Fluxo de autorização                               | Quando a regra é aplicada; se a decisão é automática ou humana; papel decisor; prazo; estados  |
|                                                    | possíveis e tratamento de solicitação negada.                                                  |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Planejamento financeiro por SKU                    | Fonte, versão, período, campos, responsável pela publicação e regra para dado ausente ou       |
|                                                    | inconsistente.                                                                                 |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Ajustes de Marketing                               | Campos obrigatórios: valor solicitado, justificativa e comentário; regra para edição ou        |
|                                                    | cancelamento antes da consolidação.                                                            |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Auditoria e acessos                                | Dados mínimos retidos: proposta inicial, valor solicitado, status, justificativa, comentário,  |
|                                                    | usuário, data/hora e regra/limite aplicados. Período de retenção e perfis que podem solicitar, |
|                                                    | decidir, configurar o limite e consultar auditoria.                                            |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Métricas                                           | Definição de Lost Sales e D&O: fórmula, fonte, granularidade, periodicidade, responsável,      |
|                                                    | baseline, meta e formato de análise de risco/assertividade versus plano financeiro.            |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Continuidade do processo                           | Formato, prazo e destinatário do forecast consolidado para o *sanity check* já existente.      |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+

**Critério de saída:** especificação funcional, matriz de responsabilidades e critérios de aceite aprovados e versionados.

## 4. Requisitos funcionais e critérios de aceite

+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| ID                             | Requisito                                                  | Critério de aceite                                                     |
+================================+============================================================+========================================================================+
| RF-01                          | AERA recebe a versão aprovada do planejamento financeiro   | Para uma amostra definida no Gate 0, SKU, período e valor exibidos no  |
|                                | por SKU.                                                   | AERA correspondem à fonte aprovada.                                    |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| RF-02                          | AERA gera proposta inicial de forecast a partir do         | A proposta é identificável por SKU, período e versão da fonte          |
|                                | planejamento financeiro por SKU.                           | financeira.                                                            |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| RF-03                          | Marketing avalia a proposta e solicita ajuste.             | A solicitação exige valor, justificativa e comentário; o sistema       |
|                                |                                                            | impede o envio se algum campo obrigatório estiver vazio.               |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| RF-04                          | AERA aplica a regra de autorização definida pelo Supply    | Casos abaixo, iguais e acima do limite produzem exatamente o           |
|                                | Chain Global.                                              | comportamento aprovado no Gate 0.                                      |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| RF-05                          | AERA retém todas as solicitações e seus resultados, com    | Consulta de auditoria mostra solicitações aprovadas e negadas com      |
|                                | acesso controlado.                                         | proposta inicial, valores, status, justificativa, comentário, usuário, |
|                                |                                                            | data/hora e regra aplicada; cada perfil possui somente as permissões   |
|                                |                                                            | definidas no Gate 0.                                                   |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| RF-06                          | AERA consolida somente o forecast resultante do fluxo      | O forecast consolidado é disponibilizado no prazo do ciclo mensal e    |
|                                | aprovado.                                                  | pode ser usado pelo *sanity check* de Supply Chain Local sem alteração |
|                                |                                                            | de formato acordado.                                                   |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| RF-07                          | AERA gera Lost Sales, D&O e análises de                    | Relatórios reproduzem as fórmulas aprovadas no Gate 0 e identificam    |
|                                | risco/assertividade.                                       | período, granularidade e versão dos dados utilizados.                  |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+

## 5. Plano de execução

+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Fase                           | Atividades                                                 | Saída obrigatória                                                      |
+================================+============================================================+========================================================================+
| 0. Governança e especificação  | Concluir e aprovar o Gate 0.                               | Especificação funcional aprovada.                                      |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| 1. Preparação de dados         | Validar planejamento financeiro por SKU, acesso do AERA,   | Carga ou consulta de teste aprovada.                                   |
|                                | versões, campos e tratamento de exceções.                  |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| 2. Configuração e              | Implementar proposta inicial, solicitação de ajuste, regra | Ambiente de homologação configurado.                                   |
| desenvolvimento                | de autorização, trilha de auditoria, consolidação e        |                                                                        |
|                                | relatórios.                                                |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| 3. Teste funcional             | Executar todos os critérios RF-01 a RF-07, inclusive       | Evidências de teste e correções críticas concluídas.                   |
|                                | solicitações aprovadas, negadas e dados incompletos.       |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| 4. Simulação do ciclo mensal   | Executar um ciclo completo em homologação com dados        | Aprovação de negócio para entrada em produção.                         |
|                                | representativos, até a entrega do forecast para o *sanity  |                                                                        |
|                                | check*.                                                    |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| 5. Treinamento e comunicação   | Treinar Marketing, decisores de autorização, Supply Chain  | Participantes treinados e material publicado.                          |
|                                | Local e suporte AERA; divulgar regra, calendário e canal   |                                                                        |
|                                | de suporte.                                                |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| 6. Entrada em produção         | Configurar a versão aprovada da regra, executar o primeiro | Primeiro ciclo concluído e conciliado.                                 |
|                                | ciclo mensal e acompanhar incidentes.                      |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| 7. Estabilização               | Revisar solicitações, autorizações, exceções, D&O, Lost    | Relatório de estabilização e decisão de continuidade.                  |
|                                | Sales e análises de risco/assertividade nos ciclos         |                                                                        |
|                                | iniciais.                                                  |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+

## 6. Cenários mínimos de teste

+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Cenário                                            | Resultado esperado                                                                             |
+====================================================+================================================================================================+
| Planejamento financeiro por SKU ausente ou         | AERA bloqueia ou sinaliza o caso conforme a regra aprovada; não gera proposta silenciosamente  |
| inconsistente                                      | incorreta.                                                                                     |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Marketing aceita a proposta sem ajuste             | Forecast segue para consolidação com identificação da proposta original.                       |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Marketing solicita ajuste completo                 | Sistema registra valor, justificativa, comentário, usuário e data/hora.                        |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Marketing tenta solicitar ajuste sem justificativa | Sistema impede o envio.                                                                        |
| ou comentário                                      |                                                                                                |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Ajuste abaixo, igual e acima do limite             | Sistema aplica exatamente a regra definida no Gate 0.                                          |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Solicitação aprovada ou negada                     | Status e trilha completa ficam disponíveis para consulta e auditoria.                          |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Usuário tenta executar ação fora de seu perfil     | AERA bloqueia a ação e registra o evento conforme a configuração aprovada.                     |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Forecast consolidado                               | Supply Chain Local recebe o formato e o prazo definidos, preservando o *sanity check* atual.   |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+
| Métricas e análises                                | Lost Sales, D&O, risco e assertividade exibem a fórmula, período, granularidade e fonte        |
|                                                    | definidos.                                                                                     |
+----------------------------------------------------+------------------------------------------------------------------------------------------------+

## 7. Entrada em produção e contingência

- A entrada em produção ocorre no início de um ciclo mensal, após a simulação aprovada.
- A regra de limite mínimo e a versão do planejamento financeiro usadas no ciclo são registradas antes da abertura das solicitações.
- Se houver falha crítica antes da consolidação, o contingenciamento é executar o fluxo atual de etapas 1 e 2 naquele ciclo, preservando os registros gerados no AERA para diagnóstico. As etapas 3 a 5 não são alteradas.
- A volta ao novo fluxo exige correção validada em homologação e aprovação do responsável de negócio definido no Gate 0.

## 8. Riscos e controles

+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Risco                          | Controle preventivo                                        | Evidência de controle                                                  |
+================================+============================================================+========================================================================+
| Fonte financeira incorreta ou  | Validar versão, campos e amostra de SKUs antes de cada     | Registro de validação da fonte.                                        |
| incompleta                     | ciclo.                                                     |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Regra de autorização ambígua   | Fechar o Gate 0 e testar casos abaixo, iguais e acima do   | Especificação aprovada e resultado dos testes.                         |
|                                | limite.                                                    |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Ajuste sem rastreabilidade     | Tornar justificativa e comentário obrigatórios; reter      | Consulta de auditoria.                                                 |
|                                | todos os status.                                           |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Acesso ou alteração de regra   | Definir perfis, acesso de configuração e período de        | Matriz de acesso aprovada e evidência de teste.                        |
| não autorizados                | retenção no Gate 0; testar bloqueios.                      |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Decisão de autorização         | Definir decisor, prazo e tratamento de pendência no Gate   | Registro do fluxo e do prazo acordado.                                 |
| atrasada                       | 0.                                                         |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Métricas sem interpretação     | Aprovar fórmula, fonte, baseline, meta e responsável antes | Ficha de indicadores aprovada.                                         |
| consistente                    | da produção.                                               |                                                                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+
| Ruptura no fluxo posterior     | Simular a entrega para o *sanity check* antes da produção. | Aprovação da simulação pelo Supply Chain Local.                        |
+--------------------------------+------------------------------------------------------------+------------------------------------------------------------------------+

## 9. Condições de conclusão da implantação

A implantação é considerada concluída quando:

1. Todos os requisitos RF-01 a RF-07 foram aprovados.
2. Um ciclo mensal completo foi executado em produção sem contingência.
3. A consulta de auditoria retorna solicitações aprovadas e negadas com os dados exigidos.
4. Supply Chain Local confirma o recebimento e uso do forecast consolidado no *sanity check* existente.
5. Lost Sales, D&O e análises de risco/assertividade são emitidos conforme as definições aprovadas.
