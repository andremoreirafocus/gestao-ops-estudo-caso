# Case proposto — Nubank: atendimento por chat em picos de demanda

Status: viável, com limitações declaradas. Substitui a avaliação anterior, que descartou o caso sem ter lido as fontes de engenharia. Base inicial: nubank.pdf (conversa com IA do Google, usada só como ponto de partida; suas afirmações genéricas não foram aproveitadas sem verificação).

## Pergunta do case

Como o processo de atendimento por chat do Nubank absorve picos de demanda gerados por incidentes (Pix fora do ar, comunicação errada)?

## Processo regular documentado (fontes de engenharia do Nubank)

1. O cliente descreve o problema por chat ou e-mail, sem URA nem menus.
2. O **Proximo** classifica o contato com modelos de IA e o coloca em uma de quase 200 filas. Os modelos acertam 75% das vezes.
3. O **Xpeer** (atendente) tem badges de habilidade; novatos atendem filas simples.
4. No **Shuffle**, o Xpeer clica em "Start" para receber o próximo job. O **Autotake** aloca chats automaticamente. Ele pode pular ou transferir o job.
5. O Xpeer classifica o problema e marca como resolvido.
6. O **Atenta** faz revisão de qualidade em amostras aleatórias.
7. O que não se resolve vai para a Ouvidoria (dias úteis, 8h–18h).

**Números públicos:** cerca de 60 mil jobs/dia; 200 filas; 8,5 milhões de contatos/mês; 60% tratados primeiro por LLM (palestra resumida no ZenML); FRT (tempo da primeira resposta) acompanhado por fila.

**Pontos de dor admitidos pelo próprio Nubank:**
- 25% de erro de roteamento, com transferência manual que prejudica a eficiência.
- Dimensionamento de Xpeers por fila recalculado por dia, semana e sazonalidade.
- Qualidade auditada só em amostra.

## Gatilhos de pico (2026)

| Data | Evento | Fonte |
|---|---|---|
| 12/06 | Aviso falso de liquidação extrajudicial a cerca de 20 mil clientes, por erro de desenvolvedor. O Banco Central desmentiu. | [Midiamax](https://midiamax.com.br/brasil/2026/nubank-diz-erro-operacional-causou-envio-indevido-mensagens-fechamento-banco/), [CNN Brasil](https://www.cnnbrasil.com.br/economia/macroeconomia/nubank-atribui-alerta-falso-a-erro-tecnico-de-desenvolvedor/) |
| 26/06 | Instabilidade no Pix à noite. | [Alô Alô Bahia](https://aloalobahia.com/noticias/2026/06/26/clientes-do-nubank-relatam-instabilidade-e-dificuldade-para-enviar-e-receber-pix-nesta-sexta-26/) |
| 08/07 | Nova instabilidade: 81% das reclamações no Pix, 13% em login, 3% em saldo. | [Leiaja](https://www.leiaja.com/tecnologia/2026/07/08/nubank-apresenta-instabilidade-e-gera-reclamacoes-de-clientes/) |
| 2026 | Relatos recorrentes de demora no chat (30 min a horas). | [Reclame Aqui](https://www.reclameaqui.com.br/nubank/tempo-de-espera-para-uma-resposta-no-chat-chega-a-30min_uVIPJ2mKYDm2eBfH/), [Seu Crédito Digital](https://seucreditodigital.com.br/clientes-reclamam-da-qualidade-no-atendimento-nubank/) |

O episódio mais recente encontrado é de 08/07/2026. O incidente da liquidação tem cerca de quatro meses.

## Hipótese de trabalho (declarar como hipótese)

Em picos, o erro de roteamento (25%) e o dimensionamento por fila ampliam a espera e as transferências.

## Recorte para o enunciado

- **Processo:** atendimento de um contato por chat, do contato do cliente até a resolução ou escalonamento.
- **Raias:** cliente, Proximo, Xpeer, backoffice/especialista, Ouvidoria.
- **Desperdícios Lean:** transporte (transferências entre filas), espera (FRT), defeitos (classificação errada), retrabalho (cliente volta cobrando).
- **Melhorias candidatas:** fila ou classificador dedicado a incidentes conhecidos com resposta proativa no app; reforço dinâmico de Xpeers entre filas; canal de escape quando o chat satura.
- **Resultados esperados:** estimativas declaradas (redução de transferências, de FRT e de recontato).

## O que NÃO usar do nubank.pdf

Estes pontos vêm do trecho genérico do Google, não do Nubank, e não foram sustentados pelas fontes:
- "Looping de bot" e "falta de histórico para o atendente" (o Shuffle mostra histórico de transferências e contexto do cliente).
- "Prazo de 3 a 5 dias no backoffice".
- "8 em 10 reclamações sem solução", "90% de emoções negativas" e "turnover de 45%" (setor, sem fonte).

## Limites e pendências

- Não está provado que os incidentes saturaram o chat ou a telefonia. O Nubank diz que não houve impacto operacional; a única evidência são relatos de clientes.
- Não há tempos oficiais por etapa (FRT, TMA, taxa de transferência). Métricas do estado futuro serão estimativas.
- O 75% de acerto do roteamento é de IA, não de resolução, e pode estar defasado. **Verificar a data dos artigos de engenharia.**
- A página do Leiaja (08/07) não abriu (403); os números vêm do resumo da busca. Confirmar na fonte.
- O PDF cita ainda o blog do Nubank sobre uso de IA no atendimento e a resposta oficial no Reclame Aqui sobre o WhatsApp; ambos não foram lidos integralmente.

## Fontes

- [Behind the scenes of Nubank's Customer Support](https://building.nu.com/behind-the-scenes-of-nubanks-customer-support/)
- [Designing Shuffle](https://building.nu.com/designing-shuffle-the-internal-tool-that-powers-nubanks-award-winning-customer-service/)
- [ZenML – agentes de IA no Nubank](https://www.zenml.io/llmops-database/building-an-ai-private-banker-with-agentic-systems-for-customer-service-and-financial-operations)
- [Página de contato do Nubank](https://nubank.com.br/ajuda-e-seguranca/contato)
- [Reclame Aqui – WhatsApp](https://www.reclameaqui.com.br/nubank/dificuldade-de-contato-com-nubank-via-telefone-e-whatsapp_3iF-av7nUJNUgCLx/)
- Notícias dos incidentes: ver tabela acima.
