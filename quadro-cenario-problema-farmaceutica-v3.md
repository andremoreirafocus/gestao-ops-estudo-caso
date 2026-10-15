# Quadro — cenário e problema: indústria farmacêutica (v2)

Esta versão consolida o conteúdo de `quadro-cenario-problema-farmaceutica.md` com as respostas registradas em `as-is-v3-lacunas.md`.

## Periodicidade e sistemas

- As etapas 1 e 2 ocorrem mensalmente.
- O sistema correto é o **AERA** (e não AURA).
- Cada gerente de Marketing de cada equipe/setor insere sua previsão de demanda no AERA.
- O AERA consolida as previsões. Supply Chain realiza um *sanity check* da base geral e analisa o que consegue e faz sentido entregar em função do histórico de demanda e do compromisso financeiro.

## Plano financeiro

O plano financeiro é elaborado pela unidade de negócio em conjunto com a equipe financeira local. Ele é apresentado ao VP Financeiro e Comercial da América Latina, que dá feedback sobre o número. Em seguida, o Financeiro o ajusta junto com a unidade de negócio e o submete aos sistemas globais, no SAP Analytics Cloud Planning.

## Etapa 1 — projeção de vendas

O time de Marketing coleta a expectativa de vendas junto à equipe Comercial para fazer a projeção de vendas dos próximos 24 meses. Esta etapa ocorre mensalmente.

## Etapa 2 — consolidação e ajustes de Marketing

O time de Marketing consolida os dados colhidos junto à equipe Comercial e faz ajustes finos para informar a expectativa de vendas ao Supply Chain. Os ajustes são baseados em dados internos e no humor do mercado percebido pela equipe de Marketing.

Nesse momento, a equipe pode colocar gorduras ou eventualmente cortar volumes onde considera que a equipe Comercial foi demasiadamente otimista. Cada gerente de Marketing de cada equipe/setor insere sua previsão de demanda no AERA; o sistema consolida essas previsões. Esta etapa ocorre mensalmente.

Quando há conflito entre Marketing, plano financeiro, estoque e restrições, a informação disponível é que Marketing assume o risco de eventuais perdas.

## Etapa 3 — análise e alinhamento local

A equipe de Supply Chain Local consolida os dados informados pela equipe de Marketing e compara com o plano financeiro. Ela avalia, junto à equipe de Supply Chain Global, o estoque local, o estoque global e a capacidade de produção.

No AERA, Supply Chain realiza um *sanity check* da base geral e analisa o que consegue e faz sentido entregar em função do histórico de demanda e do compromisso financeiro.

Supply Chain Local informa a equipe de Marketing sobre as restrições/delays já conhecidos, alinha com Marketing e envia à equipe Global os volumes. A submissão ocorre mensalmente no AERA.

## Etapa 4 — planejamento e produção global

Recebido o planejamento de vendas, a equipe Global de Supply Chain inicia o trabalho junto às fábricas para garantir que a produção atenda aos forecasts de vendas.

As fábricas recebem o planejamento de demanda e visualizam no SAP os estoques do Brasil, da fábrica e em trânsito. Em geral, o prazo médio entre o recebimento do planejamento de demanda por Supply Chain e a disponibilidade das mercadorias para venda na sucursal do Brasil é de cinco meses.

Qualquer alteração na programação deve ser informada à equipe de Supply Chain Local, que alinha com a equipe de Marketing Local os impactos e os planos de mitigação.

## Etapa 5 — importação e disponibilização para venda

O produto é enviado por navio ou aéreo, dependendo da urgência, é desembaraçado, transportado para o operador logístico e fica disponível para venda.

Supply Chain Local define a estratégia logística e é responsável pelo desembaraço por meio de despachante contratado pela empresa no Brasil.

## Eventos extraordinários

Por vezes, a equipe de Marketing observa sinais de movimentos não usuais, como falta de produto da concorrência, surtos de doenças e licitações/bids solicitados. Nesses casos, Marketing comunica o Supply Chain Local, que junto ao Supply Chain Global busca alternativas para capturar oportunidades ou mitigar riscos.

Também pode haver identificação de um problema pelo Comercial Local, em função de estoque local alto ou demanda maior que a prevista, quando se busca não perder a oportunidade de aumentar a receita de vendas. Um exemplo de mitigação mencionado é enviar um lote a outro país quando um produto foi proibido por determinados motivos.

## Problemas

- Perda de receita por falta de produto para atender a demanda do mercado.
- Perda financeira por destruição de produto vencido antes de ser comercializado.

## O que fazer para reduzir as perdas

Automatizar as etapas 1 e 2 para elaborar as estimativas de demanda e evitar as distorções intencionais criadas pelo conflito de interesse entre Marketing, interessado em maximizar a oferta e consequentemente o volume de vendas, e Supply Chain, que deve atender a todos os países com base em vendas reais e minimização de perdas.

## Definição do TO-BE

Manter todo o fluxo como está com exceção das etapas a seguir:
- etapa 1: o AERA vai gerar uma proposta inicial de forecast baseado no planejamento financeiro para avaliação da equipe de marketing. O planejamento financeiro é construído com granularidade de sku.
- etapa 2: a equipe de marketing avalia a proposta inicial gerada pelo AERA e solicita ajustes de acordo com a expectativa realista baseada na sua percpeção do momento atual do mercado. Cada alteração deve ser justificada e comentada e somente autorizada caso o valor em questão seja superior a um limite mínimo previamente definido pelo Global Supply Chain. O AERA deve reter cada alteração solicitada, aprovada ou negada para consulta, auditoria e análise posterior. O AERA consolidará os dados alterados para gerar as métricas de Lost Sales e D&O apresentando análises de riscos e assertividade dos forecasts frente ao planejamento financeiro.

## Dados ainda não fornecidos

Ainda não há dados quantitativos para medir tempos de ciclo, filas, volumes, lead times por etapa, níveis e cobertura de estoque, taxa de vencimento ou frequência de falta de produto. Também não foram fornecidos dados que comprovem a relação entre cada etapa e as perdas por falta de produto ou vencimento.

## Métricas de sucesso do processo de implantação da mudança 
- nível de D&O
- nível de Lost Sales