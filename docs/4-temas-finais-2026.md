# Temas finais (6) — metodologia, Datafolha e responsabilização

Este documento **fecha** o Passo 1 de `docs/passos.md`: **seis temas** com **tópicos internos** para análise e futuras afirmações Likert (os cinco primeiro calibrados com Datafolha; o sexto, **Natureza e Meio-ambiente**, por ângulos múltiplos). Substitui o uso de um booleano `presidential_direct` por um campo **`accountability_type`** por tópico (menos frágil, mais honesto sobre federalismo e autonomia).

***

## O que entrou na decisão (resumo)

| Fonte | Uso no projeto |
| ----- | ---------------- |
| `docs/1-metodologia-tema.md` | Quatro critérios (0–2), soma **≥ 6** para tema válido; foco específico; slugs em `data/<slug>/`. |
| **Datafolha** (mar. 2026) | Calibrou **relevância**: problemas federais espontâneos ([saúde 21%, segurança 19%, bloco económico 11%, educação 9%, corrupção 9%](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml)); jornada ([71% a favor de reduzir a carga máxima / 6×1](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/fim-da-escala-seis-por-um-tem-apoio-de-71-dos-brasileiros.shtml)). |
| **Papel do presidente** | Opiniões revelam **valores** (comparáveis entre candidatos). **Responsabilização** real depende do **tipo de ator** (executivo federal, Congresso, BC autárquico, estados, Judiciário). Por isso cada tópico interno tem **`accountability_type`**, não um booleano binário. |
| Temas quentes (mídia) | Ex.: [Operação Contenção](https://pt.wikipedia.org/wiki/Opera%C3%A7%C3%A3o_Conten%C3%A7%C3%A3o) (PM estadual), [INSS](https://pt.wikipedia.org/wiki/Esquema_de_fraudes_no_INSS) (autarquia federal), [Banco Master](https://pt.wikipedia.org/wiki/Esc%C3%A2ndalo_do_Banco_Master) (BC/PF/PGR), [CPI das Bets](https://pt.wikipedia.org/wiki/CPI_das_Bets) (Congresso + regulação) — mapeados para tópicos internos abaixo. |

### Referências Datafolha (originais)

* Hub: [https://datafolha.folha.uol.com.br/](https://datafolha.folha.uol.com.br/)
* Problemas federais espontâneos, 12/03/2026: [notícia](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml) · [PDF](https://media.folha.uol.com.br/datafolha/2026/03/12/naikc-6wqycemf1swpldckx3guswoflcu2riw5fw5ve.pdf)
* Jornada / 6×1, 17/03/2026: [notícia](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/fim-da-escala-seis-por-um-tem-apoio-de-71-dos-brasileiros.shtml) · [PDF](https://media.folha.uol.com.br/datafolha/2026/03/17/r80acaiauggabqidn4ohymjajw2iejdvxtnfp-htpb0.pdf)

***

## `accountability_type` (por tópico interno)

| Valor | Significado |
| ----- | ----------- |
| `executive_primary` | O **governo federal** é o polo principal de política pública executada (normas, orçamento, autarquias). |
| `legislative` | Muda sobretudo com **Congresso** (sanção/veto presidencial entra, mas não é “decisão só do Planalto”). |
| `autonomous_agency` | Papel decisório **técnico-institucional** (ex.: **Banco Central** na supervisão). |
| `shared` | **União + estados/municípios** ou **União + Congresso** em cadeia. |
| `state_local` | Polo principal: **governos estaduais/municipais** (ex.: PM estadual). |
| `judicial` | Polo principal: **Judiciário** / MP autónomo. |
| `values_only` | Eixo sobretudo de **princípios** (útil para comparar candidatos; sem “dono” único da entrega). |

***

## Os seis temas finais

Cada tema: **slug**, **pasta**, **âncora Datafolha** (quando aplicável), **tópicos internos** para aprofundamento e Likert futuros. Os números **1 a 5** correspondem aos eixos fechados contra o Datafolha (março/2026). O tema **6** obriga coberturas **ambientais e climáticas** com vários vectores substantivos entre os quais se escolhem **afirmações Likert não redundantes** (contagens máximas de especialistas e de CSV atualizadas em **`docs/passos.md`** para **6 temas**).

### 1. Economia do trabalho e jornada (6×1)

| Campo | Valor |
| ----- | ----- |
| **Slug** | `jornada_trabalho_modelo_6x1` |
| **Pasta** | `data/jornada_trabalho_modelo_6x1/` |
| **Datafolha** | [71% pela redução da carga máxima](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/fim-da-escala-seis-por-um-tem-apoio-de-71-dos-brasileiros.shtml) |

**Tópicos internos (exploração → Likert)**

| # | Tópico | `accountability_type` |
| - | ------ | --------------------- |
| 1.1 | Fim da escala 6×1 / redução de jornada (44h → 40h) e impactos esperados em rendimento e emprego | `legislative` + `executive_primary` (agenda e execução normativa) |
| 1.2 | Custo para empresas, produtividade, competitividade | `values_only` (com base em dados macro como contexto) |
| 1.3 | Papel do governo em requalificação / transição de trabalhadores | `executive_primary` |

**Nota presidencial:** opinião pesa para **valores**; mudar CLT é **Congresso** + **sanção**; o Planalto **ancora** a prioridade política.

***

### 2. Estado social: SUS, financiamento e governança (inclui previdência/INSS)

| Campo | Valor |
| ----- | ----- |
| **Slug** | `sus_financiamento_planos_emendas_regionalizacao` |
| **Pasta** | `data/sus_financiamento_planos_emendas_regionalizacao/` |
| **Datafolha** | [Saúde 21%](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml) como problema federal espontâneo |

*Nota:* Unifica o antigo recorte `sus_financiamento_planos_emendas_regionalizacao` com o eixo **INSS / fraudes / benefícios**, porque ambos são **política social federal** e **governança de autarquias** — e o eleitor liga “dinheiro público mal aplicado” a **corrupção** ([9% no Datafolha](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml)) sem criar tema separado só para previdência.

**Tópicos internos**

| # | Tópico | `accountability_type` |
| - | ------ | --------------------- |
| 2.1 | Financiamento do SUS: planos privados, complementação, emendas | `shared` |
| 2.2 | Regionalização, filas, atenção primária | `shared` |
| 2.3 | INSS: descontos associativos, fraudes, Dataprev, ressarcimento ([contexto](https://pt.wikipedia.org/wiki/Esquema_de_fraudes_no_INSS)) | `executive_primary` |
| 2.4 | “Quem paga a conta” da crise fiscal da saúde/previdência | `values_only` + `legislative` (reformas) |

***

### 3. Segurança pública, crime e armas

| Campo | Valor |
| ----- | ----- |
| **Slug** | `seguranca_publica_politica_armas` |
| **Pasta** | `data/seguranca_publica_politica_armas/` |
| **Datafolha** | [Segurança/violência 19%](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml) |

**Tópicos internos**

| # | Tópico | `accountability_type` |
| - | ------ | --------------------- |
| 3.1 | Porte de armas, estatuto, tráfego ilegal | `legislative` + `executive_primary` (fiscalização federal em parte) |
| 3.2 | Federalismo: PEC segurança, papel da União vs estados | `shared` |
| 3.3 | Crime organizado, fronteiras, PF/PRF | `executive_primary` |
| 3.4 | Operações policiais de grande letalidade / uso da força ([ex.: Rio](https://pt.wikipedia.org/wiki/Opera%C3%A7%C3%A3o_Conten%C3%A7%C3%A3o)) | `state_local` (PM estadual) + `shared` (papel federal de investigação/coordenação) |
| 3.5 | Direitos humanos vs ordem (posição de princípio) | `values_only` |

**Nota presidencial:** o presidente **não comanda** PM estadual; opinião e **proposta de coordenação federal** importam para o eleitor.

***

### 4. Implementação da reforma tributária (IVA dual, transição)

| Campo | Valor |
| ----- | ----- |
| **Slug** | `implementacao_reforma_tributaria_iv_dual` |
| **Pasta** | `data/implementacao_reforma_tributaria_iv_dual/` |
| **Datafolha** | [Bloco económico 11%](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml) (inflação, preços, economia) |

**Tópicos internos**

| # | Tópico | `accountability_type` |
| - | ------ | --------------------- |
| 4.1 | CBS/IBS, transição, neutralidade de carga | `legislative` + `executive_primary` (Receita/implementação) |
| 4.2 | Efeitos por setor (agronegócio, serviços, comércio) | `values_only` (com séries públicas como contexto) |
| 4.3 | Confiança no sistema financeiro e supervisão ([contexto Master](https://pt.wikipedia.org/wiki/Esc%C3%A2ndalo_do_Banco_Master)) | `autonomous_agency` + `judicial` + `executive_primary` (nomeações, agenda anticorrupção) |

***

### 5. Educação: Novo Ensino Médio, avaliação e financiamento federal

| Campo | Valor |
| ----- | ----- |
| **Slug** | `novo_ensino_medio_avaliacao_financiamento` |
| **Pasta** | `data/novo_ensino_medio_avaliacao_financiamento/` |
| **Datafolha** | [Educação 9%](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml) |

**Tópicos internos**

| # | Tópico | `accountability_type` |
| - | ------ | --------------------- |
| 5.1 | NEM: itinerários, permanência, carga horária | `shared` (MEC + redes estaduais) |
| 5.2 | SAEB, Enem, avaliação de qualidade | `shared` |
| 5.3 | Financiamento (FUNDEB, complementação federal) | `shared` + `legislative` |
| 5.4 | Prioridade do ensino médio face a outros níveis | `values_only` |

***

### 6. Natureza e Meio-ambiente (Amazónia, clima, biodiversidade e mineração)

| Campo | Valor |
| ----- | ----- |
| **Slug** | `natureza_meio_ambiente_amazonia_clima_mineracao` |
| **Pasta** | `data/natureza_meio_ambiente_amazonia_clima_mineracao/` |
| **Datafolha** | *Fora do item-a-item da pergunta espontânea federal de março/2026 já usada para os temas 1–5; consistente com o eixo onde **Amazónia/clima** sustentam **diferenciação programática** em `docs/3-proposta-temas-2026.md` (“fora do ranking espontâneo”, válidos pela metodologia de score).* |

Este tema garante cobertura **ambiental-climática** obrigatória no projeto. Para **Likert**, escolher **ângulos distintos** (diferentes em valores e em **tipo de responsabilização**), em vez de várias formulando quase a mesma alavanca. O recorte paralelo **`desmatamento_amazonia_metas_climaticas`** distribui‑se sobretudo por **6.1** e **6.2** abaixo.

**Mineradora Serra Verde (terras-raras, Goiás)** — o enquadramento natural neste projeto é **Natureza e Meio-ambiente**: vectores sócioambientais e de licenciamento mineiro (**6.5**) e o que o debate colocou em evidência (**marco legal**, **modelo estatal × privado**, **capital/controlador norte-americano**, **Memorando Goiás–EUA**, papel do Brasil na **cadeia global** de refino e fornecimento) (**6.6**). Uma afirmação Likert exclusivamente sobre **economia tributária geral** ou **abertura a investimento estrangeiro** *sem vínculo a mineração, licenciamento ambiental ou minerais estratégicos* pode ser marcada também como tangente ao **tema 4**, ou como **política externa pura** se surgir tema dedicado mais tarde — mas **pastas CSV e código** neste ciclo devem **ancorar o caso ao tema 6**.

Referência factual de âmbito (terras‑raras; não substitui jornais em citações de candidatos): [Elementos terras‑raras — Wikipédia](https://pt.wikipedia.org/wiki/Elementos_terras-raras).

**Contexto público sobre terras-raras (abril–maio de 2026):** o debate volta ao centro nacional por estes minerais serem estratégicos na **transição energética**, na **indústria militar** e nas cadeias globais correlatas — com o país citado com **elevado potencial de reserva** e **papel** menor ainda na **cadeia de refino e fornecedor** internacional. Na comunicação pública recente surgem projetos minerários em **Goiás** destacando a **Serra Verde**, **investimento/controlador norte-americano** relacionado à administração **Trump**; memorando estadual **Goiás–EUA**, assinado na gestão **Ronaldo Caiado (PSD)** e alvo de **questionamento jurídico**; e um projeto de lei no **Congresso** que fixaria **marco legal** sobre exploração, com tramitação **adiada** e disputa entre **modelo estatal** e **predominância de capitais privados**, enquanto o **governo Lula** diz **não ver urgência** numa estatal e o **PT** **defende** a criação de empresa pública no setor.

#### 6.a — ângulos amplos ambientais (Likert bem dispersos)

| # | Tópico | `accountability_type` |
| - | ------ | --------------------- |
| 6.1 | Amazónia legal: **desmatamento**, fiscalização (Ibama/forças de apoio), tensão agrícola-fronteiriça, ordenamento fundiário | `executive_primary` + `shared` |
| 6.2 | **Clima e transição**: NDC brasileiros, políticas de execução interna, financiamento climático, nexo tributário/energético onde couber | `executive_primary` + `shared` |
| 6.3 | **Água** (bacias, qualidade urbana/industrial), resíduos e poluição difusa relevante ambientalmente | `shared` |
| 6.4 | **Biodiversidade** para além da Amazónia legal (**Cerrado**, Mata Atlântica, zonas costeiras), unidades de conservação, comunidades quilombolas e povos indígenas quando o recorte assim o exija | `shared` + `values_only` |

#### 6.b — mineração, terras‑raras e soberania tecnológico-industrial

Opcional ao organizar ficheiros: subpasta `terras_raras_exploracao_marco_legal_soberania_cadeia/` *dentro* de `data/natureza_meio_ambiente_amazonia_clima_mineracao/` quando apenas fontes deste vértice exijam separação.

| # | Tópico | `accountability_type` |
| - | ------ | --------------------- |
| 6.5 | **Mineração em geral:** licenciamento e estudos de impacto, compensações/reparações, royalties e distribuição entre esferas, comunidades próximas a grandes empreendimentos | `shared` + `legislative` |
| 6.6 | **Terras‑raras e minerais críticos:** marco jurídico nacional, papel estatal versus privado, soberania tecnológico-industrial na cadeia, cooperações subnacionais com parceiros externos (memorandos, proprietário/controlador estrangeiro e transparência em setores classificados como estratégicos) | `legislative` + `shared` + `executive_primary` |

**Orientação Likert sobre terras‑raras:** quando houver texto normativo estável ou compromisso explícito para citar, testar um formulado do tipo «Concorda que deve prevalecer *X*, na exploração de terras‑raras, mesmo que atrase ou reduza investimento privado estrangeiro de curto prazo?», substituindo *X* por uma **opção normativa concretamente escrita** antes de aplicar o questionário.

***

## O que fica fora dos 6 (mas já mapeado)

* **`anistia_8_janeiro`**, **`regulacao_inteligencia_artificial_brasil`**, **`politica_externa_venezuela_mercosul`**, **`combate_desinformacao_regulacao_plataformas`** — continuam válidos pelo score em `docs/3-proposta-temas-2026.md`; usar como **rodízio**, **ondas** de questionários ou fusão futura (ex.: democracia + redes num segundo ciclo).

* **`desmatamento_amazonia_metas_climaticas`** — conteúdo absorvido pelos subtópicos **6.1** e **6.2**; o slug preserva uso **historial** na tabela paralela dos dez temas (`docs/3-proposta-temas-2026.md`).

* **`terras_raras_exploracao_marco_legal_soberania_cadeia`** — não é tema **7**; é **sub-recorte facultativo** dentro do tema **6** (secção **6.b**).

* **CPI das Bets** — encaixa em **tributária/regulação** (`legislative` / `executive_primary` para regulação dentro da lei) e **valores**; contexto legal e debate presidencial: [Agência Brasil, 08/04/2026](https://agenciabrasil.ebc.com.br/politica/noticia/2026-04/lula-defende-proibicao-de-bets-e-mostra-preocupacao-com-endividamento) (cita Lei 14.790/2023).

***

## Próximo passo

**4 a 5 especialistas** por tema (até **~30**, seis × cinco cotas — `docs/2-metodologia-especialistas.md`) e **afirmações Likert** com **vários ângulos substantivos dentro do tema 6**, evitando duplicar o mesmo par `valor × accountability_type` sem necessidade.
