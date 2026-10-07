# Comparação de força: case Nubank × case Magalu — versão 1

Objetivo: comparar, de forma fria, qual dos dois casos é mais forte para realizar o trabalho pedido no enunciado (mapear um processo, analisar desperdícios do Lean, propor melhorias e medir o impacto).

**Ordem de trabalho:** os critérios, os pesos e as regras de pontuação (seções 2 a 5) foram escritos antes de reler os dois documentos, para não serem ajustados ao que se encontrasse. Em seguida, os dois documentos foram relidos na íntegra, as verificações pendentes que afetavam a pontuação foram feitas (seção 6), e só então os casos foram pontuados.

## 1. O que está sendo comparado

A força do caso para o trabalho do grupo, e não a qualidade do texto dos documentos. Um documento pode ser bem escrito e descrever um caso fraco, e o contrário também. Os dois documentos comparados são case_nubank_v5.md e case_magalu_v5.md.

## 2. Premissas do grupo (valem para os dois casos)

- O grupo não tem acesso a nenhuma empresa. Todo dado do estado atual vem de fontes públicas ou de coleta própria externa (sem acesso interno).
- Casos com estudo de mapeamento já publicado foram descartados antes. Os dois casos comparados passaram por esse filtro.
- O enunciado exige dados concretos, processo com início e fim, mapa atual e futuro, análise de desperdícios do Lean, melhorias justificadas, métricas de impacto, plano de ação e riscos.

## 3. Critérios, pesos e o que se avalia em cada um

Os pesos somam 100. Eles refletem o quanto cada critério influencia a capacidade do grupo de cumprir o enunciado com o que está ao seu alcance.

**C1. Aderência ao tema da disciplina — peso 10.**
Gestão de operações e cadeias globais de suprimentos. Avalia o quanto o caso trata de fluxo de produtos, serviços, estoque, capacidade e nível de serviço. Peso baixo porque o próprio enunciado aceita "atendimento ao cliente" como exemplo de processo.

**C2. Evidência concreta do problema — peso 12.**
O enunciado pede "dados e exemplos concretos". Avalia se existem dados verificáveis e datados que mostrem a ineficiência, e se são oficiais, de terceiros confiáveis ou apenas relatos.

**C3. Documentação do processo atual — peso 15.**
Avalia o quanto das etapas, dos responsáveis, das entradas e das saídas já está descrito em fonte pública, o que determina a qualidade possível do mapa do estado atual.

**C4. Delimitação do processo — peso 8.**
O enunciado exige início e fim claros. Avalia se o caso permite definir um processo com limites nítidos e de tamanho gerenciável.

**C5. Base para medição — peso 15.**
O enunciado exige objetivo quantificado e resultados esperados em métricas. Avalia se existem números de referência (linha de base, metas oficiais, custos publicados) que ancorem as estimativas do grupo.

**C6. Viabilidade de gerar dados próprios sem acesso à empresa — peso 10.**
Avalia o quanto o grupo consegue, por conta própria e de forma ética, produzir evidência original (amostra de reclamações, registros como cliente).

**C7. Robustez da hipótese central — peso 10.**
Avalia o quanto a tese que sustenta o caso é apoiada por fonte, ou se depende de suposição que pode ser contestada.

**C8. Potencial para análise do Lean e melhorias não triviais — peso 10.**
Avalia se há desperdícios identificáveis em etapas distintas, e se o caso deixa espaço para melhorias que a própria empresa ainda não implementou.

**C9. Confiabilidade das fontes — peso 10.**
Avalia a proporção de fontes primárias (da própria empresa) e verificadas, em relação a fontes secundárias, resumos de busca ou itens não verificados. A idade do dado não é julgada aqui, para não penalizar duas vezes; ela é tratada nos critérios C2, C3, C5 e C7.

## 4. Escala de pontuação (0 a 5 em cada critério)

- **5:** plenamente sustentado por fonte primária verificada; lacunas irrelevantes.
- **4:** sustentado, com lacunas pequenas ou com parte em fonte secundária confiável.
- **3:** sustentado em parte; o grupo precisa complementar com estimativa ou dado próprio.
- **2:** fraco; depende majoritariamente de suposição.
- **1:** muito fraco; só indícios.
- **0:** inexistente ou inviável.

**Pontuação ponderada:** nota do critério (0 a 5) multiplicada pelo peso e dividida por 5, somando-se os nove critérios. O total vai de 0 a 100.

## 5. Regras para evitar viés

