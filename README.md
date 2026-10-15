# Trabalho — Gestão de Operações e Cadeias Globais de Suprimentos

## Caso selecionado

Planejamento de demanda e abastecimento de uma indústria farmacêutica: o caso trata do conflito entre disponibilidade de produto para atender a demanda e risco de perda financeira por vencimento de estoque.

O escopo da melhoria está nas etapas 1 e 2 do processo de previsão de demanda. As etapas 3 a 5 — *sanity check*, planejamento global/produção e logística — são mantidas no TO-BE.

## Artefatos para a entrega

| Entregável | Artefato | Uso na entrega |
|---|---|---|
| Cenário consolidado | [quadro-cenario-problema-farmaceutica-v3.md](quadro-cenario-problema-farmaceutica-v3.md) | Fonte do problema, processo atual, TO-BE, métricas de sucesso e dados ainda não fornecidos. |
| Mapa AS-IS | [Imagem PNG](as-is-v4.png) · [Fonte Mermaid](as-is-v4.mn) | Mapeamento do estado atual com entradas, atividades, responsáveis em raias, saída, pontos de dor, desperdício e lead time informado. |
| Mapa TO-BE | [Imagem PNG](to-be-v1.png) · [Fonte Mermaid](to-be-v1.mn) | Mapa futuro. As etapas alteradas estão em verde; as etapas mantidas estão em cinza. |
| Plano de ação | [planejamento-implementacao-to-be.md](planejamento-implementacao-to-be.md) | Planejamento de implementação: regras, métricas, configuração do AERA, testes, treinamento, entrada em operação, monitoramento e riscos. |

## Estrutura recomendada da apresentação

1. **Problema e contexto**
   - Perda de receita por falta de produto.
   - Perda financeira por produto vencido antes da comercialização.
   - Conflito entre ajustes de Marketing e a necessidade de Supply Chain de reduzir perdas.

2. **AS-IS**
   - Apresentar [as-is-v4.png](as-is-v4.png).
   - Destacar que o ciclo é mensal, que o lead time médio até a disponibilidade para venda é de cinco meses e que o gargalo específico não foi localizado pelo cenário.

3. **TO-BE**
   - Apresentar [to-be-v1.png](to-be-v1.png).
   - Explicar que o AERA passará a gerar a proposta inicial de forecast a partir do planejamento financeiro por SKU.
   - Explicar que ajustes de Marketing deverão ser materiais, justificados e comentados, segundo o limite mínimo definido pelo Supply Chain Global.

4. **Resultados esperados e indicadores**
   - Métricas definidas no caso: nível de D&O e nível de Lost Sales.
   - Antes da apresentação final, registrar fórmula, baseline, meta, fonte e periodicidade de cada métrica.

5. **Plano de ação, riscos e desafios**
   - Usar [planejamento-implementacao-to-be.md](planejamento-implementacao-to-be.md).
   - Destacar a definição de materialidade, a disponibilidade do planejamento financeiro por SKU, a qualidade das justificativas e a definição das métricas como condições de implantação.

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
