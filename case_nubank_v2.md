# Adequação do case Nubank ao enunciado — versão 2

Este documento avalia se o case Nubank (atendimento por chat em picos de demanda) é adequado ao trabalho de Gestão de Operações e Cadeias Globais de Suprimentos e orienta como abordá-lo. Não contém conteúdo do trabalho em si.

## 1. O caso e a pergunta que ele permite responder

**Empresa:** Nubank. **Processo candidato:** atendimento de um contato por chat, do contato do cliente até a resolução ou escalonamento.

**Pergunta:** como esse processo absorve picos de demanda gerados por incidentes (Pix fora do ar, comunicação errada)?

**Gatilhos recentes e datados (2026):**

| Data | Evento | Fonte |
|---|---|---|
| 12/06 | Aviso falso de liquidação extrajudicial a cerca de 20 mil clientes, por erro de desenvolvedor; o Banco Central desmentiu | [Midiamax](https://midiamax.com.br/brasil/2026/nubank-diz-erro-operacional-causou-envio-indevido-mensagens-fechamento-banco/), [CNN Brasil](https://www.cnnbrasil.com.br/economia/macroeconomia/nubank-atribui-alerta-falso-a-erro-tecnico-de-desenvolvedor/) |
| 26/06 | Instabilidade no Pix à noite | [Alô Alô Bahia](https://aloalobahia.com/noticias/2026/06/26/clientes-do-nubank-relatam-instabilidade-e-dificuldade-para-enviar-e-receber-pix-nesta-sexta-26/) |
| 08/07 | Nova instabilidade: 81% das reclamações no Pix, 13% em login, 3% em saldo | [Leiaja](https://www.leiaja.com/tecnologia/2026/07/08/nubank-apresenta-instabilidade-e-gera-reclamacoes-de-clientes/) (página deu 403; números vêm do resumo da busca) |

O episódio mais recente encontrado é de 08/07/2026; o incidente da liquidação tem cerca de quatro meses.

## 2. O que as fontes públicas oferecem

**Processo regular (engenharia do Nubank):** o cliente descreve o problema sem URA nem menus; o Proximo classifica o contato com IA em uma de quase 200 filas; Xpeers com badges de habilidade recebem jobs no Shuffle (Start, Autotake, pular ou transferir); o Atenta audita amostras de qualidade; casos não resolvidos vão para a Ouvidoria (dias úteis, 8h–18h).
Fontes: [Behind the scenes](https://building.nu.com/behind-the-scenes-of-nubanks-customer-support/), [Designing Shuffle](https://building.nu.com/designing-shuffle-the-internal-tool-that-powers-nubanks-award-winning-customer-service/), [página de contato](https://nubank.com.br/ajuda-e-seguranca/contato).

**Números públicos:** cerca de 60 mil jobs/dia; 200 filas; 75% de acerto do roteamento por IA; 8,5 milhões de contatos/mês e 60% tratados primeiro por LLM ([ZenML](https://www.zenml.io/llmops-database/building-an-ai-private-banker-with-agentic-systems-for-customer-service-and-financial-operations), resumo de palestra); FRT acompanhado por fila (sem valor divulgado).

**Dores admitidas pela empresa:** 25% de erro de roteamento com transferência manual; dimensionamento de Xpeers por fila (dia, semana, sazonalidade); qualidade auditada só em amostra.

**Evidência de clientes (não é métrica oficial):** relatos recorrentes de demora no chat, de 30 min a horas ([Reclame Aqui](https://www.reclameaqui.com.br/nubank/tempo-de-espera-para-uma-resposta-no-chat-chega-a-30min_uVIPJ2mKYDm2eBfH/), [Seu Crédito Digital](https://seucreditodigital.com.br/clientes-reclamam-da-qualidade-no-atendimento-nubank/)).

## 3. Avaliação de adequação por exigência do enunciado

Legenda: **Adequada** = fontes públicas sustentam; **Parcial** = sustentada em parte, o grupo complementa; **Fraca** = depende de suposição ou dado próprio.

| Exigência do enunciado | Nível | O que as fontes sustentam | O que o grupo precisa produzir | Risco |
|---|---|---|---|---|
| Problema/contexto com dados e exemplos concretos | Parcial | Incidentes datados, 75% de acerto, 200 filas, relatos de espera | Quantificar a dor com dado próprio; as esperas são relatos, não métrica oficial | Tratar relato de cliente como medida |
| Objetivo principal mensurável (X%, Y%, impacto na rentabilidade) | Fraca | Nenhum valor base de FRT, TMA ou custo por contato | Definir a linha de base e justificar X e Y como estimativas | Metas sem base |
| Objetivos secundários | Adequada | Contexto de qualidade (Atenta), satisfação e padronização entre filas | Escolher os relevantes | Baixo |
| Processo identificado, com início e fim | Adequada | Fluxo contato → fila → Xpeer → resolução/escalonamento está documentado | Delimitar o escopo (o que fica de fora) | Escopo largo demais: chat, telefone e Ouvidoria juntos |
| Mapa do estado atual (entradas, atividades, saídas, raias) | Parcial | Proximo, Xpeer/Shuffle, Atenta e Ouvidoria | Completar o backoffice/especialista e as saídas, que os artigos não detalham | Preencher lacunas com suposição sem declarar |
| Pontos de dor | Parcial | 25% de erro de roteamento e dimensionamento (admitidos); espera (relatos) | Evidência própria sobre o que mais pesa e relação com os picos | Dor "bem definida" pela empresa cobre só parte do problema |
| Gargalos | Fraca | Nenhum dado de fila por etapa | Identificar onde o fluxo trava, por inferência apoiada em evidência | Afirmar gargalo sem prova |
| Desperdícios do Lean | Parcial | Transferência (transporte), espera (FRT), classificação errada (defeitos) | Classificar e justificar cada desperdício | Rotular sem ligar ao fluxo |
| Melhorias específicas e justificativas | Adequada | Pontos de dor admitidos oferecem ligação direta | Propor e justificar cada melhoria contra um ponto de dor | Propor algo que o Nubank já faz (por ex. Autotake, rotas por badge) |
| Mapa do estado futuro com destaques | Adequada | Depende só do mapa atual | Desenhar e marcar alterações | Baixo |
| Resultados esperados em métricas | Fraca | Sem base numérica | Estimativas declaradas, com premissas | Números sem lastro |
| Benefícios da Gestão de Operações | Adequada | Teoria de filas, capacidade, Lean, qualidade | Relacionar com o conteúdo de aula | Baixo |
| Plano de ação | Adequada | Independe de dado | Detalhar etapas | Baixo |
| Desafios e riscos | Adequada | Mudança de modelo, custo de tecnologia e risco de piorar a experiência | Reconhecer e avaliar | Baixo |

## 4. Veredito

**O caso é adequado**, com duas condições:

1. **Delimitar o processo ao chat** (ou ao trecho "classificação → fila → resolução ou transferência"), deixando de fora a telefonia e a Ouvidoria, ou tratando-as como saída do processo. Isso mantém início e fim claros.
2. **Tratar a medição como ponto fraco assumido.** Exigências com nível "Fraca" (objetivo mensurável, gargalos, resultados esperados) só se sustentam com dado próprio ou com estimativas declaradas.

Sem dados internos, a adequação depende de o grupo conseguir gerar evidência original.

## 5. Orientação de abordagem

- **Separar três tipos de afirmação ao longo do trabalho:** fato documentado (com fonte), inferência do grupo (com a lógica) e estimativa (com a premissa).
- **Tratar o vínculo entre incidente e saturação como hipótese.** Nenhuma fonte encontrada prova que os incidentes de 2026 saturaram o chat, e o Nubank afirma que não houve impacto operacional.
- **Gerar dado próprio onde as fontes são fracas:**
  - amostra de reclamações recentes no Reclame Aqui (por exemplo 50 a 100), classificadas por tipo de dor (espera, transferência, resposta repetida, recontato);
  - registro de tempos de resposta no chat por quem for cliente, com data e hora anotadas. A amostra será pequena, mas é dado original.
- **Não usar do nubank.pdf** as afirmações genéricas não sustentadas: "looping do bot", "falta de histórico", "prazo de 3 a 5 dias no backoffice" e os percentuais de setor sem fonte.

## 6. Limites e pendências de verificação

- Data dos artigos de engenharia não verificada; o 75% de acerto pode estar defasado.
- Página do Leiaja (08/07) não abriu; os números vêm de resumo de busca.
- O 75% mede roteamento por IA, não resolução do problema.
- Os 60% de contatos tratados por LLM vêm do resumo de uma palestra; a data não foi verificada.
- O blog do Nubank sobre IA no atendimento citado no PDF não foi lido na íntegra.
- Não há tempos oficiais por etapa (FRT, TMA, taxa de transferência).

## 7. Fontes

- [Behind the scenes of Nubank's Customer Support](https://building.nu.com/behind-the-scenes-of-nubanks-customer-support/)
- [Designing Shuffle](https://building.nu.com/designing-shuffle-the-internal-tool-that-powers-nubanks-award-winning-customer-service/)
- [ZenML – agentes de IA no Nubank](https://www.zenml.io/llmops-database/building-an-ai-private-banker-with-agentic-systems-for-customer-service-and-financial-operations)
- [Página de contato do Nubank](https://nubank.com.br/ajuda-e-seguranca/contato)
- [Midiamax](https://midiamax.com.br/brasil/2026/nubank-diz-erro-operacional-causou-envio-indevido-mensagens-fechamento-banco/), [CNN Brasil](https://www.cnnbrasil.com.br/economia/macroeconomia/nubank-atribui-alerta-falso-a-erro-tecnico-de-desenvolvedor/)
- [Alô Alô Bahia](https://aloalobahia.com/noticias/2026/06/26/clientes-do-nubank-relatam-instabilidade-e-dificuldade-para-enviar-e-receber-pix-nesta-sexta-26/), [Leiaja](https://www.leiaja.com/tecnologia/2026/07/08/nubank-apresenta-instabilidade-e-gera-reclamacoes-de-clientes/)
- [Reclame Aqui – espera no chat](https://www.reclameaqui.com.br/nubank/tempo-de-espera-para-uma-resposta-no-chat-chega-a-30min_uVIPJ2mKYDm2eBfH/), [Seu Crédito Digital](https://seucreditodigital.com.br/clientes-reclamam-da-qualidade-no-atendimento-nubank/)