- Pontuar só o que consta nos documentos e foi verificado. Item não verificado não conta como sustentado.
- Mesma régua para os dois casos: o mesmo tipo de evidência recebe a mesma nota nos dois.
- Não premiar a extensão do documento nem a quantidade de fontes citadas, só a qualidade do que sustentam.
- Registrar a justificativa de cada nota com a evidência que a sustenta, para ser auditável.
- Fazer uma análise de sensibilidade: refazer o total com pesos iguais e com pesos alternativos, para ver se o resultado muda.
- Reconhecer vieses prováveis do avaliador: (a) o avaliador escreveu os dois documentos, o que pode favorecer o que recebeu mais rodadas de revisão; (b) o documento mais recente pode parecer mais completo; (c) a tendência de ser mais crítico com o caso que foi examinado primeiro; (d) a tendência de premiar o caso com mais números, mesmo sendo números de pouca relevância.

## 6. Verificações feitas antes de pontuar

A releitura mostrou pendências que mudariam as notas. Elas foram verificadas nas páginas originais.

**Nubank:**
- O artigo "Behind the scenes of Nubank's Customer Support", que sustenta o fluxo com o Proximo, os "75% de acerto", as "quase 200 filas" e os "60 mil jobs por dia", foi publicado em **13 de agosto de 2018**. Esses números têm oito anos.
- O artigo "Designing Shuffle" é de **30 de maio de 2023**.
- O Precog, ferramenta de IA para direcionar contatos citada em artigo de outubro de 2023, foi lançado em junho de 2023 e é para **atendimento por telefone**, não por chat. O artigo não traz métricas.
- A fonte dos "8,5 milhões de contatos por mês, 60% tratados primeiro por LLM" (modelo de IA que entende e gera texto) é uma palestra de **2025**, resumida por um site de terceiros (ZenML). O resumo diz que o chat é o canal principal.
- Conclusão: o fluxo descrito no documento do Nubank mistura três épocas (2018, 2023 e 2025) e apresenta tudo no presente. Em especial, a descrição da primeira etapa (o Proximo organizando o contato em fila) e a dor de "25% de erro de roteamento" vêm de 2018. Se hoje 60% dos contatos passam primeiro por LLM, essa etapa pode ter mudado de forma relevante, e a dor de 2018 pode não existir mais.

**Magalu:**
- A página do SLA oficial para vendedores mostra "Atualizado em 3 outubro 26", ou seja, 3 de outubro de 2026 (o ano aparece abreviado). A pendência "data do SLA não identificada" do documento do Magalu fica resolvida a favor do caso.
- O SLA exige emitir a nota fiscal até 2 dias úteis antes da expedição e atualizar o status de separação em até 1 dia útil, mas **não fixa um prazo de despacho**. A regra "aprovado até as 11h, despacho no mesmo dia" continua sem confirmação oficial.
- Os relatórios de resultados do 3T25 e do 2T26 foram lidos diretamente (texto extraído do PDF), e os dados de fulfillment (28% e 29% dos pedidos do marketplace) conferem.

## 7. Análise critério a critério

### C1. Aderência ao tema da disciplina (peso 10)

- **Nubank — nota 3.** É operação de serviços (fila, capacidade, atendimento). O enunciado aceita expressamente "Processo de Atendimento ao Cliente" como exemplo, e conceitos de operações como capacidade, filas e Lean se aplicam. Não há fluxo físico de mercadorias, e o nome da disciplina inclui cadeia de suprimentos. Nota 3 porque cumpre o enunciado, mas só em parte o nome da disciplina.
- **Magalu — nota 5.** Estoque, armazenagem, transporte, última milha, integração entre empresas e nível de serviço. É o núcleo do tema.
- **Incerteza:** Nubank 3 ou 4 (o enunciado cita atendimento como exemplo). Magalu 5.

### C2. Evidência concreta do problema (peso 12)

- **Nubank — nota 2.** O que está verificado: o aviso falso de 12/06 (várias notícias), a instabilidade do Pix em 26/06 e relatos de demora no chat. O que falta: nenhuma fonte liga esses incidentes à saturação do chat, e o próprio Nubank diz que não houve impacto operacional. A única dor admitida pela empresa (25% de erro de roteamento) é de 2018. As esperas de 30 minutos a horas são relatos de clientes. Os números de 08/07 vêm de resumo de busca (a página deu acesso negado). Ou seja: há gatilhos datados, mas não há evidência oficial e recente de ineficiência do processo.
- **Magalu — nota 3.** O que está verificado, em fonte oficial e recente: fulfillment em 28% (3T25) e 29% (2T26) dos pedidos do marketplace; a declaração da empresa de que prioriza "modalidades de entrega mais eficientes"; e as metas do SLA. Isso permite enquadrar um problema estrutural. O que falta: nenhuma medição de atraso ou de ineficiência; só relatos individuais (em página que mistura vendas próprias e de vendedores) e a visão de um integrador sobre problemas de vendedores com mais de um estoque. A afirmação de que ~71% dos pedidos estão fora do fulfillment é conta do grupo.
- **Por que Magalu ganha 1 ponto:** os dados oficiais são atuais e permitem enquadrar o problema; no Nubank, o dado oficial de dor é antigo e o vínculo com os incidentes é suposição. Nenhum dos dois mostra o problema medido, por isso nenhum passa de 3.
- **Incerteza:** Nubank 2 ou 3; Magalu 2 ou 3.

