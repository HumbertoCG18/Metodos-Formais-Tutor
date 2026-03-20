## MÉTODOS FORMAIS

Prof. Júlio Machado

## LÓGICA PROPOCIONAL

Introdução

Baseado nos materiais do Prof. Daniel Callegari

## Proposição

- Costuma-se usar a palavra ' proposição ' para designar o significado de uma sentença ou oração declarativa.
- Exemplo: 'João ama Maria' é o mesmo que 'Maria é amada por João'.

## Proposição

- Toda proposição é uma frase (mas nem toda frase é uma proposição); uma frase é uma proposição apenas quando admite um dos dois valores lógicos: Falso (F) ou Verdadeiro (V).
- Frases que não são proposições
- Pare!
- Quer uma xícara de café?
- Eu não estou bem certo se esta cor me agrada.
- Frases que são proposições
- A lua é o único satélite do planeta terra (V)
- A cidade de Salvador é a capital do estado do Amazonas (F)
- O numero 712 é ímpar (F)
- Raiz quadrada de dois é um número irracional (V)

## Composição de Proposições

- É possível construir proposições a partir de proposições já existentes. Este processo é conhecido por Composição de Proposições. Suponha que tenhamos duas proposições,
- A = "Maria tem 23 anos"
- B = "Maria é menor"

## Composição de Proposições

- "Maria não tem 23 anos" (não(A)) · "Maria não é menor' (não(B)) · "Maria tem 23 anos" e "Maria é menor" (A e B) · "Maria tem 23 anos" ou "Maria é menor" (A ou B) · "Maria não tem 23 anos" e "Maria é menor" (não(A) e B) · "Maria não tem 23 anos" ou "Maria é menor" (não(A) ou B) · "Maria tem 23 anos" ou "Maria não é menor" (A ou não(B)) · "Maria tem 23 anos" e "Maria não é menor" (A e não(B)) · Se "Maria tem 23 anos" então "Maria é menor" (se A então B) · Se "Maria não tem 23 anos" então "Maria é menor" (se não(A) então B) · "Maria não tem 23 anos" e "Maria é menor" (não(A) e B)

## Composição de Proposições

· "Maria não tem 23 anos" (nãoA) · "Maria não é menor' (não(B)) · "Maria tem 23 anos" e "Maria é menor" (A e B) · "Maria tem 23 anos" ou "Maria é menor" (A ou B) · "Maria não tem 23 anos" e "Maria é menor" (não(A) e B) · "Maria não tem 23 anos" ou "Maria é menor" (não(A) ou B) · "Maria tem 23 anos" ou "Maria não é menor" (A ou não(B)) · "Maria tem 23 anos" e "Maria não é menor" (A e não(B)) · Se "Maria tem 23 anos" então "Maria é menor" (se A então B) · Se "Maria não tem 23 anos" então "Maria é menor" (se não(A) então B) · "Maria não tem 23 anos" e "Maria é menor" (não(A) e B) Note que, para compor proposições usou-se os símbolos não ( negação ), e ( conjunção ), ou ( disjunção ), se então ( implicação ). São os chamados conectivos lógicos . Note, também, que usou-se um símbolo para representar uma proposição: C representa a proposição Maria tem 18 anos . Assim, não(B) representa Maria não é menor , uma vez que B representa Maria é menor .

## LÓGICA PROPOCIONAL

## Sintaxe

Baseado nos materiais do Prof. Alfio Martini

## Sintaxe

- Ao apresentarmos uma linguagem formal, precisamos fornecer os componentes básicos da linguagem, chamados de alfabeto, para em seguida fornecer as regras de formação da linguagem, também chamada de gramática.

## Sintaxe

- Na Lógica Proposicional, o alfabeto é constituído dos seguintes elementos:
- Um conjunto enumerável de símbolos atômicos para variáveis proposicionais, que representam as sentenças declarativas · {p,q,r,...}
- Símbolos para os conectivos lógicos e para os valores lógicos (verdadeiro e falso)
- Símbolos para agrupamentos via parênteses ( e )

