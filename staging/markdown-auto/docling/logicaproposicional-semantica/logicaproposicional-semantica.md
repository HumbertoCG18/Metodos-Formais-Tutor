## MÉTODOS FORMAIS

Prof. Júlio Machado

## LÓGICA PROPOSICIONAL

## Semântica

Baseado nos materiais do Prof. Alfio Martini

## Semântica

- O estudo da semântica da lógica proposicional consiste em atribuir valores verdade a fórmulas
- Na lógica clássica há apenas dois valores:
- Verdadeiro - V
- Falso - F

## Interpretações

- Os símbolos que não possuem significado fixo são chamados de variáveis proposicionais
- Uma interpretação I para um conjunto de variáveis proposicionais  é uma função I: → B, onde B={V,F}
- Exemplo:
- Se  ={p,q}, então temos quatro interpretações possíveis:

$$\mathcal { I } _ { 1 } = \{ p \mapsto F , q \mapsto F \} \\ \mathcal { I } _ { 2 } = \{ p \mapsto F , q \mapsto V \} \\ \mathcal { I } _ { 3 } = \{ p \mapsto V , q \mapsto F \} \\ \mathcal { I } _ { 4 } = \{ p \mapsto V , q \mapsto V \}$$

## Semântica dos Operadores

- Os operadores proposicionais possuem um significado fixo, o qual pode ser definido através de uma tabelaverdade

## Semântica dos Operadores

| 𝒑   | 𝒒   | ¬𝒑   | 𝒑 ∧ 𝒒   | 𝒑 ∨ 𝒒   | 𝒑→𝒒   | 𝒑↔𝒒   |
|-----|-----|------|---------|---------|-------|-------|
| V   | V   | F    | V       | V       | V     | V     |
| V   | F   | F    | F       | V       | F     | F     |
| F   | V   | V    | F       | V       | V     | F     |
| F   | F   | V    | F       | F       | V     | V     |

## Fórmulas e Interpretações

- Se n é o número de variáveis proposicionais em uma fórmula, então temos 2 n interpretações ou linhas na tabela-verdade correspondente à fórmula

## Fórmulas e Interpretações

| 𝒑   | 𝒒   | 𝒓   | ¬𝒑   | ¬𝒑 → 𝒒   | (¬𝒑→ 𝒒) ∨ 𝒓   |
|-----|-----|-----|------|----------|---------------|
| V   | V   | V   | F    | V        | V             |
| V   | V   | F   | F    | V        | V             |
| V   | F   | V   | F    | V        | V             |
| V   | F   | F   | F    | V        | V             |
| F   | V   | V   | V    | V        | V             |
| F   | V   | F   | V    | V        | V             |
| F   | F   | V   | V    | F        | V             |
| F   | F   | F   | V    | F        | F             |

## Modelos

- Modelos são interpretações na qual uma fórmula (ou conjunto de fórmulas) é verdadeira (são verdadeiras)
- Uma interpretação I: → B é um modelo para uma fórmula A  P  se somente se [A] I = V (ou seja, o valor da fórmula nessa interpretação é verdadeira)
- Nesse caso escrevemos 𝐼 ⊨ 𝐴
- Uma interpretação I: → B não é um modelo para uma fórmula A  P  se somente se [A] I = F (ou seja, o valor da fórmula nessa interpretação é falsa)
- Nesse caso escrevemos 𝐼 ⊭ 𝐴

## Modelos

- Uma interpretação I: → B é um modelo para um conjunto de fórmulas {A 1 ,...,A n } onde A i  P  se somente se [A i ] I = V para todo i=1,...,n
- Nesse caso escrevemos 𝐼 ⊨ 𝐴1 , … , 𝐴𝑛
- Uma interpretação I: → B não é um modelo para um conjunto de fórmulas {A 1 ,...,A n } onde A i  P  se somente se [A i ] I = F para algum 1  i  n
- Nesse caso escrevemos 𝐼 ⊭ 𝐴1 , … , 𝐴𝑛

## Modelos

- Sejam as seguintes interpretações:

$$I _ { 1 }$$

