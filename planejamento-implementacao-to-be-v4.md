# Planejamento de implementação do TO-BE — v4

Esta versão substitui a v3 para fins de entrega. Ela foi construída a partir do TO-BE definido em [quadro-cenario-problema-farmaceutica-v3.md](quadro-cenario-problema-farmaceutica-v3.md) e dos critérios em [criterios-avaliacao-plano-acao.md](criterios-avaliacao-plano-acao.md).

## 1. Objetivo e limite da implantação

Implantar no AERA, no ciclo mensal de previsão de demanda, as mudanças das etapas 1 e 2:

1. Gerar proposta inicial de forecast a partir do planejamento financeiro aprovado, com granularidade de SKU.
2. Permitir que Marketing avalie a proposta e solicite ajustes com valor, justificativa e comentário.
3. Aplicar a regra de autorização definida pelo Supply Chain Global para cada solicitação de ajuste.
4. Reter solicitações aprovadas e negadas para consulta, auditoria e análise posterior.
5. Consolidar o resultado do fluxo para gerar Lost Sales, D&O, análise de risco e assertividade do forecast frente ao planejamento financeiro.

As etapas 3 a 5 não serão redesenhadas. O forecast consolidado deve continuar chegando ao *sanity check* de Supply Chain Local no formato e prazo acordados.

## 2. Responsabilidades

- **Marketing:** avalia a proposta, solicita ajustes e valida a usabilidade do novo fluxo.
- **Financeiro e unidade de negócio:** publicam a versão aprovada do planejamento financeiro por SKU.
- **Supply Chain Global:** define a regra de autorização, aprova sua configuração e designa o decisor quando houver decisão humana.
- **Supply Chain Local:** valida a continuidade da saída para o *sanity check* e participa da simulação do ciclo mensal.
- **Responsável técnico pelo AERA:** é designado no Gate 0 para configurar, testar, publicar, monitorar e suportar a solução.
- **Decisor de autorização:** é identificado nominalmente no Gate 0 caso a regra exija decisão humana.

## 3. Gate 0 — condições obrigatórias antes da configuração

O Gate 0 só é aprovado quando as definições abaixo estiverem documentadas, versionadas e aprovadas por Marketing, Financeiro/unidade de negócio, Supply Chain Global, Supply Chain Local e responsável técnico pelo AERA.

1. **Regra de autorização**
   - Limite mínimo, unidade, granularidade, vigência e comportamento para solicitações abaixo, iguais e acima do limite.
   - Momento da aplicação da regra, estados possíveis da solicitação, decisor, prazo de decisão e tratamento de negativa, devolução ou pendência.

2. **Fonte financeira**
   - Fonte, versão, período, campos e responsável pela publicação do planejamento financeiro por SKU.
   - Tratamento para dado ausente, inconsistente ou indisponível.

3. **Ajustes, auditoria e acessos**
   - Valor solicitado, justificativa e comentário como campos obrigatórios.
   - Dados a reter: proposta inicial, solicitação, decisão, status, usuário, data/hora e regra aplicada.
   - Perfis autorizados a solicitar, decidir, configurar a regra e consultar a auditoria; período de retenção.

4. **Saída para a etapa 3**
   - Formato, prazo e destinatário do forecast consolidado para o *sanity check* já existente.

5. **Métricas**
   - Fórmula, fonte, granularidade, periodicidade, responsável, baseline e meta para D&O e Lost Sales.
   - Forma de apresentar risco e assertividade do forecast versus o planejamento financeiro.

**Saída do Gate 0:** especificação funcional aprovada, responsáveis nomeados, matriz de acessos aprovada e critérios de aceite versionados. Sem essa saída, a configuração e a entrada em produção não começam.

## 4. Plano de execução

### Fase 1 — Preparar dados e ambiente

- Confirmar a disponibilidade da versão aprovada do planejamento financeiro por SKU no AERA.
- Validar uma amostra de SKU, período e valor contra a fonte aprovada.
- Configurar os perfis de acesso definidos no Gate 0.

**Critério de saída:** a carga ou consulta de teste reproduz corretamente a fonte financeira e os acessos bloqueiam ações fora de perfil.

### Fase 2 — Configurar o fluxo no AERA

- Configurar a proposta inicial de forecast a partir do planejamento financeiro por SKU.
- Configurar a solicitação de ajuste com valor, justificativa e comentário obrigatórios.
- Configurar a regra de autorização, os estados da solicitação e a trilha de auditoria.
- Configurar a consolidação do resultado do fluxo e os relatórios de Lost Sales, D&O, risco e assertividade.

**Critério de saída:** ambiente de homologação disponível com as funcionalidades previstas no TO-BE.

### Fase 3 — Testar requisitos e exceções

- Validar proposta inicial identificada por SKU, período e versão financeira.
- Testar solicitação sem justificativa ou comentário, que deve ser impedida.
- Testar os comportamentos aprovados para solicitações abaixo, iguais e acima do limite.
- Testar solicitação aprovada, negada, devolvida ou pendente, conforme os estados definidos no Gate 0.
- Confirmar que a auditoria mostra proposta inicial, solicitação, decisão, status, usuário, data/hora e regra aplicada.
- Validar que o AERA bloqueia ação fora de perfil.
- Conferir relatórios contra as fórmulas aprovadas para Lost Sales, D&O, risco e assertividade.

