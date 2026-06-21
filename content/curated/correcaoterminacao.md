<!-- EXEC_SUMMARY_START -->
## Sumário
> *Leia antes de varrer o arquivo. Vá direto à seção relevante para a pergunta do aluno.*

- **1. Correção**
  - Correção parcial:
  - Correção total:
- **2. Relações e ordens**
- **3. Ordens bem-fundamentadas**
- **4. Exemplos e construção de ordens bem-fundamentadas**
- **5. Prova (informal) de terminação**

<!-- EXEC_SUMMARY_END -->
{0}------------------------------------------------

# Correção de Algoritmos

## 1. Correção

Um passo importante no trabalho com algoritmos é ser capaz de argumentar sobre sua correção. Deve-se salientar de antemão que não é razoável falar formalmente que “um algoritmo está correto”. A correção de um algoritmo deve ser dada através da relação com sua especificação, ou seja, diz-se que “o algoritmo está correto com relação à especificação das pré e pós condições e invariantes”.

Existem duas definições para correção:

- Correção parcial;
- Correção total.

### Correção parcial:

Seja um algoritmo  $A$  com pré-condição  $P$  e pós-condição  $Q$ , diz-se que  $(|P|)A(|Q|)$  é válida sob o critério de correção parcial se e somente se toda computação terminante que começa em um estado que satisfaz  $P$  termina em um estado que satisfaz  $Q$ .

(observação: essa notação se deve ao trabalho de Hoare na prova de correção de algoritmos e programas sequenciais, e é chamada de *Tripla de Hoare*).

O algoritmo  $A$  é parcialmente correto com respeito a  $P$  e  $Q$  se e somente se para todos os valores do domínio do algoritmo:

- **SE** a pré-condição é verdadeira
- **E** o algoritmo termina,
- **Então** a pós-condição é verdadeira.

Observe que a correção parcial não implica que um algoritmo termine, pois a definição é uma implicação lógica (“se o algoritmo termina, então a pós-condição é verdadeira”) e, pelo significado dessa operação lógica, se o antecedente é falso, toda a implicação é verdadeira.

### Correção total:

Seja um algoritmo  $A$  com pré-condição  $P$  e pós-condição  $Q$ , diz-se que  $[P]A[Q]$  é válida sob o critério de correção total se e somente se toda computação que começa em um estado que satisfaz  $P$  termina e o estado resultante também satisfaz  $Q$ .

{1}------------------------------------------------

O algoritmo  $A$  é totalmente correto com respeito a  $P$  e  $Q$  se e somente se para todos os valores do domínio do algoritmo:

- **SE** a pré-condição é verdadeira,
- **Então** o algoritmo termina
- **E** a pós-condição é verdadeira.

Observe que o conceito de correção total implica na necessidade de mostrar que o programa termina. A prova de terminação de programas não é algo simples e tem implicações teóricas importantes na Computação. Para compreender uma prova de terminação é necessário recorrer-se aos conceitos de ordem e ordem bem-fundamentada.

## 2. Relações e ordens

Uma relação binária  $R$  entre dois conjuntos  $A$  e  $B$ , escrita  $R: A \leftrightarrow B$ , é um subconjunto qualquer do produto cartesiano  $A \times B$ .

Uma relação binária  $\preceq$  em um conjunto  $D$  ( $\preceq: D \leftrightarrow D$ ) é chamada de ordem parcial ampla se e somente se a relação é:

- Reflexiva:  $\forall d \in D. d \preceq d$
- Antissimétrica:  $\forall d, d' \in D. d \preceq d' \wedge d' \preceq d \Rightarrow d = d'$
- Transitiva:  $\forall d, d', d'' \in D. d \preceq d' \wedge d' \preceq d'' \Rightarrow d \preceq d''$

Neste caso, o par  $(D, \preceq)$  é chamado de conjunto parcialmente ordenado ou poset reflexivo.

São exemplos de ordens parciais reflexivas:

- $A = \{1,2,3\}$  e  $R = \{(1,1), (2,2), (3,3), (1,2), (1,3), (2,3)\} \equiv (A, \leq)$
- $B = \{1,2,3,4,6,12\}$  e  $R = \{(x,y)/x \text{ divide } y\}$
- $(\mathbb{N}, \leq)$

Uma relação binária  $<$  em um conjunto  $D$  ( $<: D \leftrightarrow D$ ) é chamada de ordem parcial estrita se e somente se a relação é:

- Irreflexiva:  $\forall d \in D. \neg(d < d)$
- Antissimétrica:  $\forall d, d' \in D. d < d' \wedge d' < d \Rightarrow d = d'$
- Transitiva:  $\forall d, d', d'' \in D. d < d' \wedge d' < d'' \Rightarrow d < d''$

Neste caso, o par  $(D, <)$  é chamado de conjunto parcialmente ordenado ou poset irreflexivo.

São exemplos de ordens parciais irreflexivas:

- $(2^{\{1,2\}}, \subset)$
- $(\mathbb{N}, <)$

Um poset  $(D, <)$  é chamado de ordem linear ou ordem total se todos seus elementos são comparáveis entre si, ou seja,  $\forall d, d' \in D. d < d' \vee d' < d$ .

{2}------------------------------------------------

São exemplos de ordens totais:

- a)  $A = \{1,3,9,45\}$  e  $R = \{(x,y)/x \text{ divide } y\}$
- b)  $(\mathbb{N}, \leq)$
- c)  $(\mathbb{N}, <)$

Se  $x < y$  em um poset  $(D, <)$  então dizemos que  $x$  é o predecessor de  $y$  ou que  $y$  é o sucessor de  $x$ . Se o conjunto de elementos definido por  $\{z \in D \mid x < z < y\}$  for vazio, diz-se que  $x$  é o predecessor imediato de  $y$  ou que  $y$  é o sucessor imediato de  $x$ .

Um elemento  $s$  em um subconjunto não-vazio  $S$  de um poset  $(D, <)$  é chamado de mínimo de  $S$  se  $s$  não possui predecessores. Um elemento mínimo  $s$  em um subconjunto não-vazio  $S$  de um poset  $(D, <)$  é chamado de o menor elemento de  $S$  se  $s$  precede todos os elementos de  $S$ , ou seja,  $\forall y \in S. s < y$ .

Por exemplo, no poset  $(\mathbb{N}, \text{divide})$ :

- a)  $\{2,4,5,10\}$  possui elementos mínimos 2 e 5
- b)  $\{2,4,12\}$  possui menor elemento 2

Um elemento  $s$  em um subconjunto  $S$  de um poset  $(D, <)$  é chamado de máximo de  $S$  se  $s$  não possui sucessores. Um elemento máximo  $s$  em um subconjunto  $S$  de um poset  $(D, <)$  é chamado de o maior elemento de  $S$  se  $s$  sucede todos os elementos de  $S$ , ou seja,  $\forall y \in S. y < s$ .

Por exemplo, no poset  $(\mathbb{N}, \text{divide})$ :

- a)  $\{2,4,5,10\}$  possui elementos máximos 4 e 10
- b)  $\{2,4,12\}$  possui maior elemento 12

## 3. Ordens bem-fundamentadas

Um subconjunto  $C$  de uma ordem parcial sobre  $D$  é chamado de cadeia se todos os elementos de  $C$  são comparáveis entre si.

Uma sequência  $d_0, d_1, d_2, \dots$  de elementos de  $(D, <)$  é chamada de cadeia descendente se  $d_0 > d_1 > d_2 > \dots$

São exemplos de cadeias descendentes:

- a)  $4 > 2 > 0 > -2 > -4 > \dots$  no poset  $(\mathbb{Z}, <)$
- b)  $\{1,2\} \supset \{1\} \supset \emptyset$  no poset  $(2^{\{1,2\}}, \subset)$

Um poset  $(D, <)$  é chamado de bem-fundamentado se cada cadeia descendente de elementos é finita.

Exemplos de ordens bem-fundamentadas:

- a)  $(\mathbb{N}, <)$
- b)  $(2^{\{1,2\}}, \subset)$
- c)  $(2^A, \subset)$  para  $A$  um conjunto finito

{3}------------------------------------------------

Exemplos de ordens que não são bem-fundamentadas:

- a)  $(\mathbb{Z}, <)$
- b)  $(2^A, \subset)$  para  $A$  um conjunto infinito

Mas como saber se um determinado poset é bem fundamentado? Alguns teoremas podem ajudar.

Teorema: Um poset  $(D, <)$  é bem-fundamentado se e somente se todo subconjunto não vazio de  $D$  tem um elemento mínimo.

## 4. Exemplos e construção de ordens bem-fundamentadas

Ordem lexicográfica sobre  $\mathbb{N}^k$ :

A ordenação total  $(\mathbb{N}^k, <)$  pode ser usada para criar a chamada ordem lexicográfica sobre uma relação  $n$ -ária  $\mathbb{N}^k$ .

Define-se o poset  $(\mathbb{N}^k, <)$  tal que  $(x_1, \dots, x_k) < (y_1, \dots, y_k)$  se e somente se existe  $j \geq 1$  tal que  $x_j < y_j$  e para todo  $i < j$  tem-se  $x_i = y_i$ .

Ordem bem-fundamentada sobre conjuntos:

Seja  $S$  um conjunto e  $f: S \rightarrow \mathbb{N}$  uma função total. Constrói-se um poset bem-fundamentado  $(S, <)$  onde  $x < y \triangleq f(x) < f(y)$ .

São exemplos de ordens bem-fundamentadas sobre conjuntos:

- a) Qualquer conjunto de listas é bem-fundamentado, onde  $L < L' \triangleq tamanho(L) < tamanho(L')$
- b) Qualquer conjunto de árvores é bem-fundamentado, onde  $T < T' \triangleq numNodos(T) < numNodos(T')$

