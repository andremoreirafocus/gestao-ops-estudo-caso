# Adequação do case Magalu ao enunciado — versão 3

Este documento avalia se o case Magalu (caminho de um pedido do marketplace até a entrega ao cliente) é adequado ao trabalho de Gestão de Operações e Cadeias Globais de Suprimentos e orienta como abordá-lo. Não contém conteúdo do trabalho em si. Ele substitui a proposta anterior (case_magalu.md, versão 1), que era um esboço sem análise das fontes.

## 1. O caso e a pergunta que ele permite responder

**Empresa:** Magalu (Magazine Luiza), varejista que também opera um marketplace e uma empresa de logística própria, o Magalog.

**Marketplace (explicação para quem não conhece o termo):** é a parte do site e do aplicativo em que lojistas independentes, chamados de sellers (vendedores), anunciam e vendem seus produtos usando a plataforma do Magalu. O Magalu não é o dono do estoque nesse caso. Quando o Magalu vende produtos do próprio estoque, isso é chamado de 1P. Quando vende produtos de terceiros, é 3P.

**Processo candidato:** o caminho de um pedido do marketplace, do momento em que o pagamento é aprovado até o momento em que o cliente recebe a mercadoria, nas modalidades em que o vendedor mantém o estoque (ou seja, fora do fulfillment, explicado na seção 3).

**Pergunta:** onde o pedido de marketplace perde tempo entre o pagamento aprovado e a entrega, e como esse caminho pode cumprir melhor o prazo prometido ao cliente?

**Por que a pergunta faz sentido (dados da própria empresa):**

- O fulfillment (o serviço em que o Magalu guarda e envia os produtos do vendedor) respondia por 28% dos pedidos do marketplace no 3T25 e por 29% no 2T26. Isso significa que cerca de 71% dos pedidos ainda passam por outras modalidades, e é razoável supor que nelas o vendedor guarda o estoque e participa de etapas do processo. Tanto o "cerca de 71%" (100% menos 29%) quanto a suposição sobre o vendedor são inferências do grupo, não números ou afirmações da empresa.
- O avanço do fulfillment parece ter desacelerado: a empresa informou alta de 4 pontos percentuais (p.p.) no 3T25 sobre o 3T24 e de 2 p.p. no 2T26 sobre o 2T25. Comparar esses dois números é inferência do grupo, porque são trimestres diferentes.
- O marketplace vendeu R$ 3,9 bilhões no 3T25 (38% do e-commerce do Magalu) e R$ 3,6 bilhões no 2T26.
- O Magalu declara que prioriza "modalidades de entrega mais eficientes" no marketplace.