**Critério de saída:** todos os critérios de aceite aprovados; nenhuma falha crítica aberta.

### Fase 4 — Simular o ciclo mensal completo

- Executar em homologação um ciclo completo, da publicação do plano financeiro até o recebimento do forecast consolidado por Supply Chain Local.
- Validar que o *sanity check* recebe o formato e o prazo definidos, sem alteração nas etapas 3 a 5.
- Obter aprovação de Marketing, Supply Chain Local, Supply Chain Global e Financeiro/unidade de negócio.

**Critério de saída:** aprovação formal para entrada em produção.

### Fase 5 — Preparar as pessoas e entrar em produção

- Treinar Marketing, decisores de autorização, Supply Chain Local e suporte do AERA.
- Comunicar regra, calendário mensal, perfis de acesso e canal de suporte.
- Registrar a versão do planejamento financeiro e a regra aplicável antes de abrir as solicitações do primeiro ciclo.
- Executar o primeiro ciclo mensal e acompanhar incidentes até a consolidação.

**Critério de saída:** primeiro ciclo concluído, conciliado e aceito por Supply Chain Local.

### Fase 6 — Estabilizar e monitorar

- Revisar solicitações, decisões, exceções, acessos e registros de auditoria dos ciclos iniciais.
- Emitir D&O, Lost Sales, risco e assertividade conforme as definições aprovadas.
- Comparar os indicadores com o baseline e registrar ações corretivas quando houver desvio.

**Critério de saída:** relatório de estabilização e decisão formal de continuidade do novo fluxo.

## 5. Riscos, condição de superação e decisão

### Fonte financeira incorreta, incompleta ou indisponível

- **Prevenção:** validar versão, campos e amostra de SKU antes de cada ciclo.
- **Condição de superação:** a fonte aprovada está disponível e conciliada para o período.
- **Se a condição não for atendida:** bloquear a geração da proposta; não abrir o novo fluxo naquele ciclo.

### Regra de autorização ambígua ou não aprovada

- **Prevenção:** documentar a regra e testar todos os comportamentos definidos no Gate 0.
- **Condição de superação:** há regra versionada, decisor definido quando aplicável e testes aprovados.
- **Se a condição não for atendida:** não publicar a configuração nem iniciar a produção.

### Falta de rastreabilidade ou acesso indevido

- **Prevenção:** tornar os campos obrigatórios, reter os dados definidos e testar perfis e trilha de auditoria.
- **Condição de superação:** auditoria completa e bloqueios de perfil aprovados em homologação.
- **Se a condição não for atendida:** corrigir em homologação; não liberar o fluxo.

### Atraso ou ausência de decisão de autorização

- **Prevenção:** definir decisor, prazo e tratamento de pendência no Gate 0.
- **Condição de superação:** o decisor está nomeado e o teste do fluxo de pendência foi aprovado.
- **Se a condição não for atendida antes da entrada em produção:** não liberar o novo fluxo.
- **Se a indisponibilidade ocorrer em um ciclo após a entrada em produção:** usar temporariamente o fluxo atual das etapas 1 e 2 no ciclo afetado e registrar a pendência para correção.

### Métricas sem definição ou sem consistência

- **Prevenção:** aprovar fórmula, fonte, baseline, meta, periodicidade e responsável antes da produção.
- **Condição de superação:** relatórios reproduzem as fórmulas aprovadas e identificam fonte, período, granularidade e versão.
- **Se a condição não for atendida antes da entrada em produção:** não liberar o novo fluxo; corrigir os relatórios e repetir a validação.
- **Se a inconsistência for identificada após a entrada em produção:** corrigir os relatórios, repetir a validação e não encerrar a estabilização enquanto a condição não for atendida.

### Ruptura no fluxo posterior

- **Prevenção:** simular a entrega do forecast consolidado ao *sanity check* antes da produção.
- **Condição de superação:** Supply Chain Local aceita formato, prazo e conteúdo da saída.
- **Se a condição não for atendida:** não colocar o novo fluxo em produção até ajustar a integração.

### Baixa adoção do novo fluxo

- **Prevenção:** treinamento, comunicação do calendário e suporte no primeiro ciclo.
- **Condição de superação:** os usuários dos perfis previstos conseguem executar o fluxo em simulação e registram dúvidas resolvidas.
- **Se a condição não for atendida:** reforçar treinamento e suporte antes de ampliar o uso.

## 6. Contingência

Se houver falha crítica antes da consolidação do forecast, o ciclo afetado volta temporariamente ao fluxo atual das etapas 1 e 2. Os registros já gerados no AERA são preservados para diagnóstico. As etapas 3 a 5 continuam inalteradas.

O retorno ao novo fluxo exige correção validada em homologação e nova aprovação de negócio conforme os critérios da fase de simulação.

## 7. Condições de conclusão

A implantação é concluída quando:

1. O Gate 0 está aprovado e todos os responsáveis estão nomeados.
2. Os testes e a simulação mensal foram aprovados sem falha crítica.
3. Um ciclo mensal em produção foi concluído sem contingência.
4. Supply Chain Local confirmou o uso do forecast consolidado no *sanity check* existente.
5. A auditoria retorna as solicitações aprovadas e negadas com todos os dados exigidos.
6. D&O, Lost Sales, risco e assertividade são emitidos conforme as definições aprovadas.
7. O relatório de estabilização registra a decisão de continuidade.
