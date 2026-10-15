# Adequação do case Nubank ao enunciado — versão 5

Este documento avalia se o case Nubank (atendimento por chat em picos de demanda) é adequado ao trabalho de Gestão de Operações e Cadeias Globais de Suprimentos e orienta como abordá-lo. Não contém conteúdo do trabalho em si.

## 1. O caso e a pergunta que ele permite responder

**Empresa:** Nubank. **Processo candidato:** atendimento de um contato por chat, do contato do cliente até a resolução ou escalonamento (encaminhamento do caso a um nível superior ou a outra equipe).

**Pergunta:** como esse processo absorve picos de demanda gerados por incidentes (Pix, o sistema brasileiro de pagamentos instantâneos, fora do ar; comunicação errada)?

**Gatilhos recentes e datados (2026):**

- **12/06** — Aviso falso de liquidação extrajudicial (decretada pelo Banco Central quando encerra as atividades de uma instituição financeira em dificuldade) a cerca de 20 mil clientes, por erro de desenvolvedor; o Banco Central desmentiu.
  Fontes: [Midiamax](https://midiamax.com.br/brasil/2026/nubank-diz-erro-operacional-causou-envio-indevido-mensagens-fechamento-banco/), [CNN Brasil](https://www.cnnbrasil.com.br/economia/macroeconomia/nubank-atribui-alerta-falso-a-erro-tecnico-de-desenvolvedor/)
- **26/06** — Instabilidade no Pix à noite.
  Fonte: [Alô Alô Bahia](https://aloalobahia.com/noticias/2026/06/26/clientes-do-nubank-relatam-instabilidade-e-dificuldade-para-enviar-e-receber-pix-nesta-sexta-26/)
- **08/07** — Nova instabilidade: 81% das reclamações no Pix, 13% em login, 3% em saldo.
  Fonte: [Leiaja](https://www.leiaja.com/tecnologia/2026/07/08/nubank-apresenta-instabilidade-e-gera-reclamacoes-de-clientes/) (página deu 403; números vêm do resumo da busca)

O episódio mais recente encontrado é de 08/07/2026; o incidente da liquidação tem cerca de quatro meses.

## 2. Aderência ao tema da disciplina

O enunciado cita expressamente como exemplo de processo o "Processo de Atendimento ao Cliente", que começa com a ligação do cliente e termina com a resolução do problema. O caso se encaixa nesse formato. Trata-se de operação de serviços, não de cadeia física de suprimentos; na defesa, convém explicitar a relação com os conceitos da disciplina: capacidade, filas, flexibilidade, qualidade e desperdícios do Lean (método de gestão que busca eliminar tudo que não agrega valor ao cliente, como espera, retrabalho e movimentação desnecessária).

## 3. O que as fontes públicas oferecem

**Processo regular (engenharia do Nubank), explicado passo a passo:**

O Nubank publicou, no seu blog de engenharia, como funciona o atendimento por dentro. Em linguagem simples, o caminho de um contato é este:

1. **O cliente escreve o problema.** Ele usa o chat do aplicativo ou o e-mail e conta com as próprias palavras o que aconteceu. Não passa por URA (aquele menu automático do tipo "digite 1 para cartão, digite 2 para fatura") nem por menus de opções.

2. **O Proximo organiza o contato em uma fila.** O Proximo é um sistema interno do Nubank. Ele lê a mensagem do cliente, usa inteligência artificial para entender o assunto (por exemplo cartão perdido, cobrança que o cliente não reconhece, problema com transação) e coloca o contato na fila daquele assunto. Há quase 200 filas, uma por tipo de problema. Segundo o próprio Nubank, a IA acerta a fila em 75% das vezes. Nos outros 25%, o contato vai para a fila errada e precisa ser transferido.

3. **Um atendente com a habilidade certa recebe o contato.** O Nubank chama seus atendentes de **Xpeers**. Cada Xpeer tem **badges**, que são selos digitais de habilidade (por exemplo contestação de compra ou reemissão de cartão). Quem tem mais experiência acumula vários badges e atende várias filas; quem está começando atende só os assuntos mais simples. Assim, cada fila é atendida por quem sabe resolver aquele tipo de problema.

4. **O atendente trabalha dentro do Shuffle.** O Shuffle é a ferramenta interna onde o Xpeer vê tudo sobre o cliente em uma única tela. Cada contato que o atendente recebe é chamado de **job** (uma unidade de trabalho). Na prática:
   - **Start:** o atendente clica nesse botão para receber o próximo job da fila compatível com seus badges.
   - **Autotake:** é um modo automático. O atendente define quantos chats quer atender ao mesmo tempo e o sistema passa a distribuí-los sozinho.
   - **Pular ou transferir:** se o atendente estiver sobrecarregado, ou se o assunto for de outra equipe, ele pode devolver o job ou enviá-lo para outro time.

5. **O atendente classifica e encerra.** Ele registra qual era o problema e marca o contato como resolvido, ou o transfere se não for possível resolver.

6. **A qualidade é conferida por amostragem.** O **Atenta** é o processo de controle de qualidade. Alguns Xpeers selecionados revisam conversas antigas escolhidas ao acaso e avaliam se o procedimento foi seguido e se o tom de voz foi adequado. O cliente também pode dar uma avaliação depois do atendimento. Como só uma amostra é revisada, não são todos os atendimentos que passam por essa conferência.

7. **O que não se resolve vai para a Ouvidoria.** A Ouvidoria é o canal de última instância, para casos que o atendimento normal não resolveu. Ela funciona só em dias úteis, das 8h às 18h (horário de Brasília), o que contrasta com o chat, que funciona 24 horas por dia.

**O que as fontes não dizem:** os artigos não explicam o que acontece depois que o atendente transfere um caso para outra equipe (por exemplo uma análise de fraude). Essa parte do processo é uma lacuna que o grupo terá de tratar como suposição declarada.

Fontes: [Behind the scenes](https://building.nu.com/behind-the-scenes-of-nubanks-customer-support/), [Designing Shuffle](https://building.nu.com/designing-shuffle-the-internal-tool-that-powers-nubanks-award-winning-customer-service/), [página de contato](https://nubank.com.br/ajuda-e-seguranca/contato).

**Números públicos:** cerca de 60 mil jobs/dia; 200 filas; 75% de acerto do roteamento (direcionamento de cada contato à fila certa) por IA; 8,5 milhões de contatos/mês e 60% tratados primeiro por LLM (modelo de IA que entende e gera texto, a tecnologia dos chatbots atuais) ([ZenML](https://www.zenml.io/llmops-database/building-an-ai-private-banker-with-agentic-systems-for-customer-service-and-financial-operations), resumo de palestra); FRT (First Response Time, tempo até a primeira resposta ao cliente) acompanhado por fila (sem valor divulgado).

**Dores admitidas pela empresa:** 25% de erro de roteamento com transferência manual; dimensionamento de Xpeers (cálculo de quantos atendentes cada fila precisa) por fila, por dia, semana e sazonalidade (variação previsível da demanda em certas épocas); qualidade auditada só em amostra.

**Evidência de clientes (não é métrica oficial):** relatos recorrentes de demora no chat, de 30 min a horas, registrados no Reclame Aqui (site onde consumidores publicam queixas contra empresas) e na comunidade de clientes do Nubank (NuCommunity) ([Reclame Aqui](https://www.reclameaqui.com.br/nubank/tempo-de-espera-para-uma-resposta-no-chat-chega-a-30min_uVIPJ2mKYDm2eBfH/), [Seu Crédito Digital](https://seucreditodigital.com.br/clientes-reclamam-da-qualidade-no-atendimento-nubank/)).

## 4. Avaliação de adequação por exigência do enunciado

Legenda: **Adequada** = fontes públicas sustentam; **Parcial** = sustentada em parte, o grupo complementa; **Fraca** = depende de suposição ou dado próprio.

**1. Problema/contexto com dados e exemplos concretos — PARCIAL**
- Fontes sustentam: incidentes datados, 75% de acerto, 200 filas, relatos de espera.
- Grupo produz: quantificação da dor com dado próprio; as esperas são relatos, não métrica oficial.
- Risco: tratar relato de cliente como medida.

**2. Objetivo principal mensurável (X%, Y%, impacto na rentabilidade) — FRACA**
- Fontes sustentam: nenhum valor base de FRT, TMA (Tempo Médio de Atendimento, duração média de cada atendimento) ou custo por contato.
- Grupo produz: linha de base (situação atual medida, usada como ponto de comparação) e justificativa de X e Y como estimativas.
- Risco: metas sem base.

**3. Objetivos secundários — PARCIAL**
- Fontes sustentam: menção a CSAT (nota de satisfação que o cliente dá após o atendimento) e auditoria de qualidade (Atenta) nas fontes de engenharia.
- Grupo produz: escolha e justificativa dos relevantes.
- Risco: baixo.

**4. Processo identificado, com início e fim — ADEQUADA**
- Fontes sustentam: fluxo contato → fila → Xpeer → resolução/escalonamento documentado; o enunciado cita atendimento ao cliente como exemplo.
- Grupo produz: delimitação do escopo e do que fica de fora.
- Risco: escopo largo demais (chat, telefone e Ouvidoria juntos).

**5. Mapa do estado atual (entradas, atividades, saídas e raias, isto é, faixas do mapa que mostram quem executa cada etapa) — PARCIAL**
- Fontes sustentam: Proximo, Xpeer/Shuffle, Atenta e Ouvidoria.
- Grupo produz: backoffice/especialista (equipe de retaguarda que analisa casos complexos, sem contato direto com o cliente) e saídas, que os artigos não detalham.
- Risco: preencher lacunas com suposição sem declarar.

**6. Pontos de dor — PARCIAL**
- Fontes sustentam: 25% de erro de roteamento e dimensionamento (admitidos); espera (relatos).
- Grupo produz: evidência própria sobre o que mais pesa e relação com os picos.
- Risco: a empresa admite parte do problema, mas não o impacto.

**7. Gargalos — FRACA**
- Fontes sustentam: nenhum dado de fila por etapa.
- Grupo produz: identificação de onde o fluxo trava, por inferência apoiada em evidência.
- Risco: afirmar gargalo sem prova.

**8. Desperdícios do Lean — PARCIAL**
- Fontes sustentam: transferência (transporte: o trabalho muda de mãos sem agregar valor), espera (FRT), classificação errada (defeitos: erro que obriga a refazer).
- Grupo produz: classificação e justificativa de cada desperdício.
- Risco: rotular sem ligar ao fluxo.

**9. Melhorias específicas e justificativas — ADEQUADA**
- Fontes sustentam: os pontos de dor admitidos oferecem ligação direta.
- Grupo produz: propostas, cada uma justificada contra um ponto de dor.
- Risco: propor algo que o Nubank já faz (por exemplo Autotake e roteamento por badge).

**10. Mapa do estado futuro com destaques — ADEQUADA**
- Fontes sustentam: depende só do mapa atual.
- Grupo produz: desenho e marcação das alterações.
- Risco: baixo.

**11. Resultados esperados em métricas — FRACA**
- Fontes sustentam: sem base numérica.
- Grupo produz: estimativas declaradas, com premissas.
- Risco: números sem lastro.

**12. Benefícios da Gestão de Operações — ADEQUADA**
- Fontes sustentam: teoria de filas, capacidade, Lean, qualidade.
- Grupo produz: relação com o conteúdo de aula.
- Risco: baixo.

**13. Plano de ação — ADEQUADA**
- Fontes sustentam: independe de dado.
- Grupo produz: detalhamento das etapas.
- Risco: baixo.

**14. Desafios e riscos — ADEQUADA**
- Fontes sustentam: mudança de modelo, custo de tecnologia e risco de piorar a experiência.
- Grupo produz: reconhecimento e avaliação.
- Risco: baixo.

**Resumo dos níveis (14 exigências):** 6 Adequadas, 5 Parciais, 3 Fracas. As três Fracas (objetivo mensurável, gargalos, resultados esperados) são todas de medição.

## 5. Veredito

**O caso é adequado, com ressalva forte na medição.** Estrutura, processo, melhorias, plano e riscos estão bem sustentados. As exigências quantitativas dependem de estimativas ou de dado próprio. Três condições:

1. **Delimitar o processo ao chat**, ou ao trecho "classificação → fila → resolução ou transferência", deixando telefonia e Ouvidoria fora ou como saídas do processo.
2. **Tratar a medição como ponto fraco assumido.** Gargalos, objetivo mensurável e resultados esperados só se sustentam com dado próprio ou estimativas declaradas.
3. **Tratar o vínculo entre incidente e saturação (chat com mais demanda do que consegue atender) como hipótese.** Nenhuma fonte encontrada prova que os incidentes de 2026 saturaram o chat, e o Nubank afirma que não houve impacto operacional.

## 6. Orientação de abordagem

- **Separar três tipos de afirmação ao longo do trabalho:** fato documentado (com fonte), inferência do grupo (com a lógica) e estimativa (com a premissa).
- **Gerar dado próprio onde as fontes são fracas:**
  - **Amostra de reclamações** recentes no Reclame Aqui (por exemplo 50 a 100), classificadas por tipo de dor (espera, transferência, resposta repetida, recontato, isto é, cliente que volta a pedir atendimento pelo mesmo problema). Limitação a declarar: quem reclama se autosseleciona (só aparece quem decidiu reclamar), então a amostra não representa todos os clientes.
  - **Registro de tempos de resposta no chat** por quem for cliente, com data e hora anotadas, a partir de uma necessidade real de suporte. Não abrir chamados artificiais para não sobrecarregar o atendimento. A amostra será pequena e deve ser apresentada como ilustrativa.
- **Não usar do nubank.pdf** as afirmações genéricas não sustentadas: "looping do bot" (robô de atendimento que repete as mesmas opções sem resolver), "falta de histórico", "prazo de 3 a 5 dias no backoffice" e os percentuais de setor sem fonte.

## 7. Limites e pendências de verificação

- Data dos artigos de engenharia não verificada; o 75% de acerto pode estar defasado.
- Página do Leiaja (08/07) não abriu; os números vêm de resumo de busca.
- O 75% mede roteamento por IA, não resolução do problema.
- Os 60% de contatos tratados por LLM vêm do resumo de uma palestra; a data não foi verificada.
- O blog do Nubank sobre IA no atendimento citado no PDF não foi lido na íntegra.
- Não há tempos oficiais por etapa (FRT, TMA, taxa de transferência).
- A data de 12/06 do aviso falso vem de uma fonte (Midiamax); outras notícias são de meados de junho.

## 8. Fontes

- [Behind the scenes of Nubank's Customer Support](https://building.nu.com/behind-the-scenes-of-nubanks-customer-support/)
- [Designing Shuffle](https://building.nu.com/designing-shuffle-the-internal-tool-that-powers-nubanks-award-winning-customer-service/)
- [ZenML – agentes de IA no Nubank](https://www.zenml.io/llmops-database/building-an-ai-private-banker-with-agentic-systems-for-customer-service-and-financial-operations)
- [Página de contato do Nubank](https://nubank.com.br/ajuda-e-seguranca/contato)
- [Midiamax](https://midiamax.com.br/brasil/2026/nubank-diz-erro-operacional-causou-envio-indevido-mensagens-fechamento-banco/), [CNN Brasil](https://www.cnnbrasil.com.br/economia/macroeconomia/nubank-atribui-alerta-falso-a-erro-tecnico-de-desenvolvedor/)
- [Alô Alô Bahia](https://aloalobahia.com/noticias/2026/06/26/clientes-do-nubank-relatam-instabilidade-e-dificuldade-para-enviar-e-receber-pix-nesta-sexta-26/), [Leiaja](https://www.leiaja.com/tecnologia/2026/07/08/nubank-apresenta-instabilidade-e-gera-reclamacoes-de-clientes/)
- [Reclame Aqui – espera no chat](https://www.reclameaqui.com.br/nubank/tempo-de-espera-para-uma-resposta-no-chat-chega-a-30min_uVIPJ2mKYDm2eBfH/), [Seu Crédito Digital](https://seucreditodigital.com.br/clientes-reclamam-da-qualidade-no-atendimento-nubank/)
