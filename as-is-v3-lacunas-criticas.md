# Lacunas críticas para finalizar o AS-IS

Base de análise: `quadro-cenario-problema-farmaceutica-v2.md`.

Esta versão substitui a lista ampla de lacunas por somente o que ainda impede a finalização de um AS-IS fiel ao processo e sustentado por evidências. Não repete pontos já esclarecidos: periodicidade mensal, sistema AERA, plano financeiro, estoques analisados, prazo médio total de cinco meses e responsabilidade de Supply Chain Local pela estratégia logística e desembaraço.

## 1. Decisão e registro do volume final

**O que já se sabe:** Marketing “assume o risco de eventuais perdas” quando há conflito entre Marketing, plano financeiro, estoque e restrições.

**O que ainda falta:** essa afirmação não informa qual é a decisão operacional tomada após o *sanity check*: quem aprova ou bloqueia o volume final, se Supply Chain Local/Global pode limitar o forecast, qual volume é efetivamente submetido e onde a decisão fica registrada no AERA.

**Por que é crítico para o AS-IS:** sem isso, não é possível representar corretamente o ponto de decisão entre forecast desejado, viabilidade de abastecimento e compromisso financeiro — que é o núcleo do conflito descrito no problema.

**Pergunta objetiva:** após o *sanity check*, quem define o volume final por produto/país e como uma divergência entre Marketing e Supply Chain é registrada no AERA?

## 2. Handoffs e integração entre AERA, SAP Analytics Cloud Planning e SAP

**O que já se sabe:** previsão é inserida no AERA; o plano financeiro é submetido no SAP Analytics Cloud Planning; fábricas consultam no SAP os estoques do Brasil, da fábrica e em trânsito.

**O que ainda falta:** não está informado se as informações passam automaticamente entre esses sistemas ou se há exportação, planilha, e-mail ou lançamento manual; tampouco quem realiza cada transferência e em qual momento do ciclo mensal.

**Por que é crítico para o AS-IS:** o diagrama precisa mostrar os fluxos de informação entre as etapas. Sem essa definição, não se pode afirmar onde há transferência manual, espera, risco de erro ou retrabalho.

**Pergunta objetiva:** como o forecast do AERA, o plano financeiro do SAP Analytics Cloud Planning e a informação de estoque do SAP são disponibilizados para o *sanity check* e para o planejamento das fábricas?

## 3. Composição do lead time médio de cinco meses

**O que já se sabe:** o prazo médio entre Supply Chain receber o planejamento de demanda e a mercadoria ficar disponível para venda na sucursal brasileira é de cinco meses.

**O que ainda falta:** não há separação desse prazo entre validação global, programação/produção, espera de embarque, transporte marítimo/aéreo, desembaraço e entrega ao operador logístico. Também não se sabe onde há fila ou atraso recorrente.

**Por que é crítico para o AS-IS:** cinco meses é uma informação relevante, mas não identifica o gargalo. Para marcar um gargalo ou desperdício de espera no mapa atual, é preciso saber em qual etapa o tempo se acumula.

**Pergunta objetiva:** dos cinco meses, qual é o tempo médio e a espera média em cada etapa: validação global, produção, embarque/transporte, desembaraço e entrega ao operador logístico?

## 4. Evidência e dimensão das duas perdas informadas

**O que já se sabe:** há perda de receita por falta de produto e perda financeira por destruição de produto vencido.

**O que ainda falta:** faltam dados que permitam localizar, dimensionar e relacionar essas perdas ao processo: forecast versus venda real, quantidade/valor de vendas perdidas por ruptura, quantidade/valor de produtos vencidos, validade remanescente, estoque por localidade e número de revisões do forecast.

**Por que é crítico para o AS-IS:** os requisitos do trabalho pedem pontos de dor, gargalos e desperdícios. Sem evidência, o diagrama pode apresentar apenas hipóteses, e não problemas do processo atual comprovados.

**Pergunta objetiva:** é possível obter, por produto/país/mês, forecast inicial e final, venda real, rupturas/vendas perdidas, estoque e perdas por vencimento?

## Itens que não são lacunas críticas para o primeiro AS-IS

- A origem do plano financeiro e o fluxo de sua aprovação já estão descritos.
- As etapas 1 e 2 têm periodicidade mensal.
- O AERA foi identificado como sistema de previsão e consolidação.
- A análise considera estoque local, estoque global e capacidade de produção.
- Supply Chain Local define a estratégia logística e responde pelo desembaraço via despachante.
- Eventos extraordinários podem ser representados, no primeiro AS-IS, como fluxo de exceção de Marketing/Comercial para Supply Chain Local e Global; não é necessário detalhar ainda todas as regras de realocação entre países.
