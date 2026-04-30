# Temas finais (5) — metodologia, Datafolha e responsabilização

Este documento **fecha** o Passo 1 de `docs/passos.md`: **cinco temas** com **tópicos internos** para análise e futuras afirmações Likert. Substitui o uso de um booleano `presidential_direct` por um campo **`accountability_type`** por tópico (menos frágil, mais honesto sobre federalismo e autonomia).

***

## O que entrou na decisão (resumo)

| Fonte | Uso no projeto |
| ----- | ---------------- |
| `docs/1-metodologia-tema.md` | Quatro critérios (0–2), soma **≥ 6** para tema válido; foco específico; slugs em `data/<slug>/`. |
| **Datafolha** (mar. 2026) | Calibrou **relevância**: problemas federais espontâneos ([saúde 21%, segurança 19%, bloco económico 11%, educação 9%, corrupção 9%](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml)); jornada ([71% a favor de reduzir a carga máxima / 6×1](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/fim-da-escala-seis-por-um-tem-apoio-de-71-dos-brasileiros.shtml)). |
| **Papel do presidente** | Opiniões revelam **valores** (comparáveis entre candidatos). **Responsabilização** real depende do **tipo de ator** (executivo federal, Congresso, BC autárquico, estados, Judiciário). Por isso cada tópico interno tem **`accountability_type`**, não um booleano binário. |
| Temas quentes (mídia) | Ex.: [Operação Contenção](https://pt.wikipedia.org/wiki/Opera%C3%A7%C3%A3o_Conten%C3%A7%C3%A3o) (PM estadual), [INSS](https://pt.wikipedia.org/wiki/Esquema_de_fraudes_no_INSS) (autarquia federal), [Banco Master](https://pt.wikipedia.org/wiki/Esc%C3%A2ndalo_do_Banco_Master) (BC/PF/PGR), [CPI das Bets](https://pt.wikipedia.org/wiki/CPI_das_Bets) (Congress + regulação) — mapeados para tópicos internos abaixo. |

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

## Os cinco temas finais

Cada tema: **slug**, **pasta**, **âncora Datafolha** (quando aplicável), **tópicos internos** para aprofundamento e Likert futuros.

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

*Nota:* Unifica o antigo recorte `sus_financiamento_planos_emendas_regionalizacao` com o eixo **INSS / fraudes / benefícios**, porque ambos são **política social federal** e **governança de autarquias** — e o eleitor liga “dinheiro público mal aplicado” a **corrupção** ([9% no Datafolha](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml)) sem precisar de um sexto tema.

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

### Natureza e Meio-ambiente — terras-raras e mineração estratégica (Likert sob âncora temática maior)

Este recorte integra um **âmbito temático maior** sobre **Natureza e Meio-ambiente**, onde **`desmatamento_amazonia_metas_climaticas`** aparece já como tema paralelo em `docs/3-proposta-temas-2026.md`. Os **cinco temas finais** fechados com Datafolha acima não reservam bloco próprio nem à Amazónia nem a minerais estratégicos; **mantêm-se aqui** o **slug**, os **tópicos internos** e **`accountability_type`** para **futuras afirmações Likert**, com foco atual na **cadeia de terras-raras**.

Em **abril–maio de 2026**, o debate sobre **minerais críticos ou terras-raras** volta ao centro nacional (relevância global na transição energética e em setores sensíveis; **Brasil** com **elevado potencial de reservas** e **peso menor ainda na cadeia global** de refino e fornecimento). Entram nos **marcadores públicos**: operação minerária em **Goiás** (entre os casos emblemáticos, **Serra Verde** e comunicação sobre **investimento/controlador nos EUA ligado ao apoio do governo Trump**); cooperação subnacional com parceiros estrangeiros (**memorando Goiás–EUA** na anterior gestão estadual **Ronaldo Caiado**, alvo de **questionamento jurídico**); projeto de **lei** que fixaria **marco legal** sobre exploração de terras-raras, cuja análise no **Congresso** foi **adiada**, gerando atrito típico (**inclusão de estatal** versus predominânio de projeto privado) enquanto o **Planalto** indica não ver urgência para estatal e o **campo próximo ao PT defende modelo estatal.**

| Campo | Valor |
| ----- | ----- |
| **Slug** | `terras_raras_exploracao_marco_legal_soberania_cadeia` |
| **Pasta** | `data/terras_raras_exploracao_marco_legal_soberania_cadeia/` |
| **Âncora Datafolha** | *Inexistente nos recortes de março/2026 já usados para fechar os cinco temas; relevância aqui por **agenda económico-estratégica e legislativa**.* |

Referência de âmbito (não substitui cobertura jornalística para factos concretos): [Elementos terras-raras — Wikipédia](https://pt.wikipedia.org/wiki/Elementos_terras-raras).

**Tópicos internos (exploração → Likert)**

| # | Tópico | `accountability_type` |
| - | ------ | --------------------- |
| N.1 | Marco legal nacional (lei de exploração, licenciamento, royalties, ordenamento territorial minerário federal–estadual) | `legislative` + `shared` |
| N.2 | Soberania e posicionamento estratégico do Brasil na cadeia global (valor agregado, refino, transição energética, indústria de defesa) | `executive_primary` + `shared` |
| N.3 | Modelo institucional: **estatal** setorial versus predominânio de concessionárias privadas e investimento estrangeiro (inclui tensão governo/partido sobre necessidade ou não de estatal) | `legislative` + `values_only` |
| N.4 | Cooperação subnacional com parceiros estrangeiros; licitude, transparência e controle público (memorandos intergovernativos; alteração de proprietários/controladores de projetos mineiros estratégicos) | `shared` + `executive_primary` (política externa quando aplicável) |
| N.5 | Custos sócioambientais (água, solos e comunidades) de explorações de terras-raras no Brasil versus benefício económico | `shared` + `values_only` |

**Likert futuro (exemplo orientador, formulável quando houver texto fechado de lei ou posições públicas atualizadas):** usar um enunciado concreto *“Concorda que … sobre exploração de terras-raras e papel do Estado deve ser aplicada mesmo que isso atrase investimento estrangeiro ou privado.”*, preenchendo o espaço antes de “sobre” com a **posição a testar** (texto normativo ou citação de governo/partido); desdobrar por **N.1–N.5**.

***

## O que fica fora dos 5 (mas já mapeado)

* **`anistia_8_janeiro`**, **`regulacao_inteligencia_artificial_brasil`**, **`desmatamento_amazonia_metas_climaticas`**, **`politica_externa_venezuela_mercosul`**, **`combate_desinformacao_regulacao_plataformas`** — continuam válidos pelo score em `docs/3-proposta-temas-2026.md`; usar como **rodízio**, **ondas** de questionários ou fusão futura (ex.: democracia + redes num segundo ciclo).

* **`terras_raras_exploracao_marco_legal_soberania_cadeia`** — enquadrado no **Âmbito Natureza e Meio-ambiente**, acima (Likert paralelo aos cinco fechados; pode **fundir-se** temporalmente em questionários sobre Amazónia/indústria verde segundo o desenho de onda).

* **CPI das Bets** — encaixa em **tributária/regulação** (`legislative` / `executive_primary` para regulação dentro da lei) e **valores**; contexto legal e debate presidencial: [Agência Brasil, 08/04/2026](https://agenciabrasil.ebc.com.br/politica/noticia/2026-04/lula-defende-proibicao-de-bets-e-mostra-preocupacao-com-endividamento) (cita Lei 14.790/2023).

***

## Próximo passo

Para cada tópico interno, **4 a 5 especialistas** por tema (`docs/2-metodologia-especialistas.md`) e depois **afirmações Likert** (sem duplicar tópicos com o mesmo `accountability_type` sem necessidade).
