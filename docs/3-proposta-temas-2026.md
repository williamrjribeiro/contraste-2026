# Proposta de temas — Brasil 2026 (avaliação paralela)

**Lista fechada dos cinco temas, tópicos internos e `accountability_type`:** ver `docs/4-temas-finais-2026.md`.

Este ficheiro consolida **dez avaliações independentes** feitas em paralelo (cada uma com foco num tema), seguindo o quadro de `docs/1-metodologia-tema.md`:

| Critério | Pergunta prática | Score |
| -------- | ---------------- | ----- |
| Relevância eleitoral | Aparece em debates, sondagens ou programas? | 0–2 |
| Diferenciação | Existem posições divergentes entre candidatos? | 0–2 |
| Documentação | Existem pelo menos 3 fontes por candidato? | 0–2 |
| Atualidade | Houve desenvolvimentos nos últimos 12 meses? | 0–2 |

**Regra:** soma **≥ 6** → tema válido; **≤ 5** → rejeitar.

**Nota metodológica:** nos critérios de “documentação” e “diferenciação”, a lista alargada de pré-candidatos em `docs/0-candidatos.md` (oito nomes) pode exigir **triagem**: há temas com abundância de fontes para os polos (Lula, Flávio Bolsonaro, governadores com mandato) e menos matéria dedicada para estreantes ou figuras com menos tempo de antena no mesmo recorte. As notas abaixo assinalam isso quando relevante.

***

## Cruzamento com o Datafolha (março de 2026)

