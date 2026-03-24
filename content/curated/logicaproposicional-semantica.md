# MÉTODOS FORMAIS

Prof. Júlio Machado

# LÓGICA PROPOSICIONAL

Semântica

Baseado nos materiais do Prof. Alfio Martini

#### Semântica

- O estudo da semântica da lógica proposicional consiste em atribuir valores verdade a fórmulas
- Na lógica clássica há apenas dois valores:
  - Verdadeiro V
  - Falso F

## Interpretações

- Os símbolos que não possuem significado fixo são chamados de variáveis proposicionais
- Uma interpretação I para um conjunto de variáveis proposicionais $\Sigma$ é uma função I:$\Sigma$→B, onde B={V,F}
- Exemplo:
  - Se  $\Sigma$ ={p,q}, então temos quatro interpretações possíveis:

$$\mathcal{I}_1 = \{ p \mapsto F, q \mapsto F \}$$

$$\mathcal{I}_2 = \{ p \mapsto F, q \mapsto V \}$$

$$\mathcal{I}_3 = \{ p \mapsto V, q \mapsto F \}$$

$$\mathcal{I}_4 = \{ p \mapsto V, q \mapsto V \}$$

## Semântica dos Operadores

 Os operadores proposicionais possuem um significado fixo, o qual pode ser definido através de uma tabelaverdade

# Semântica dos Operadores

| p | q | $\neg p$ | $p \wedge q$ | $p \lor q$ | $p\rightarrow q$ | $p \leftrightarrow q$ |
|---|---|----------|--------------|------------|------------------|-----------------------|
| V | V | F        | V            | V          | V                | V                     |
| V | F | F        | F            | V          | F                | F                     |
| F | V | V        | F            | V          | V                | F                     |
| F | F | V        | F            | F          | V                | V                     |

## Fórmulas e Interpretações

 Se n é o número de variáveis proposicionais em uma fórmula, então temos 2<sup>n</sup> interpretações ou linhas na tabela-verdade correspondente à fórmula

## Fórmulas e Interpretações

| p | q | r | $\neg p$ | $\neg p \rightarrow q$ | $(\neg p \rightarrow q) \lor r$ |
|---|---|---|----------|------------------------|---------------------------------|
| V | V | V | F        | V                      | V                               |
| V | V | F | F        | V                      | V                               |
| V | F | V | F        | V                      | V                               |
| V | F | F | F        | V                      | V                               |
| F | V | V | V        | V                      | V                               |
| F | V | F | V        | V                      | V                               |
| F | F | V | V        | F                      | V                               |
| F | F | F | V        | F                      | F                               |

#### Modelos

- Modelos são interpretações na qual uma fórmula (ou conjunto de fórmulas) é verdadeira (são verdadeiras)
- Uma interpretação I:$\Sigma$→B é um modelo para uma fórmula A$\in$P<sub>$\Sigma$</sub> se somente se [A]<sub>I</sub> = V (ou seja, o valor da fórmula nessa interpretação é verdadeira)
  - Nesse caso escrevemos  $I \models A$
- Uma interpretação I:$\Sigma$→B não é um modelo para uma fórmula A$\in$P<sub>$\Sigma$</sub> se somente se [A]<sub>I</sub> = F (ou seja, o valor da fórmula nessa interpretação é falsa)
  - Nesse caso escrevemos  $I \not\models A$

#### Modelos

- Uma interpretação I: $\Sigma \rightarrow B$  é um modelo para um conjunto de fórmulas  $\{A_1,...,A_n\}$  onde  $A_i \in P_\Sigma$  se somente se  $[A_i]_I = V$  para todo i=1,...,n
  - Nesse caso escrevemos  $I \models A_1, ..., A_n$