### C3. Documentação do processo atual (peso 15)

- **Nubank — nota 3.** Há descrição detalhada em fonte primária de etapas, papéis e ferramentas (Proximo, Xpeer e badges, Shuffle com Start e Autotake, Atenta, Ouvidoria), o que daria um bom mapa. Mas a descrição combina 2018 (Proximo), 2023 (Shuffle) e 2025 (LLM no primeiro contato, que o documento nem integra ao fluxo). A etapa de classificação e fila pode estar desatualizada. Falta o backoffice (equipe de retaguarda), o que o documento já reconhece. Granularidade alta, vigência incerta.
- **Magalu — nota 3.** O SLA e as páginas de serviço (atuais) dão as etapas do vendedor, os prazos de status e as modalidades de saída do produto. A rede logística interna (CDs, triagem, rotas) é uma caixa-preta. As modalidades aparecem contadas de formas diferentes (três ou cinco), e as contagens de CDs divergem (21 contra 270). Parte do fluxo vem de blogs de integradores e de um resumo de busca. Granularidade menor, vigência melhor.
- **Empate em 3:** o Nubank tem mais detalhe, mas com vigência duvidosa; o Magalu tem menos detalhe, mas mais atual. Os efeitos se compensam.
- **Incerteza:** Nubank 3 ou 4 (se o fluxo de 2018 ainda valer); Magalu 3.

### C4. Delimitação do processo (peso 8)

- **Nubank — nota 4.** Início (cliente escreve) e fim (resolução ou transferência) são claros, e o recorte é de tamanho gerenciável (o chat). Ponto fraco: a fronteira com o backoffice e o fato de o foco em picos exigir tratar eventos que o grupo não observa diretamente.
- **Magalu — nota 3.** Início (pedido confirmado, o que o grupo supõe equivaler ao pagamento aprovado) e fim (entrega) são claros, mas o processo cruza vendedor, rede do Magalu e transporte, tem várias modalidades, e o grupo precisa escolher uma sem poder observar qual modalidade cada pedido usa. O escopo é maior e mais heterogêneo.
- **Incerteza:** Nubank 3 ou 4; Magalu 3 ou 4.

### C5. Base para medição (peso 15)

- **Nubank — nota 2.** Não há linha de base (tempo de espera, tempo de atendimento, custo por contato). Os dados quantitativos públicos são os de 2018 (volumes, 75%) e, de 2025, o volume de 8,5 milhões de contatos por mês (resumo de palestra). Não há metas oficiais de nível de serviço.
- **Magalu — nota 3.** Também não há linha de base de desempenho, mas há metas oficiais e atuais (mais de 95% de entregas no prazo; reclamações abaixo de 5%; casos externos abaixo de 1%), tarifas publicadas do fulfillment (custo por venda e por coleta) e números de venda do marketplace. As metas do SLA não são desempenho medido, mas ancoram estimativas de objetivo.
- **Incerteza:** Nubank 1 ou 2; Magalu 2 ou 3.

### C6. Viabilidade de gerar dados próprios (peso 10)

- **Nubank — nota 3.** Amostra de reclamações recentes no Reclame Aqui (viável e ética) e registro de tempos de resposta no chat por quem for cliente (viável, mas só com necessidade real, e amostra pequena). Limitação central: o foco em picos de demanda é difícil de observar, porque os incidentes são imprevisíveis, e só se enxerga o passado pelos relatos.
- **Magalu — nota 3.** Amostra de reclamações no Reclame Aqui (viável, com a limitação de misturar vendas próprias e de vendedores) e registro de prazos de compras reais (viável, mas sem comprar só para medir, e sem saber a modalidade). O lado do vendedor não é observável pelo grupo.
- **Empate em 3:** as duas têm possibilidade equivalente, com limitações diferentes.
- **Incerteza:** Nubank 3; Magalu 3.

### C7. Robustez da hipótese central (peso 10)