| operador   | significado                      |
|------------|----------------------------------|
| L          | (bottom), constante para falso   |
| T          | (top), constante para verdadeiro |
|            | negacao, l nao                   |
| V          | conjuncao, e                     |
|            | disjuncao, ou                    |
|            | implicacao, se...entao...        |
|            | equivalencia, se e somente se    |

## Sintaxe

- Os elementos da linguagem da Lógica Proposicional são chamados de fórmulas
- O conjunto de fórmulas da Lógica Proposicional (chamado de fórmulas bem-formadas, representado pelo símbolo P  ) será definido por indução
- Base da indução: o conjunto já possui alguns elemento conhecidos
- Passo da indução: adiciona-se elementos ao conjunto de acordo com algumas regras

## Sintaxe

- Toda proposição atômica no conjunto Σ = {𝑝, 𝑞, 𝑟, … } é uma fórmula bem-formada, ou seja, {𝑝, 𝑞, 𝑟, … } ⊂ 𝑃 Σ

$$\frac { v \in \Sigma } { v \in P _ { \Sigma } } ( A T M )$$

- As constantes ⊥ e ⊤ estão em 𝑃Σ

$$\overline { \perp \in P _ { \Sigma } } \left ( C O N S T 1 \right )$$

$$\overline { T \in P _ { \Sigma } } \left ( C O N S T 2 \right )$$

## Sintaxe

- Se 𝜙 é uma fórmula bem-formada, então ¬𝜙 é uma fórmula bem-formada

$$\frac { \phi \in P _ { \Sigma } } { ( \neg \phi ) \in P _ { \Sigma } } ( N E G )$$

## Sintaxe

- Se 𝜙 e 𝜓 são fórmulas bem-formadas, então 𝜙 ∧ 𝜓 é uma fórmula bem-formada

$$\frac { \phi \in P _ { \Sigma } , \psi \in P _ { \Sigma } } { ( \phi \wedge \psi ) \in P _ { \Sigma } } ( E )$$

## Sintaxe

- Se 𝜙 e 𝜓 são fórmulas bem-formadas, então 𝜙 ∨ 𝜓 é uma fórmula bem-formada

$$\frac { \phi \in P _ { \Sigma } , \psi \in P _ { \Sigma } } { ( \phi \vee \psi ) \in P _ { \Sigma } } ( O U )$$

## Sintaxe

- Se 𝜙 e 𝜓 são fórmulas bem-formadas, então 𝜙 → 𝜓 é uma fórmula bem-formada

$$\frac { \phi \in P _ { \Sigma } , \psi \in P _ { \Sigma } } { ( \phi \rightarrow \psi ) \in P _ { \Sigma } } ( I M P )$$

## Sintaxe

- Se 𝜙 e 𝜓 são fórmulas bem-formadas, então 𝜙 ↔ 𝜓 é uma fórmula bem-formada

$$\frac { \phi \in P _ { \Sigma } , \psi \in P _ { \Sigma } } { ( \phi \leftrightarrow \psi ) \in P _ { \Sigma } } ( E Q U I )$$

## Sintaxe

## Formulas bem-formadas

$$\begin{array} { c } \ F o r m u l a s \ b e n { - i o r m a d a s } \\ ( p \nearrow q ) \\ ( ( \bot \vee q ) \rightarrow r ) \\ ( ( ( \neg q ) \vee ( \neg r ) ) \leftrightarrow ( p \nearrow s ) ) \\ ( p \rightarrow ( q \rightarrow r ) ) \\ \ F o r m u l a s \ m a l { - o r m a d a s } \end{array}$$

Formulas mal-formadas

$$\begin{matrix} p \rightarrow q \\ ( p \wedge q \neg ) \\ ( ( p \wedge q ) \vee - r ) \\ p \wedge q \end{matrix}$$