O site do **Datafolha** ([https://datafolha.folha.uol.com.br/](https://datafolha.folha.uol.com.br/)) publica, entre outras rubricas, levantamentos em **Opinião e sociedade** e **Eleições**. Dois textos de **março de 2026** ajudam a calibrar **relevância eleitoral** e a proximidade com o que os brasileiros dizem priorizar neste ciclo:

1. **Problemas de responsabilidade federal (espontâneo)** — *“Saúde (21%) e segurança pública (19%) são áreas de responsabilidade federal mais problemáticas”*, 12/03/2026, com relatório em PDF: [https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/saude-21-e-seguranca-publica-19-sao-areas-de-responsabilidade-federal-mais-problematicas.shtml) ([PDF](https://media.folha.uol.com.br/datafolha/2026/03/12/naikc-6wqycemf1swpldckx3guswoflcu2riw5fw5ve.pdf)).

   No corpo da notícia, o instituto resume a hierarquia (citações **espontâneas** do “principal problema” entre áreas federais): **saúde 21%**; **segurança pública/violência 19%** (em alta face a levantamentos anteriores); temas económicos (inflação, economia em geral, preços) **11%**; **corrupção 9%**; **educação 9%**; desemprego 4%; outros.

2. **Jornada e escala 6×1** — *“Fim da escala seis por um tem apoio de 71% dos brasileiros”*, 17/03/2026: [https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/fim-da-escala-seis-por-um-tem-apoio-de-71-dos-brasileiros.shtml](https://datafolha.folha.uol.com.br/opiniao-e-sociedade/2026/03/fim-da-escala-seis-por-um-tem-apoio-de-71-dos-brasileiros.shtml) ([PDF](https://media.folha.uol.com.br/datafolha/2026/03/17/r80acaiauggabqidn4ohymjajw2iejdvxtnfp-htpb0.pdf)). **71%** dos entrevistados (16+ anos) dizem que a **carga máxima de trabalho deveria ser reduzida** face ao enquadramento legal atual (44h, até seis dias — escala 6×1).

### Tabela de alinhamento (Datafolha → slugs deste projeto)

| Indicador ou eixo Datafolha (mar. 2026) | Slug(s) do projeto que cobrem o recorte |
| --------------------------------------- | ---------------------------------------- |
| Saúde como principal problema federal (21%) | `sus_financiamento_planos_emendas_regionalizacao` (recorte orçamentário e federativo, não “saúde” vaga) |
| Segurança pública/violência (19%) | `seguranca_publica_politica_armas` |
| Economia / preços / inflação (11%) | `implementacao_reforma_tributaria_iv_dual` (efeitos de transição e setores) |
| Educação (9%) | `novo_ensino_medio_avaliacao_financiamento` |
| Corrupção (9%) | *Não há slug dedicado na lista de dez;* possível tema futuro ou ângulo transversal em `anistia_8_janeiro` / governança — a validar no fecho dos cinco |
| Apoio majoritário à redução de jornada / fim do 6×1 (71%) | `jornada_trabalho_modelo_6x1` |

Temas fortes no projeto mas **fora do ranking espontâneo** da pergunta federal acima — **IA**, **Amazônia/metas climáticas**, **Venezuela**, **desinformação** — continuam válidos pelo quadro de `docs/1-metodologia-tema.md`, mas pesam mais em **diferenciação programática** e **documentação técnica** do que em “top of mind” dessa pergunta específica.

***

## Tabela — dez temas avaliados em paralelo

| Tema (título) | Slug (`data/<slug>/`) | R | D | Doc | A | Total |
| ------------- | ---------------------- | - | - | --- | - | ----- |
| Jornada de trabalho e fim da escala 6×1 (44h/40h, CLT, produtividade) | `jornada_trabalho_modelo_6x1` | 2 | 2 | 1 | 2 | **7** |
| Anistia (ou pacotes legislativos equivalentes) aos envolvidos nos atos de 8 de janeiro de 2023 | `anistia_8_janeiro` | 2 | 2 | 1 | 2 | **7** |
| Regulação de inteligência artificial no Brasil (risco, inovação, autoral, uso público) | `regulacao_inteligencia_artificial_brasil` | 2 | 2 | 2 | 2 | **8** |
| Desmatamento na Amazônia e metas climáticas (fiscalização, fundiário, agro na fronteira, financiamento) | `desmatamento_amazonia_metas_climaticas` | 2 | 2 | 2 | 2 | **8** |
| Segurança pública, crime organizado e política de armas (porte, fronteiras, PEC/federalismo) | `seguranca_publica_politica_armas` | 2 | 1 | 2 | 2 | **7** |
| Implementação da reforma tributária (IVA dual CBS/IBS, transição, compensações setoriais) | `implementacao_reforma_tributaria_iv_dual` | 2 | 2 | 2 | 2 | **8** |
| Política externa regional: Venezuela, crise democrática e efeitos no Brasil (Mercosul, refugiados) | `politica_externa_venezuela_mercosul` | 2 | 2 | 1 | 2 | **7** |
| Novo Ensino Médio, SAEB/Enem e financiamento federal (itinerários, permanência) | `novo_ensino_medio_avaliacao_financiamento` | 2 | 2 | 1 | 2 | **7** |
| Financiamento do SUS (contribuição de planos), emendas e regionalização assistencial | `sus_financiamento_planos_emendas_regionalizacao` | 2 | 2 | 2 | 2 | **8** |
| Combate à desinformação e regulação de redes/plataformas (Marco Civil, TSE, projetos tipo PL 2630) | `combate_desinformacao_regulacao_plataformas` | 2 | 2 | 2 | 2 | **8** |

**Todos os dez temas cumprem o limiar ≥ 6** e respeitam o pedido de foco específico (evitando “economia” ou “saúde” genéricos sem recorte).

***

## Conjunto sugerido para o Passo 1 (`docs/passos.md`): cinco temas

### Versão A — alinhamento explícito ao Datafolha (março 2026)

Esta versão **espelha** os dois primeiros lugares da pergunta espontânea sobre problemas federais (**saúde**, **segurança**), o **bloco económico** (11%), a **educação** (9%) e o levantamento dedicado à **jornada/6×1** (71% a favor da redução da carga máxima). Mantém **cinco temas** sem duplicar “economia” genérica.

| # | Tema | Slug | Pasta sugerida | Âncora Datafolha |
| - | ---- | ---- | --------------- | ---------------- |
| 1 | Jornada de trabalho / 6×1 | `jornada_trabalho_modelo_6x1` | `data/jornada_trabalho_modelo_6x1/` | Apoio 71% à redução da jornada máxima (17/03/2026) |
| 2 | Financiamento do SUS, planos e emendas | `sus_financiamento_planos_emendas_regionalizacao` | `data/sus_financiamento_planos_emendas_regionalizacao/` | Saúde 21% como principal problema federal (12/03/2026) |
| 3 | Segurança pública e política de armas | `seguranca_publica_politica_armas` | `data/seguranca_publica_politica_armas/` | Segurança/violência 19% (12/03/2026) |
| 4 | Implementação da reforma tributária (IVA dual) | `implementacao_reforma_tributaria_iv_dual` | `data/implementacao_reforma_tributaria_iv_dual/` | Bloco económico/inflação/preços 11% |
| 5 | Novo Ensino Médio, SAEB/Enem e financiamento | `novo_ensino_medio_avaliacao_financiamento` | `data/novo_ensino_medio_avaliacao_financiamento/` | Educação 9% |

### Versão B — equilíbrio “agenda pública + diferenciação de campanha”

Se quiser **forçar** um eixo de **democracia institucional** que polariza pré-candidatos mas **não aparece** como categoria espontânea nesse recorte do Datafolha, troque o **#5** da Versão A por **`anistia_8_janeiro`**, ou o **#4** por **anistia** e mantenha a tributária como **reserva** (ver abaixo).

| # | Tema | Slug | Pasta sugerida |
| - | ---- | ---- | --------------- |
| 1 | Jornada de trabalho / 6×1 | `jornada_trabalho_modelo_6x1` | `data/jornada_trabalho_modelo_6x1/` |
| 2 | Anistia e atos de 8 de janeiro de 2023 | `anistia_8_janeiro` | `data/anistia_8_janeiro/` |
| 3 | Regulação de IA no Brasil | `regulacao_inteligencia_artificial_brasil` | `data/regulacao_inteligencia_artificial_brasil/` |
| 4 | Amazônia, desmatamento e metas climáticas | `desmatamento_amazonia_metas_climaticas` | `data/desmatamento_amazonia_metas_climaticas/` |
| 5 | Financiamento do SUS, planos e emendas | `sus_financiamento_planos_emendas_regionalizacao` | `data/sus_financiamento_planos_emendas_regionalizacao/` |

**Reservas (troca 1:1):** `seguranca_publica_politica_armas` (Datafolha 19%) se a Versão B ficar sem segurança; `implementacao_reforma_tributaria_iv_dual` (Datafolha 11% económico) em lugar do **#4** ou **#5** conforme a sua prioridade analítica.

***

## Contexto resumido (por tema sugerido)

Os blocos abaixo cobrem os slugs das **Versões A e B**; use só os que corresponderem ao conjunto de cinco que fechar.

### `jornada_trabalho_modelo_6x1`

Em 2025–2026 o debate sobre **fim da escala 6×1** e **redução da jornada** ocupou centro do Congresso e da comunicação de governo, com reação de entidades patronais e de pré-candidatos de centro-direita que associam flexibilização da CLT a competitividade. O **Datafolha** (17/03/2026) regista **71%** a favor da **redução da carga máxima** no enquadramento atual (44h, até seis dias — 6×1), o que reforça **relevância eleitoral** além da cobertura legislativa. O tema é **mensurável** (propostas, sondagens, posições públicas) e **polariza** de forma legível.

### `anistia_8_janeiro`

A tensão entre **anistia legislativa ampla** (e debates sobre inelegibilidades) e a linha de **responsabilização** e **rejeição de perdão** permaneceu na agenda parlamentar e é explorada por campanhas. Há **diferenciação forte** entre quem assume publicamente a pauta da anistia, quem a rejeita e quem propõe vias jurídicas alternativas (revisão de penas, clemência). A documentação é **desigual por pré-candidato**; convém priorizar declarações e projetos com data e veículo.

### `regulacao_inteligencia_artificial_brasil`

Tramitação do **PL 2338/2023**, projetos satélites (deepfakes, governo, autoral) e iniciativas de **governança no setor público** mantêm o tema atual e técnico o suficiente para fugir de slogan. Permite contrastar **inovação versus precaução**, **direitos de titulares**, **transparência algorítmica** e papel do Estado — com base em texto legal e relatórios.

### `desmatamento_amazonia_metas_climaticas`

Indicadores oficiais e de alerta (**MMA**, **INPE/DETER**, **IBAMA**) dão âncora quantitativa; o tema cruza **soberania ambiental**, **agro**, **regularização fundiária** e **diplomacia climática**. A disputa entre **modelo de fiscalização** e **flexibilização/licenciamento** aparece de forma diferenciada entre campos políticos.

### `sus_financiamento_planos_emendas_regionalizacao`

Recorte evita “saúde” genérica: concentra-se em **quem financia o SUS**, **contribuição de planos**, **canal das emendas** e **desigualdade regional** de acesso. Há base em **Ministério da Saúde**, **ANS**, **Congresso** e literatura de institutos — adequado a afirmações mensuráveis e a tensões federativas. O **Datafolha** de 12/03/2026 coloca **saúde** no topo das **citações espontâneas** de problemas federais (**21%**), o que sustenta a escolha deste slug em vez de um tema de saúde indiferenciado.

### `seguranca_publica_politica_armas`

O mesmo levantamento de 12/03/2026 posiciona **segurança pública/violência** em **19%** nas respostas espontâneas (em alta face a ondas anteriores), com **diferença por género** (homens citam mais segurança; mulheres, mais saúde). O recorte proposto (armas, fronteiras, federalismo, crime organizado com base institucional) mantém o tema **específico** e comparável entre candidatos.

### `implementacao_reforma_tributaria_iv_dual`

O bloco **económico** agregado (inflação, economia em geral, aumento de preços) aparece com **11%** no levantamento espontâneo de março de 2026 — não substitui uma sondagem dedicada à reforma tributária, mas ancora **relevância** numa reforma com **texto legal**, cronograma de transição e **efeitos setoriais** mensuráveis (Receita Federal, IBGE).

### `novo_ensino_medio_avaliacao_financiamento`

**Educação** surge com **9%** no mesmo recorte espontâneo federal. O foco em **NEM**, **SAEB/Enem** e **financiamento** evita “educação” genérica e liga o tema a normas do **MEC**, dados do **INEP** e tensão de implementação nos estados.

***

## Próximo passo (após a sua revisão)

Quando fechar os **cinco temas**, seguir o Passo 2 em `docs/passos.md` e `docs/2-metodologia-especialistas.md`: **4 a 5 especialistas por tema** (máximo 25).