Fontes: [Divulgação de Resultados 3T25](https://ri.magazineluiza.com.br/Download.aspx?Arquivo=DrGoHuqyLORrX4ht41IIlA%3D%3D) e [Divulgação de Resultados 2T26](https://investidor10.com.br/acoes/link_comunicado/MGLU3/47047/) (relatórios de resultados publicados pela empresa).

## 2. Aderência ao tema da disciplina

Este é o ponto mais forte do caso. A disciplina trata de operações e cadeias de suprimentos, e o caso envolve diretamente: estoque, armazenagem, expedição (saída dos produtos), transporte e entrega ao consumidor (a chamada última milha), integração entre empresas diferentes (vendedor e Magalu) e indicadores de nível de serviço. Diferentemente de um caso de atendimento ao cliente, aqui há fluxo físico de mercadorias, o que casa com o nome da disciplina.

## 3. O que as fontes públicas oferecem

### 3.1 Como o pedido de marketplace percorre o processo

O Magalu não publica um mapa único do processo. O que se consegue montar vem de três tipos de fonte: o próprio Magalu (relatórios e páginas de serviço), blogs de empresas que integram sistemas de vendedores ao Magalu e relatos de clientes. Em linguagem simples, o caminho é este:

1. **O cliente compra e o pagamento é aprovado.** A partir daí corre o prazo de entrega prometido ao cliente na hora da compra.

2. **O vendedor prepara o pedido.** Ele emite a nota fiscal, separa o produto no seu estoque e o embala. Pelo acordo de nível de serviço (SLA, o contrato que fixa os prazos e metas que o vendedor precisa cumprir), o vendedor deve atualizar o status de separação do estoque em menos de 1 dia útil depois da confirmação do pedido. Um resumo de busca indicou que pedidos aprovados até as 11h devem ser despachados no mesmo dia e os aprovados depois, em 1 dia útil, mas não consegui confirmar essa regra em fonte oficial.

3. **O produto sai do vendedor.** Aqui há modalidades diferentes, e as fontes divergem na contagem. Um blog de integração conta três (Agências Magalu, Coletas e Entrega Ultra Rápida); outro conta cinco, incluindo postagem pelos Correios e fulfillment. As principais são:
   - **Agências Magalu:** o vendedor leva o produto a uma das mais de 400 lojas do Magalu que funcionam como ponto de postagem (o Magalu tem 1.246 lojas no total, segundo o relatório de resultados).
   - **Magalu Coletas:** a equipe do Magalu retira os produtos no centro de distribuição ou na loja do vendedor, sem custo adicional, desde que o vendedor atinja um volume mínimo diário e esteja na área de cobertura.
   - **Entrega Ultra Rápida:** pedidos aprovados até as 11h são coletados no endereço do vendedor e entregues no mesmo dia ou no dia seguinte.
   - **Fulfillment:** o vendedor envia o estoque antes ao Magalu, que armazena, separa, embala e envia (explicado abaixo). Esta modalidade fica fora do recorte proposto.

4. **O Magalog transporta a encomenda.** O Magalog é a empresa de logística do grupo. A encomenda passa por centros de distribuição (CDs, galpões onde as mercadorias são recebidas, separadas e redirecionadas) e depois segue para a entrega. O relatório da empresa fala em 21 CDs, enquanto sites de terceiros falam em 270 "centros de distribuição e cross-dockings" (cross-docking é a passagem rápida da mercadoria por um galpão sem armazená-la). As duas contagens podem usar critérios diferentes, e não consegui conciliá-las.

5. **A entrega é feita ao cliente.** O vendedor precisa também atualizar o rastreamento: "em transporte" e "entrega realizada", cada um em até 1 dia útil.

6. **Comprovação e atendimento.** Se o Magalu pedir o comprovante de entrega, o vendedor tem 5 dias úteis para enviá-lo. O atendimento ao cliente do vendedor funciona de segunda a sexta, das 9h às 18h, com resposta em até 2 dias úteis para 98% dos registros.

**O que é o fulfillment (fora do recorte, mas importante como contraste):** o vendedor envia o estoque ao Magalu, que cuida de receber, armazenar, separar, embalar, enviar e tratar devoluções. A promessa é de entrega no mesmo dia ou no dia seguinte. Pelo site oficial, os serviços de armazenagem e manuseio são gratuitos até dezembro de 2026 (para tamanhos selecionados) e depois passam a ser cobrados (por exemplo, de R$ 0,05 a R$ 37,90 por venda, conforme peso e volume). Só são aceitos produtos de giro alto e não perecíveis. Fontes: [Magalu Entregas – Fulfillment](https://www.magaluentregas.com.br/servicos/fulfillment), [Anymarket – guia do Magalu Entregas](https://marketplace.anymarket.com.br/magalu-entregas-guia-completo/), [Bling – Magalu Entregas](https://blog.bling.com.br/magalu-entregas/).

### 3.2 Metas que o Magalu cobra do vendedor (SLA oficial)

Segundo o acordo de nível de serviço publicado no blog oficial do Magalu:

- Mais de 95% dos pedidos confirmados devem ser entregues dentro do prazo informado ao cliente.
- Reclamações abaixo de 5% das vendas faturadas.
- Casos nos canais externos de reclamação abaixo de 1%. Esses canais são o SAC (Serviço de Atendimento ao Consumidor), as redes sociais, a imprensa, o Reclame Aqui (site em que consumidores registram queixas contra empresas), o Procon (órgão de defesa do consumidor) e o Consumidor.gov (plataforma do governo para reclamações).
- Descumprir as metas pode levar à suspensão do vendedor no marketplace até a correção ou até ao desligamento imediato.

Fonte: [Acordo de nível de serviço do vendedor (SLA) – Universo Magalu](https://universo.magalu.com/blog/artigo/acordo-de-nivel). Não consegui identificar a data de publicação na página.

Um blog de consultoria (Arcos Scale) cita metas de 97% para despacho e entrega no prazo e de cancelamento abaixo de 2%. Essas metas são mais rígidas que as do SLA oficial e não consegui confirmá-las no Magalu, então não devem ser usadas como fato. Fonte: [Arcos Scale](https://blog.arcosscale.com.br/melhorar-reputacao-magalu/).

### 3.3 Números públicos da operação logística

- **Magalog:** mais de 5,5 milhões de entregas no 3T25 para empresas fora do grupo, 12 grandes operações que se tornaram clientes nesse trimestre (entre elas Arezzo, C&A e Renner) e prêmio de nível de serviço (nstech Logistics Advantage 2025). No 2T26, os pedidos entregues para terceiros subiram 15%, e o Magalog passará a prestar serviços logísticos para a Amazon.
- **Investimento em logística:** R$ 6,9 milhões no 2T26 contra R$ 10,9 milhões no 2T25, queda de 36%. Os investimentos totais caíram 25%. A empresa não explica essa queda no trecho que li.

### 3.4 Dores e evidências de problema

- **Dificuldade de integração para vendedores com mais de um estoque:** um guia de integrador relata frete calculado a partir do CD errado e estoque baixado no local errado quando o vendedor opera vários CDs sem sistema integrado. É a visão de uma empresa de integração, não do Magalu. Fonte: [Anymarket](https://marketplace.anymarket.com.br/magalu-entregas-guia-completo/).
- **Relatos de clientes no Reclame Aqui:** atrasos de entrega, produto parado em centro logístico por 6 dias, falta de informação e atendimento só por respostas automáticas. Exemplos: [geladeira parada no centro logístico](https://www.reclameaqui.com.br/magazine-luiza-loja-online/atraso-na-entrega-de-geladeira-brastemp-bre66ak-comprada-na-magalu-e-parad_PnjrbP6ELQb41gRb/), [atraso e falta de comunicação](https://www.reclameaqui.com.br/magazine-luiza-loja-online/atraso-na-entrega-de-produto-comprado-no-magalu-e-falta-de-comunicacao_73vVVX6RBMydQarZ/), [atraso e falha de comunicação com atendimento automatizado](https://www.reclameaqui.com.br/magazine-luiza-loja-online/magalu-atraso-na-entrega-e-falha-na-comunicacao-devido-a-ia-gerando-insatisfacao-do-consumidor_2wzLIK3dMVkPbohB/). Esses relatos são individuais, a página reúne vendas próprias e de vendedores, e eles não provam a taxa real de atraso.
- **Relatos de vendedores:** bloqueio de acesso ao painel e falta de suporte para lojistas. Exemplos: [falta de suporte ao lojista](https://www.reclameaqui.com.br/magalu-vendas/reclamacao-magalu-marketplace-para-lojista-falta-de-suporte_C7vV8i6U8M5A6k66/), [bloqueio de acesso e impossibilidade de envio](https://www.reclameaqui.com.br/magazine-luiza-loja-online/bloqueio-de-acesso-e-impossibilidade-de-envio-de-pedidos-no-marketplace-mag_71Tt9KbAgQKEd9wT/).

## 4. Avaliação de adequação por exigência do enunciado

Legenda: **Adequada** = fontes públicas sustentam; **Parcial** = sustentada em parte, o grupo complementa; **Fraca** = depende de suposição ou dado próprio.

**1. Problema/contexto com dados e exemplos concretos — PARCIAL**
- Fontes sustentam: fulfillment em 28% e 29% dos pedidos do marketplace, avanço mais lento, meta de 95% de entrega no prazo, relatos de atraso.
- Grupo produz: a ligação entre os dados da empresa e a dor no processo. Não há taxa pública de atraso por modalidade.
- Risco: apresentar relato de cliente ou número de blog como medida.

**2. Objetivo principal mensurável (X%, Y%, impacto na rentabilidade) — PARCIAL**
- Fontes sustentam: o SLA fornece metas de referência (95% de entregas no prazo, reclamações abaixo de 5%), e as tarifas do fulfillment dão uma base de custo.
- Grupo produz: a linha de base (situação atual medida, usada como ponto de comparação), que não é pública, e a justificativa de X e Y.
- Risco: metas sem base real; tratar a meta do SLA como se fosse o desempenho atual.

**3. Objetivos secundários — ADEQUADA**
- Fontes sustentam: padronização entre modalidades, redução de reclamações externas, melhor integração com vendedores e menor custo unitário (o Magalu fala em aumentar a densidade da malha logística, isto é, ter mais entregas na mesma rede, o que reduz o custo por entrega).
- Grupo produz: escolha e justificativa dos relevantes.
- Risco: baixo.

**4. Processo identificado, com início e fim — ADEQUADA**
- Fontes sustentam: o início (pagamento aprovado) e o fim (entrega realizada) são definidos pelo próprio SLA.
- Grupo produz: delimitação da modalidade (por exemplo, coleta pelo Magalu) e do que fica de fora.
- Risco: escopo largo demais, juntando todas as modalidades, ou dependente de uma modalidade que o Magalu pode alterar.

**5. Mapa do estado atual (entradas, atividades, saídas e raias, isto é, faixas do mapa que mostram quem executa cada etapa) — PARCIAL**
- Fontes sustentam: etapas do vendedor, do Magalog e do cliente, via SLA, guias e páginas de serviço.
- Grupo produz: as etapas internas do Magalog (recebimento no CD, triagem, rotas), que não são detalhadas publicamente, e os tempos de cada etapa.
- Risco: preencher lacunas com suposição sem declarar.

**6. Pontos de dor — PARCIAL**
- Fontes sustentam: integração em vendedores com mais de um estoque, atraso e falta de informação (relatos).
- Grupo produz: priorização com evidência própria (por exemplo, amostra de reclamações).
- Risco: tratar queixas de um site de reclamação como representativas de todos os pedidos.

**7. Gargalos — FRACA**
- Fontes sustentam: não há dados de tempo por etapa nem de fila nos CDs.
- Grupo produz: identificação de onde o fluxo trava, por inferência apoiada em evidência.
- Risco: afirmar gargalo sem prova, por exemplo atribuir o atraso ao vendedor quando ele pode estar no transporte.

**8. Desperdícios do Lean (método de gestão que busca eliminar tudo que não agrega valor ao cliente, como espera, retrabalho e movimentação desnecessária) — PARCIAL**
- Fontes sustentam: espera (produto parado em CD, segundo um relato), movimentação e transporte entre CDs, estoque em local errado (integração) e retrabalho por informação incorreta.
- Grupo produz: classificação e justificativa de cada desperdício, ligada a uma etapa do mapa.
- Risco: rotular sem ligar ao fluxo ou sem evidência.

**9. Melhorias específicas e justificativas — ADEQUADA**
- Fontes sustentam: os pontos de dor e as ferramentas do Magalu (coleta, agências, fulfillment) permitem ligar cada melhoria a uma dor.
- Grupo produz: propostas concretas, cada uma justificada contra um ponto de dor.
- Risco: propor algo que o Magalu já faz (por exemplo, migração para fulfillment) sem acrescentar nada.

**10. Mapa do estado futuro com destaques — ADEQUADA**
- Fontes sustentam: depende só do mapa atual.
- Grupo produz: desenho e marcação das alterações.
- Risco: baixo.

**11. Resultados esperados em métricas — FRACA**
- Fontes sustentam: não há tempo de ciclo nem custo por pedido por modalidade.
- Grupo produz: estimativas declaradas, com premissas, ancoradas nas metas do SLA e nas tarifas publicadas.
- Risco: números sem lastro.

**12. Benefícios da Gestão de Operações — ADEQUADA**
- Fontes sustentam: cadeia de suprimentos, gestão de estoque, capacidade, nível de serviço e Lean aparecem de forma direta no caso.
- Grupo produz: relação com o conteúdo de aula.
- Risco: baixo.

**13. Plano de ação — ADEQUADA**
- Fontes sustentam: independe de dado.
- Grupo produz: detalhamento das etapas.
- Risco: baixo.

**14. Desafios e riscos — ADEQUADA**
- Fontes sustentam: depender de terceiros (vendedores), custo do fulfillment após dezembro de 2026 e mudança de regras pelo Magalu (por exemplo, em março de 2024 a cobrança de coleta passou a ter seis faixas de distância).
- Grupo produz: reconhecimento e avaliação.
- Risco: baixo.

**Resumo dos níveis (14 exigências):** 7 Adequadas, 5 Parciais, 2 Fracas. As duas Fracas (gargalos e resultados esperados) são de medição.

## 5. Veredito

**O caso é adequado, com ressalva na medição.** O tema é o mais aderente à disciplina entre os casos avaliados, e há uma base de fatos oficiais (relatórios e SLA). A fragilidade está na falta de tempos por etapa. Três condições:

1. **Delimitar o processo a uma modalidade** (por exemplo, o pedido de marketplace com coleta pelo Magalu), com início no pagamento aprovado e fim na entrega, deixando o fulfillment como contraste e não como parte do processo.
2. **Tratar a medição como ponto fraco assumido.** Gargalos e resultados esperados só se sustentam com estimativas declaradas, ancoradas nas metas do SLA e nas tarifas publicadas.
3. **Tratar a origem do atraso como hipótese.** Nenhuma fonte indica em qual etapa os atrasos se concentram (vendedor, coleta, CD ou entrega final). O grupo não deve assumir que a causa está no vendedor.

## 6. Orientação de abordagem

- **Separar três tipos de afirmação ao longo do trabalho:** fato documentado (com fonte), inferência do grupo (com a lógica) e estimativa (com a premissa). Exemplo: "29% de fulfillment" é fato; "cerca de 71% fora do fulfillment" é inferência do grupo.
- **Gerar dado próprio onde as fontes são fracas:**
  - **Amostra de reclamações** recentes no Reclame Aqui sobre atraso de entrega no Magalu (por exemplo, 50 a 100), classificadas pela etapa em que o problema aparece (antes do envio, no transporte, na entrega, na comunicação). Limitações a declarar: quem reclama se autosseleciona (só aparece quem decidiu reclamar), a página mistura vendas próprias e de vendedores e muitos relatos não identificam a etapa.
  - **Registro dos prazos de compras reais**, por quem já fosse comprar no marketplace (não comprar só para a medição): data da compra, data prevista, data efetiva de postagem e data de entrega, com o código de rastreamento. O comprador nem sempre sabe qual modalidade de envio foi usada, então essa amostra pode misturar modalidades. Ela será pequena e deve ser apresentada como ilustrativa.
- **Usar o SLA como parâmetro, não como medida.** As metas do SLA mostram o que o Magalu exige, não o que acontece.
- **Não afirmar nada sobre o interior dos CDs do Magalog** sem fonte. As etapas dentro do CD são lacuna a tratar como suposição declarada.

## 7. Limites e pendências de verificação

- As regras de despacho "até 11h no mesmo dia, depois 1 dia útil" vêm de um resumo de busca, não de página oficial. Verificar na Central do Seller.
- As metas de 97% e de cancelamento abaixo de 2% vêm de um blog de consultoria e não foram confirmadas.
- A data do SLA oficial não está visível; as regras podem ter mudado.
- Não consegui acessar a página de reputação da empresa no Reclame Aqui (acesso negado). Um resumo de busca citava 90,9% de reclamações resolvidas e tempo médio de resposta de 12 dias, mas esses números não foram verificados e não devem ser usados.
- Os relatos de clientes não permitem separar vendas próprias de vendas de vendedores.
- A discrepância entre 21 CDs (relatório) e 270 CDs e cross-dockings (sites de terceiros) não foi esclarecida.
- A divulgação do 1T26 não pôde ser lida (o arquivo obtido era de outro trimestre); o dado de 29% no 1T26 não foi usado.
- As tarifas do fulfillment e as regras de coleta podem mudar; as datas das páginas não são visíveis.
- Não há tempos por etapa (da aprovação do pagamento à entrega) por modalidade.

## 8. Fontes

- [Divulgação de Resultados 3T25 – Magalu](https://ri.magazineluiza.com.br/Download.aspx?Arquivo=DrGoHuqyLORrX4ht41IIlA%3D%3D)
- [Divulgação de Resultados 2T26 – Magalu (via Investidor10)](https://investidor10.com.br/acoes/link_comunicado/MGLU3/47047/)
- [Magalu Entregas – Fulfillment](https://www.magaluentregas.com.br/servicos/fulfillment)
- [Acordo de nível de serviço do vendedor (SLA) – Universo Magalu](https://universo.magalu.com/blog/artigo/acordo-de-nivel)
- [Anymarket – guia completo do Magalu Entregas](https://marketplace.anymarket.com.br/magalu-entregas-guia-completo/)
- [Bling – Magalu Entregas](https://blog.bling.com.br/magalu-entregas/)
- [Arcos Scale – reputação no Magalu](https://blog.arcosscale.com.br/melhorar-reputacao-magalu/)
- [Reclame Aqui – geladeira parada no centro logístico](https://www.reclameaqui.com.br/magazine-luiza-loja-online/atraso-na-entrega-de-geladeira-brastemp-bre66ak-comprada-na-magalu-e-parad_PnjrbP6ELQb41gRb/)
- [Reclame Aqui – atraso e falta de comunicação](https://www.reclameaqui.com.br/magazine-luiza-loja-online/atraso-na-entrega-de-produto-comprado-no-magalu-e-falta-de-comunicacao_73vVVX6RBMydQarZ/)
- [Reclame Aqui – atraso com atendimento automatizado](https://www.reclameaqui.com.br/magazine-luiza-loja-online/magalu-atraso-na-entrega-e-falha-na-comunicacao-devido-a-ia-gerando-insatisfacao-do-consumidor_2wzLIK3dMVkPbohB/)
- [Reclame Aqui – falta de suporte ao lojista](https://www.reclameaqui.com.br/magalu-vendas/reclamacao-magalu-marketplace-para-lojista-falta-de-suporte_C7vV8i6U8M5A6k66/)
- [Reclame Aqui – bloqueio de acesso de vendedor](https://www.reclameaqui.com.br/magazine-luiza-loja-online/bloqueio-de-acesso-e-impossibilidade-de-envio-de-pedidos-no-marketplace-mag_71Tt9KbAgQKEd9wT/)
- [E-Commerce Brasil – mudanças de regras e tarifas (abril de 2024)](https://www.ecommercebrasil.com.br/artigos/shopee-magalu-e-americanas-realizam-mudancas-de-regras-e-tarifas-em-seus-marketplaces)
