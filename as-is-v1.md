%% AS-IS v1 — Planejamento de demanda e abastecimento farmacêutico
%% Atores explicitamente citados no cenário: Marketing, Comercial, Supply Chain Local,
%% Supply Chain Global, Fábricas, Operador Logístico e AURA.
%% Atores inferidos logicamente: Financeiro, Planejamento de Fábrica, Transporte Internacional
%% e Desembaraço Aduaneiro.

flowchart LR
    subgraph MKT[Marketing]
        direction TB
        M1[Coleta expectativa de vendas<br/>com a equipe comercial]
        M2[Consolida dados e faz<br/>ajustes finos manuais]
        ME[Identifica evento extraordinário:<br/>concorrente sem produto, doença,<br/>licitação/bid ou restrição regulatória]
    end

    subgraph COM[Comercial]
        direction TB
        C1[Informa expectativa<br/>de vendas]
    end

    subgraph FIN[Financeiro — inferido]
        direction TB
        F1[Disponibiliza plano financeiro]
    end

    subgraph LSC[Supply Chain Local]
        direction TB
        L1[Consolida forecast de Marketing<br/>e compara com plano financeiro]
        L2[Avalia estoque e restrições/delays<br/>já conhecidos]
        L3[Alinha impactos e planos<br/>de mitigação com Marketing]
    end

    subgraph AURA[Sistema AURA]
        direction TB
        A1[Registra e submete volumes<br/>mensalmente]
    end

    subgraph GSC[Supply Chain Global]
        direction TB
        G1[Avalia disponibilidade de estoque<br/>e capacidade global]
        G2[Define volumes globais<br/>a produzir/abastecer]
        G3[Busca alternativa para evento<br/>extraordinário]
        G4[Informa alteração na programação<br/>ao Supply Chain Local]
    end

    subgraph FAB[Fábricas / Planejamento de fábrica — inferido]
        direction TB
        P1[Programa produção conforme<br/>forecast de vendas]
        P2[Produz e libera produto]
    end

    subgraph LOG[Transporte internacional e desembaraço — inferidos]
        direction TB
        T1[Define modal: navio ou aéreo<br/>conforme urgência]
        T2[Transporta produto]
        T3[Realiza desembaraço]
    end

    subgraph OPL[Operador Logístico]
        direction TB
        O1[Recebe produto]
        O2[Disponibiliza produto<br/>para venda]
    end

    C1 --> M1 --> M2 --> L1
    F1 --> L1
    L1 --> L2 --> G1 --> G2 --> A1 --> P1 --> P2 --> T1 --> T2 --> T3 --> O1 --> O2

    M2 -. sinal de evento .-> ME
    ME --> L3 --> G3 --> G2
    G3 -->|impactos e plano de mitigação| L3
    P1 -->|alteração de programação| G4 --> L3

    classDef actor fill:#EAF2FF,stroke:#2563EB,color:#111827;
    classDef system fill:#FFF4CC,stroke:#D97706,color:#111827;
    classDef output fill:#DCFCE7,stroke:#16A34A,color:#111827;
    class M1,M2,ME,C1,F1,L1,L2,L3,G1,G2,G3,G4,P1,P2,T1,T2,T3,O1 actor;
    class A1 system;
    class O2 output;