$$I _ { 1 } & = \{ p \mapsto V , q \mapsto F , r \mapsto V \} \\ I _ { 2 } & = \{ p \mapsto F , q \mapsto F , r \mapsto F \} \\$$

- Verificar (via tabela-verdade):

$$I 1 \models ( \neg p \to q ) \vee r$$

$$I 2 \neq ( \neg p \to q ) \vee r$$

- Sejam as seguintes interpretações:

$$I _ { 1 } & = \{ p \mapsto F , q \mapsto F \} \\ I _ { 2 } & = \{ p \mapsto V , q \mapsto F \} \\$$

- Verificar (via tabela-verdade):

$$I 1 \equiv p \rightarrow q , \neg p \vee q$$

$$I 2 \neq p \rightarrow q , \neg p \vee q$$

## Classificação das Fórmulas

- Uma fórmula A é uma tautologia (ou válida) se e somente se toda interpretação I: → B para A é modelo
- Ou seja, para toda interpretação I, [A] I=V
- Nesse caso escrevemos ⊨ 𝐴
- Uma fórmula A é uma contradição (ou inválida) se e somente se nenhuma interpretação I: → B para A é modelo
- Ou seja, para toda interpretação I, [A] I=F
- Nesse caso escrevemos ⊭ 𝐴
- Uma fórmula A é satisfatível se e somente se existe ao menos uma interpretação I: → B para A que é modelo
- Ou seja, existe pelo menos uma interpretação I, [A] I = V

## Classificação das Fórmulas

- Verifique usando tabela-verdade:
- P  P é tautologia
- P  Q é satisfatível
- P  P é contradição

## Classificação de Conjunto de Fórmulas

- Seja {A 1 ,...,A n } um conjunto de fórmulas
- O conjunto de modelos de {A 1 ,...,A n }, escrito mod ({A 1 ,...,A n }), é definido como o conjunto de interpretações I: → B tal que I é modelo para cada fórmula do conjunto {A 1 ,...,A n }
- Ou seja, os modelos de um conjunto de fórmulas são somente aquelas interpretações que satisfazem simultaneamente todas as fórmulas do conjunto

$$m o d ( \{ A _ { 1 } , \dots , A _ { n } \} ) = \bigcap m o d ( A _ { i } )$$

## Classificação de Conjunto de Fórmulas

- Verifique usando tabelas-verdade quais os modelos de cada conjunto de fórmulas:
- 𝑚𝑜𝑑({𝑝,𝑝 → 𝑞, 𝑞})
- 𝑚𝑜𝑑({𝑝,¬𝑝})
- 𝑚𝑜𝑑({𝑝 → 𝑞,𝑞})

## Classificação de Conjunto de Fórmulas

- Um conjunto de fórmulas proposicionais {A 1 ,...,A n } é consistente quando existe pelo menos uma interpretação I: → B no conjunto de modelos mod ({A 1 ,...,A n }) para as fórmulas
- Um conjunto de fórmulas proposicionais {A 1 ,...,A n } é inconsistente quando não existe uma interpretação I: → B no conjunto de modelos mod ({A 1 ,...,A n }) para as fórmulas, ou seja, mod ({A 1 ,...,A n })= 

## Classificação de Conjunto de Fórmulas

- Verifique usando tabelas-verdade quais dos conjuntos de fórmulas abaixo são consistente e quais são inconsistentes:
- 𝑝 → 𝑞, ¬𝑞 · {𝑝 → 𝑞, ¬𝑞 ∨ 𝑟, 𝑝 ∧ ¬𝑟} · {(𝑝 ∨ 𝑞) → 𝑟, ¬((¬𝑝 ∧ ¬𝑞) ∨ 𝑟)}

## Consequência Lógica/Semântica

- Diz que uma fórmula proposicional B é consequência lógica/semântica de um conjunto de fórmulas proposicionais {A 1 ,...,A n } se e somente se 𝑚𝑜𝑑({𝐴1,…,𝐴𝑛}) ⊆ 𝑚𝑜𝑑({𝐵})
- Nesse caso escrevemos 𝐴1, … , 𝐴𝑛 ⊨ 𝐵
- Ou seja, se para todos os valores nos quais todas as fórmulas de {A 1 ,...,A n } têm valor V, B também tem valor V