- Uma interpretação I:$\Sigma$→B não é um modelo para um conjunto de fórmulas {A<sub>1</sub>,...,A<sub>n</sub>} onde A<sub>i</sub>$\in$P<sub>$\Sigma$</sub> se somente se [A<sub>i</sub>]<sub>I</sub> = F para algum 1$\leq$i$\leq$n
  - Nesse caso escrevemos  $I \not\models A_1, ..., A_n$

#### Modelos

Sejam as seguintes interpretações:

$$I_1 = \{ p \mapsto V, q \mapsto F, r \mapsto V \}$$
  
$$I_2 = \{ p \mapsto F, q \mapsto F, r \mapsto F \}$$

Verificar (via tabela-verdade):

$$I1 \vDash (\neg p \to q) \lor r$$
$$I2 \nvDash (\neg p \to q) \lor r$$

Sejam as seguintes interpretações:

$$I_1 = \{ p \mapsto F, q \mapsto F \}$$
$$I_2 = \{ p \mapsto V, q \mapsto F \}$$

Verificar (via tabela-verdade):

$$I1 \vDash p \rightarrow q, \neg p \lor q$$
$$I2 \not\vDash p \rightarrow q, \neg p \lor q$$

## Classificação das Fórmulas

- Uma fórmula A é uma tautologia (ou válida) se e somente se toda interpretação I:$\Sigma$→B para A é modelo
  - Ou seja, para toda interpretação I, [A]<sub>I</sub>=V
  - Nesse caso escrevemos  $\models A$
- Uma fórmula A é uma contradição (ou inválida) se e somente se nenhuma interpretação I:$\Sigma$→B para A é modelo
  - Ou seja, para toda interpretação I, [A]<sub>I</sub>=F
  - Nesse caso escrevemos  $\not\models A$
- Uma fórmula A é <u>satisfatível</u> se e somente se existe ao menos uma interpretação I:$\Sigma$→B para A que é modelo
  - Ou seja, existe pelo menos uma interpretação I, [A]<sub>I</sub> = V

## Classificação das Fórmulas

- Verifique usando tabela-verdade:
  - P$\lor$$\neg$P é tautologia
  - P$\lor$Q é satisfatível
  - P$\land$$\neg$P é contradição

- Seja {A<sub>1</sub>,...,A<sub>n</sub>} um conjunto de fórmulas
- O conjunto de modelos de {A<sub>1</sub>,...,A<sub>n</sub>}, escrito mod({A<sub>1</sub>,...,A<sub>n</sub>}), é definido como o conjunto de \ninterpretações I:$\Sigma$→B tal que I é modelo para cada fórmula do conjunto {A<sub>1</sub>,...,A<sub>n</sub>}
  - Ou seja, os modelos de um conjunto de fórmulas são somente aquelas interpretações que satisfazem simultaneamente todas as fórmulas do conjunto

$$mod(\{A_1,\ldots,A_n\}) = \bigcap mod(A_i)$$

 Verifique usando tabelas-verdade quais os modelos de cada conjunto de fórmulas:

```
• mod(\{p, p \rightarrow q, q\})
```

- $mod(\{p, \neg p\})$
- $mod(\{p \rightarrow q, q\})$

- Um conjunto de fórmulas proposicionais {A<sub>1</sub>,...,A<sub>n</sub>} é
   consistente quando existe pelo menos uma interpretação
   I:$\Sigma$→B no conjunto de modelos mod({A<sub>1</sub>,...,A<sub>n</sub>}) para as
   fórmulas
- Um conjunto de fórmulas proposicionais {A<sub>1</sub>,...,A<sub>n</sub>} é
   inconsistente quando não existe uma interpretação I:$\Sigma$→B
   no conjunto de modelos mod({A<sub>1</sub>,...,A<sub>n</sub>}) para as fórmulas,
   ou seja, mod({A<sub>1</sub>,...,A<sub>n</sub>})=$\emptyset$

 Verifique usando tabelas-verdade quais dos conjuntos de fórmulas abaixo são consistente e quais são inconsistentes:

```
• \{p \rightarrow q, \neg q\}
• \{p \rightarrow q, \neg q \lor r, p \land \neg r\}
• \{(p \lor q) \rightarrow r, \neg((\neg p \land \neg q) \lor r)\}
```

## Consequência Lógica/Semântica

- Diz que uma fórmula proposicional B é consequência lógica/semântica de um conjunto de fórmulas proposicionais  $\{A_1,...,A_n\}$  se e somente se  $mod(\{A_1,...,A_n\}) \subseteq mod(\{B\})$ 
  - Nesse caso escrevemos  $A_1, ..., A_n \models B$
  - Ou seja, se para todos os valores nos quais todas as fórmulas de {A<sub>1</sub>,...,A<sub>n</sub>} têm valor V, B também tem valor V

# Consequência Lógica/Semântica

• 
$$\neg p \rightarrow q, \neg q \models p$$

| p | q | $\neg p$ | $\neg p \rightarrow q$ | $\neg q$ |
|---|---|----------|------------------------|----------|
| V | V | F        | V                      | F        |
| V | F | F        | V                      | V        |
| F | V | V        | V                      | F        |
| F | F | V        | F                      | V        |

- $mod(\{\neg p \to q\}) = \{I1, I2, I3\}$
- $mod(\{\neg q\}) = \{I2, I4\}$
- $mod(\{\neg p \rightarrow q\}) \cap mod(\{\neg q\}) = \{I2\}$
- $mod(\{p\}) = \{I1, I2\}$
- $\{I2\} \subseteq \{I1, I2\}$ , logo, é consequência semântica

## Conjectura e Consequência Lógica

 Uma conjectura é <u>válida</u> se e somente se a conclusão é consequência lógica/semântica das premissas

## Teoremas Importantes

- Tautologia e Consequência Semântica:
  - Seja A uma fórmula da Lógica Proposicional, então A é uma tautologia se e somente se  $\models A$
- Teorema da Consequência:
  - Sejam A<sub>1</sub>,...,A<sub>n</sub> e B fórmulas da Lógica Proposicional, então temos

$$A_1, ..., A_n \models B \ sse \ A_1 \land \cdots \land A_n \rightarrow B \ \'e \ uma \ tautologia$$
  
 $A_1, ..., A_n \models B \ sse \ A_1 \land \cdots \land A_n \land \neg B \ \'e \ uma \ contradição$   
 $A_1, ..., A_n \models B \ sse \ \{A_1, ..., A_n, \neg B\} \ \'e \ inconsistente$ 

## Equivalências

- O conceito de equivalência entre fórmulas permite a abstração de certas diferenças sintáticas entre as fórmulas
- Sejam A e B duas fórmulas da Lógica Proposicional
- Diz-se que <u>A e B são equivalentes</u>, denotado A$\equiv$B, se e somente se mod({A})=mod({B})

## Equivalências

• Mostre que  $\neg p \lor q \equiv p \rightarrow q$ 

| p | q | $\neg p$ | $\neg p \lor q$ | $\boldsymbol{p} \to \boldsymbol{q}$ |
|---|---|----------|-----------------|-------------------------------------|
| V | V | F        | V               | V                                   |
| V | F | F        | F               | F                                   |
| F | V | V        | V               | V                                   |
| F | F | V        | V               | V                                   |

A equivalência está correta pois

$$mod(\{\neg p \lor q\}) = \{I_1, I_3, I_4\} = mod(\{p \to q\})$$

# Equivalências

• Mostre que  $p \rightarrow q \equiv \neg q \rightarrow \neg p$ 

## Teoremas Importantes

- Equivalência e Consequência Semântica:
  - Sejam A e B fórmulas da Lógica Proposicional; então A$\equiv$B
  - se e somente se  $A \models B \in B \models A$
  - se e somente se  $A \leftrightarrow B$  é uma tautologia