- **Nubank — nota 2.** A tese é que, em picos, o erro de roteamento e o dimensionamento por fila ampliam a espera e as transferências. A premissa de roteamento é de 2018; o vínculo entre incidente e saturação do chat não tem fonte, e a empresa nega impacto operacional; e a evidência de 2025 (LLM no primeiro contato para 60% dos contatos) sugere que o processo mudou. A tese pode ser contestada por qualquer um que conheça o histórico.
- **Magalu — nota 3.** A pergunta do caso é aberta ("onde o pedido perde tempo"), e a premissa estrutural (parte grande dos pedidos ainda fora do fulfillment, e a empresa priorizando modalidades mais eficientes) é sustentada por dado oficial e atual. A hipótese causal (que o atraso se concentre no caminho com vendedor) não tem fonte, e o documento já a trata como hipótese. É menos contestável porque afirma menos.
- **Incerteza:** Nubank 1 a 3; Magalu 2 a 3.

### C8. Potencial para o Lean e melhorias não triviais (peso 10)

- **Nubank — nota 3.** Há desperdícios identificáveis (espera, transferência entre filas, classificação errada, retrabalho por recontato). O espaço de melhoria existe (por exemplo, tratamento de incidentes conhecidos e reforço dinâmico de equipe), mas o Nubank é sofisticado (Autotake, badges, LLM, Precog), então a chance de propor algo que já existe é alta.
- **Magalu — nota 4.** Os sete desperdícios clássicos do Lean (transporte, estoque, movimentação, espera, superprodução, excesso de processamento e defeitos) têm correspondência mais direta num fluxo físico, em etapas distintas (preparo do vendedor, coleta, passagem por CDs, entrega). O espaço de melhoria é amplo. Risco: propostas óbvias como "migrar para fulfillment".
- **Incerteza:** Nubank 3; Magalu 3 ou 4.

### C9. Confiabilidade das fontes (peso 10)

- **Nubank — nota 4.** Fontes primárias verificadas: dois artigos do blog de engenharia e a página oficial de contato. Há várias notícias independentes sobre o aviso falso. Fragilidades: os números de 08/07 vêm de resumo de busca; a data de 12/06 vem de uma só fonte; o resumo da palestra de 2025 é de terceiros. A idade dos dados não é julgada aqui.
- **Magalu — nota 4.** Fontes primárias verificadas: os dois relatórios de resultados (lidos diretamente), a página de fulfillment e o SLA. Fragilidades: o fluxo logístico vem em parte de blogs de integradores e de um resumo de busca; a regra de despacho não foi confirmada; há discrepância entre as contagens de CDs.
- **Empate em 4:** proporções parecidas de fontes primárias e secundárias.
- **Incerteza:** Nubank 3 ou 4; Magalu 3 ou 4.

## 8. Pontuação final

Contribuição de cada critério (nota multiplicada pelo peso e dividida por 5), com o máximo possível entre parênteses:

- **C1 (10):** Nubank 6,0 — Magalu 10,0
- **C2 (12):** Nubank 4,8 — Magalu 7,2
- **C3 (15):** Nubank 9,0 — Magalu 9,0
- **C4 (8):** Nubank 6,4 — Magalu 4,8
- **C5 (15):** Nubank 6,0 — Magalu 9,0
- **C6 (10):** Nubank 6,0 — Magalu 6,0
- **C7 (10):** Nubank 4,0 — Magalu 6,0
- **C8 (10):** Nubank 6,0 — Magalu 8,0
- **C9 (10):** Nubank 8,0 — Magalu 8,0

**Total (de 100): Nubank 56,2 — Magalu 68,0.** Diferença de 11,8 pontos a favor do Magalu.

De onde vem a diferença: C1 (+4,0), C5 (+3,0), C2 (+2,4), C7 (+2,0) e C8 (+2,0) favorecem o Magalu; C4 (+1,6) favorece o Nubank; C3, C6 e C9 empatam.

## 9. Análise de sensibilidade

- **Pesos iguais:** Nubank 57,8 — Magalu 68,9.
- **Peso maior em medição e evidência** (C5 em 25 e C2 em 20): Nubank 51,2 — Magalu 64,4.
- **Peso maior em viabilidade e processo** (C6 em 20, C3 em 20 e C4 em 15): Nubank 58,4 — Magalu 64,4.
- **Sem o critério de tema (C1 com peso 0):** Nubank 55,8% do máximo — Magalu 64,4% do máximo.
- **Nubank com 4 em C1:** Nubank 58,2 (Magalu continua com 68,0).
- **Contrafactual: o dado de 2018 ainda vale** (Nubank sobe para 3 em C2, 4 em C3, 3 em C5 e 3 em C7): Nubank 66,6 — Magalu 68,0. Quase empate.
- **Cenário adverso ao Magalu e favorável ao Nubank** (Nubank 4 em C1 e 3 em C2; Magalu 2 em C2, C5 e C7): empate em 60,6 a 60,6.
- **Simulação de incerteza** (cada nota varia 1 ponto para mais ou para menos, de forma independente; é um exercício ilustrativo, não estatística rigorosa): o Magalu fica à frente em cerca de 95% das simulações. Se houver 50% de chance de o dado de 2018 ainda valer, cai para cerca de 75%.