## Consequência Lógica/Semântica

$$\circ \neg p \to q , \neg q \models p$$

| 𝒑   | 𝒒   | ¬𝑝   | ¬𝑝 →𝑞   | ¬𝑞   |
|-----|-----|------|---------|------|
| V   | V   | F    | V       | F    |
| V   | F   | F    | V       | V    |
| F   | V   | V    | V       | F    |
| F   | F   | V    | F       | V    |

- 𝑚𝑜𝑑 ¬𝑝 → 𝑞 = {𝐼1, 𝐼2, 𝐼3}
- 𝑚𝑜𝑑 ¬𝑞 = I2, I4
- 𝑚𝑜𝑑 ¬𝑝 → 𝑞 ∩𝑚𝑜𝑑 ¬𝑞 = {𝐼2}
- 𝑚𝑜𝑑 𝑝 = {𝐼1, 𝐼2}
- 𝐼2 ⊆ {𝐼1, 𝐼2} , logo, é consequência semântica

## Conjectura e Consequência Lógica

- Uma conjectura é válida se e somente se a conclusão é consequência lógica/semântica das premissas

## Teoremas Importantes

- Tautologia e Consequência Semântica:
- Seja A uma fórmula da Lógica Proposicional, então A é uma tautologia se e somente se
- Teorema da Consequência:
- Sejam A 1 ,...,A n e B fórmulas da Lógica Proposicional, então temos

𝐴1, … , 𝐴𝑛 ⊨ 𝐵 𝑠𝑠𝑒 𝐴1 ∧ ⋯∧ 𝐴𝑛 → 𝐵 é 𝑢𝑚𝑎 𝑡𝑎𝑢𝑡𝑜𝑙𝑜𝑔𝑖𝑎 𝐴1, … , 𝐴𝑛 ⊨ 𝐵 𝑠𝑠𝑒 𝐴1 ∧ ⋯∧ 𝐴𝑛 ∧ ¬𝐵 é 𝑢𝑚𝑎 𝑐𝑜𝑛𝑡𝑟𝑎𝑑𝑖çã𝑜 𝐴1, … , 𝐴𝑛 ⊨ 𝐵 𝑠𝑠𝑒 {𝐴1 , … , 𝐴 𝑛, ¬𝐵} é 𝑖𝑛𝑐𝑜𝑛𝑠𝑖𝑠𝑡𝑒𝑛𝑡𝑒

## Equivalências

- O conceito de equivalência entre fórmulas permite a abstração de certas diferenças sintáticas entre as fórmulas
- Sejam A e B duas fórmulas da Lógica Proposicional
- Diz-se que A e B são equivalentes, denotado A  B, se e somente se mod ({A})= mod ({B})

## Equivalências

- Mostre que ¬𝑝 ∨ 𝑞 ≡ 𝑝 → 𝑞
- A equivalência está correta pois

| 𝒑   | 𝒒   | ¬𝒑   | ¬𝒑∨𝒒   | 𝒑→𝒒   |
|-----|-----|------|--------|-------|
| V   | V   | F    | V      | V     |
| V   | F   | F    | F      | F     |
| F   | V   | V    | V      | V     |
| F   | F   | V    | V      | V     |

$$\ m o d ( \{ - \uparrow p \vee q \} ) = \{ I _ { 1 } , I _ { 3 } , I _ { 4 } \} = m o d ( \{ p \to q \} )$$

## Equivalências

- Mostre que 𝑝 → 𝑞 ≡ ¬𝑞 → ¬𝑝

## Teoremas Importantes

- Equivalência e Consequência Semântica:
- Sejam A e B fórmulas da Lógica Proposicional; então A  B
- se e somente se 𝐴 ⊨ 𝐵 e 𝐵 ⊨ 𝐴
- se e somente se 𝐴 ↔ 𝐵 é uma tautologia