## 5. Prova (informal) de terminação

Ordens bem-fundamentadas são comumente utilizadas na Ciência da Computação como um meio de provar que uma determinada computação irá terminar. A ideia geral é assinalar um determinado valor a cada passo sucessivo de uma computação (laço de repetição ou recursão) tal que o valor sempre decresça a cada passo. A expressão que define esse valor é chamada de variante. Caso os valores sejam de um domínio sobre um poset bem-ordenado, então a computação não pode ocorrer infinitamente, já que é garantido que as cadeias de valores decrescentes sempre terminam.

Para um algoritmo iterativo, utiliza-se a seguinte técnica:

- Escolhe-se uma ordem bem-fundamentada  $(D, <)$ ;
- Define-se uma variante como uma função (uma expressão sobre as variáveis do programa)  
 $var: estado \rightarrow D$ ;

{4}------------------------------------------------

- Prova-se que sempre que a invariante e a condição do laço são verdadeiras para um estado  $s$ , então a variante estritamente decresce no próximo estado, ou seja,  $var(s) > var(s')$ , onde  $s'$  representa o próximo estado da computação.

No exemplo que segue, retomamos o algoritmo para o cálculo eficiente para computar a potência de um número, ou seja,  $x^n$ . O algoritmo utiliza uma técnica conhecida como “exponenciação rápida” ou “exponenciação por quadrados”. O algoritmo iterativo para o cálculo:

```

begin Potencia(a,b)
    <true>
    x=a;
    y=1;
    z=b;
    loop
        < $x \geq 0, y > 0, z \geq 0$ >
        < $y * x^z = a^b$ >
        exit when (z=0)
        r=resto(z,2);
        z=quociente(z,2);
        if (r=1) then y=x*y;
        x=x*x;
    end loop
    return y;
    < $y = a^b$ >
end

```

Estamos interessados na prova de terminação, já que ele apresenta um laço de repetição.

A prova de terminação do algoritmo envolve encontrar um valor Natural (lembre-se que o poset  $(\mathbb{N}, <)$  é bem-ordenado) para cada estado da computação e mostrar que a sequência de estados é uma cadeia decrescente desse poset.

Definindo-se o estado como sendo  $s \triangleq \mathbb{N} \times \mathbb{N} \times \mathbb{N} = \langle x, y, z \rangle$  e o estado inicial  $\langle a, 1, b \rangle$ . As seguintes sequências de estados demonstram os passos de computação para o cálculo de  $2^4$  e  $2^3$ :

| Estados                                                            | Invariante              |
|--------------------------------------------------------------------|-------------------------|
| $s_0 = \langle 2, 1, 4 \rangle = \langle x_0, y_0, z_0 \rangle$    | $1 \times 2^4 = 2^4$    |
| $s_1 = \langle 4, 1, 2 \rangle = \langle x_1, y_1, z_1 \rangle$    | $1 \times 4^2 = 2^4$    |
| $s_2 = \langle 16, 1, 1 \rangle = \langle x_2, y_2, z_2 \rangle$   | $1 \times 16^1 = 2^4$   |
| $s_3 = \langle 256, 16, 0 \rangle = \langle x_3, y_3, z_3 \rangle$ | $16 \times 256^0 = 2^4$ |

| Estados                                                          | Invariante            |
|------------------------------------------------------------------|-----------------------|
| $s_0 = \langle 2, 1, 3 \rangle = \langle x_0, y_0, z_0 \rangle$  | $1 \times 2^3 = 2^3$  |
| $s_1 = \langle 4, 2, 1 \rangle = \langle x_1, y_1, z_1 \rangle$  | $2 \times 4^1 = 2^3$  |
| $s_2 = \langle 16, 8, 0 \rangle = \langle x_2, y_2, z_2 \rangle$ | $8 \times 16^0 = 2^3$ |

{5}------------------------------------------------

Observe que a cada passo, a **variável  $z$  define uma variante** que é estritamente decrescente e, portanto, pelo princípio das ordens bem-fundamentadas, o laço sempre irá terminar.

Considere agora o seguinte algoritmo para o cálculo iterativo de potências:

```
begin Potencia(a,b)
  <true>
  i=0;
  y=1;
  loop
    < $i \geq 0 \wedge i \leq b \wedge y = a^i$ >
    exit when <i=b>
    y=y*a;
    i=i+1;
  end loop
  return y;
  < $y = a^b$ >
end
```

**Uma variante para a prova de terminação pode ser dada pela expressão  $b - i$ .** Observe que quando a invariante e a condição de execução (não de saída) do laço são verdadeiras,  $b - i > 0$  e, cada execução do laço, incrementa o valor de  $i$  e, portanto, decrementa o valor de  $b - i$ . Como  $(\mathbb{N}, <)$  é bem-ordenado, a terminação está garantida.