**Leitura:** o Magalu fica à frente em todas as variações de pesos, mas a vantagem depende em grande parte de um fato: a idade das fontes do Nubank. Se o processo descrito em 2018 ainda fosse atual, a diferença quase desapareceria, e o que restaria seria a vantagem do tema. A vantagem do Magalu, portanto, é real, mas menor e menos sólida do que a nota bruta sugere.

## 10. Conclusão

**O Magalu é o caso mais forte, com diferença moderada (cerca de 12 pontos em 100).** Os fatores:

1. **Tema:** o Magalu é um caso de cadeia de suprimentos, o que o Nubank não é.
2. **Dados atuais e oficiais:** metas do SLA (atualizado em 3 de outubro de 2026), relatórios de resultados de 2025 e 2026 e tarifas publicadas dão âncora para medição. No Nubank, os dados oficiais de processo e de dor são de 2018 e 2023.
3. **Hipótese menos frágil:** a pergunta do Magalu afirma menos e é mais difícil de contestar. A do Nubank depende de um vínculo sem fonte e de uma premissa de 2018.
4. **Espaço de análise Lean:** o fluxo físico oferece mais variedade de desperdícios.

A vantagem do Nubank está em ter um recorte de processo mais fácil de delimitar e mais detalhe sobre a ferramenta e as etapas do atendimento.

**Nada disso resolve o ponto fraco comum:** nenhum dos dois casos tem linha de base medida. Em qualquer um, objetivo mensurável e resultados esperados dependerão de estimativas declaradas ou de dado próprio.

## 11. Problemas encontrados nos dois documentos de caso

Estes problemas foram encontrados durante a comparação. Não corrigi os documentos de caso, porque a tarefa era só comparar.

**case_nubank_v5.md:**
- Apresenta o fluxo do Proximo, os "75%", as "quase 200 filas" e os "60 mil jobs por dia" no presente, sem informar que o artigo é de 2018. A seção de limites diz apenas que o 75% "pode estar defasado", o que subestima o problema: o dado tem oito anos.
- Chama os 25% de erro de roteamento de "dor admitida pela empresa" no presente. É dor admitida em 2018.
- Não integra ao fluxo o dado de 2025 de que 60% dos contatos passam primeiro por LLM, que muda a primeira etapa.
- Atribui o Precog ao tema de IA no atendimento sem esclarecer que ele é para telefone.

**case_magalu_v5.md:**
- Diz que a data do SLA não foi identificada. A página mostra "Atualizado em 3 outubro 26".
- A seção de comparação (seção 5 do documento) diz que o Nubank tem "o processo interno mais bem documentado". Isso vale só para o nível de detalhe, não para a atualidade, e deve ser qualificado. O placar 6/5/3 contra 7/5/2 também usa uma régua diferente da desta comparação.
- O SLA não fixa prazo de despacho, e o documento só diz que a regra de 11h não foi confirmada. Convém afirmar que o SLA consultado não traz prazo de despacho.

## 12. Limites desta comparação

- As notas são julgamentos do avaliador, sem fonte externa que as calibre. A faixa de incerteza de 1 ponto por critério é uma estimativa.
- O avaliador escreveu os dois documentos de caso. O Nubank foi examinado primeiro e recebeu mais rodadas de revisão; o Magalu foi examinado depois, e as fontes dele foram lidas com mais profundidade neste trabalho. Isso pode influenciar a percepção de maturidade.
- Os pesos refletem uma avaliação de importância para o enunciado e para um grupo sem acesso a empresas. Grupos com outras prioridades chegariam a outro resultado, ainda que a análise de sensibilidade indique que a ordem se mantém na maioria das variações.
- A comparação avalia os casos como estão documentados hoje. Se as pendências de verificação forem resolvidas (por exemplo, descobrir que o processo do Nubank ainda funciona como em 2018), as notas podem mudar.
- Parte do que sustenta as notas do Magalu vem de blogs de integradores e de um resumo de busca, como informado nas fontes do documento do caso.
