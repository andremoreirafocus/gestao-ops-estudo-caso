# Trabalho — Gestão de Operações e Cadeias Globais de Suprimentos

## Caso selecionado

Planejamento de demanda e abastecimento de uma indústria farmacêutica: o caso trata do conflito entre disponibilidade de produto para atender a demanda e risco de perda financeira por vencimento de estoque.

O escopo da melhoria está nas etapas 1 e 2 do processo de previsão de demanda. As etapas 3 a 5 — *sanity check*, planejamento global/produção e logística — são mantidas no TO-BE.

## Artefatos para a entrega

| Entregável | Artefato | Uso na entrega |
|---|---|---|
| Apresentação | [projeto_go_cs_forecast_aera-v3.pptx](projeto_go_cs_forecast_aera-v3.pptx) | Arquivo da apresentação que consolida o problema, os mapas AS-IS e TO-BE, indicadores e plano de ação. |
| Cenário consolidado | [quadro-cenario-problema-farmaceutica-v3.md](quadro-cenario-problema-farmaceutica-v3.md) | Fonte do problema, processo atual, TO-BE, métricas de sucesso e dados ainda não fornecidos. |
| Mapa AS-IS | [Imagem PNG](as-is-v17.png) · [Fonte Mermaid](as-is-v7.mn) | Mapeamento do estado atual com entradas, atividades, responsáveis em raias, saída, pontos de dor, desperdício e lead time informado. A legenda foi composta na imagem final. |
| Mapa TO-BE | [Imagem PNG](to-be-v7.png) · [Fonte Mermaid](to-be-v5.mn) | Mapa futuro. As etapas alteradas estão em verde; as etapas mantidas estão em cinza. A legenda foi composta na imagem final. |
| Plano de ação | [planejamento-implementacao-to-be-v4.md](planejamento-implementacao-to-be-v4.md) | Plano vigente: Gate 0, configuração do AERA, testes, simulação, treinamento, contingência, estabilização e riscos com condição de superação e decisão. |
| Critérios de avaliação | [criterios-avaliacao-plano-acao.md](criterios-avaliacao-plano-acao.md) | Critérios derivados das aulas para validar o plano de ação. |
| Análise de conformidade | [analise-conformidade-plano-acao-v4.md](analise-conformidade-plano-acao-v4.md) | Avaliação de conformidade do plano vigente, a v4. |

## Estrutura recomendada da apresentação

1. **Problema e contexto**
   - Perda de receita por falta de produto.
   - Perda financeira por produto vencido antes da comercialização.
   - Conflito entre ajustes de Marketing e a necessidade de Supply Chain de reduzir perdas.

2. **AS-IS**
   - Apresentar [as-is-v17.png](as-is-v17.png).
   - Destacar que o ciclo é mensal, que o lead time médio até a disponibilidade para venda é de cinco meses e que o gargalo específico não foi localizado pelo cenário.

3. **TO-BE**
   - Apresentar [to-be-v7.png](to-be-v7.png).
   - Explicar que o AERA passará a gerar a proposta inicial de forecast a partir do planejamento financeiro por SKU.
   - Explicar que os ajustes de Marketing devem ser justificados e comentados e seguem a regra de autorização definida pelo Supply Chain Global.

4. **Resultados esperados e indicadores**
   - Métricas definidas no caso: nível de D&O e nível de Lost Sales.
   - O Gate 0 do plano prevê registrar fórmula, baseline, meta, fonte e periodicidade de cada métrica antes da produção.

5. **Plano de ação, riscos e desafios**
   - Usar [planejamento-implementacao-to-be-v4.md](planejamento-implementacao-to-be-v4.md).
   - Destacar a regra de autorização, a disponibilidade do planejamento financeiro por SKU, a qualidade das justificativas, a definição das métricas e as condições para superação dos riscos.

## Fontes de orientação acadêmica

- [Enunciado do trabalho](enunciado_trabalho.docx)
- [Aula 03 — Gestão de Operações e Supply Chain Digital](internal/Aula%2003%20-%20MBA%20-%20GO%20e%20SC%20digital%20vf5.pdf)
  - Página 25: elementos do mapa de estado atual.
  - Página 26: requisitos do estado futuro.
  - Página 27: plano de ação, desafios e riscos.

## Documentos de apoio

- [Cenário original transcrito literalmente](quadro-cenario-problema-farmaceutica.md)
- [Respostas que complementaram as lacunas iniciais](as-is-v3-lacunas.md)

As versões anteriores dos diagramas foram mantidas apenas como histórico de trabalho e não devem ser usadas na entrega.
