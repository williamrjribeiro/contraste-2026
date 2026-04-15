# Metodologia de escolha automática de temas

# Passo 1: Definição do Tema

## Objetivo

Selecionar um tema político relevante, mensurável e com diferenciação real entre candidatos. Possiveis fontes de pesquisa:

* <https://datafolha.folha.uol.com.br/>
* <https://www.reddit.com/r/PoliticaBrasileira/>

Exemplos de temas a explorar

* Escala 6x1
* Escandalo corrupção do Banco Master
* Anistia aos envolvidos nos protestos do dia 8 de janeiro de 2023
* Guerra Ukrania v Russia
* Guerra Israel + EUA v Palestina + Libano + Irã
* Inteligencia Artificial

## Framework de Avaliação

| Critério             | Pergunta prática                               | Score |
| -------------------- | ---------------------------------------------- | ----- |
| Relevância eleitoral | Aparece em debates, sondagens ou programas?    | 0–2   |
| Diferenciação        | Existem posições divergentes entre candidatos? | 0–2   |
| Documentação         | Existem pelo menos 3 fontes por candidato?     | 0–2   |
| Atualidade           | Houve desenvolvimentos nos últimos 12 meses?   | 0–2   |

### Regra de Decisão

* ≥ 6 → Tema válido
* ≤ 5 → Rejeitar

## Regras de Qualidade

* Foco específico (evitar “economia”)
* Conflito real entre posições
* Mensurável com dados públicos
* Base factual sólida

## Output

* `{tema}`
* Contexto (2–3 parágrafos)
* Score detalhado

Exemplo:

| Tema                        | Slug              | Pasta                   | Score |
| --------------------------- | ----------------- | ----------------------- | ----- |
| Política Económica e Fiscal | `economia_fiscal` | `data/economia_fiscal/` | 6     |

Usar sempre o **slug** da tabela acima para nomear pastas e ficheiros. O slug deve ser em minúsculas, sem acentos, com underscores em vez de espaços.
