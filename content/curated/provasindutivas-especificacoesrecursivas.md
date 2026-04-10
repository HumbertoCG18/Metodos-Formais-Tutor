# Provas por Indução de Especificações Recursivas

## 1. Princípio da indução matemática

O princípio da indução matemática sobre os Naturais pode ser definido como: supondo que  $P(x)$  é um predicado sobre os números naturais, para provar:

$$\forall x \in \mathbb{N}. P(x) \quad (P(x) \text{ é verdadeiro para todo o natural } x)$$

é suficiente provar:

- Caso base:  $P(0)$ ; isto é, o predicado é verdadeiro para  $x$  com valor 0.
- Caso indutivo:  $\forall x \in \mathbb{N}. (P(x) \rightarrow P(x+1))$ ; isto é, para um natural arbitrário  $x_0$ , assumimos que  $P(x_0)$  é verdadeiro (isso é chamado de HI – Hipótese de Indução) e provamos que  $P(x_0 + 1)$  também é verdadeiro (isso é chamado de Passo da Indução).

| <i>indução sobre <math>\mathbb{N}</math></i> |               |                            |
|----------------------------------------------|---------------|----------------------------|
| $P(0)$                                       | $P(x_0)$ (HI) |                            |
|                                              | ...           | $(x_0 \text{ arbitrário})$ |
|                                              | $P(x_0 + 1)$  |                            |
| <hr/> $\forall x \in \mathbb{N}. P(x)$       |               | <i>IndNat</i>              |

## 2. Princípio da indução matemática generalizada

Muitas vezes queremos provar uma propriedade por indução sobre um determinado subconjunto dos números Naturais, ou um determinado subconjunto dos Inteiros que inclua o conjunto dos números Naturais. Dessa forma, o princípio da indução natural pode ser generalizado.

Seja  $m \in \mathbb{Z}$ . Suponha  $P(x)$  um predicado sobre  $\mathbb{Z}$ . Para provar:

$$\forall x \in \mathbb{Z}. (x \geq m \rightarrow P(x)) \quad (P(x) \text{ é verdadeiro para todo } x \geq m)$$

é suficiente provar:

- Caso base:  $P(m)$ ; isto é, o predicado é verdadeiro para  $x$  com valor  $m$ .
- Caso indutivo:  $\forall x \in \mathbb{Z}. ((x \geq m \wedge P(x)) \rightarrow P(x+1))$ ; isto é, para um inteiro arbitrário  $x_0 \geq m$ , assumimos que  $P(x_0)$  é verdadeiro (isso é chamado de HI – Hipótese de Indução) e provamos que  $P(x_0 + 1)$  também é verdadeiro (isso é chamado de Passo da Indução).

| <i>indução matemática generalizada</i>                                                                   |                                                      |                            |
|----------------------------------------------------------------------------------------------------------|------------------------------------------------------|----------------------------|
| $P(m)$                                                                                                   | $\frac{x_0 \geq m, P(x_0) \text{ (HI)}}{P(x_0 + 1)}$ | $(x_0 \text{ arbitrário})$ |
| $\forall x \in \mathbb{Z}. (x \geq m \rightarrow P(x))$ <span style="float: right;"><i>IndGen</i></span> |                                                      |                            |

## 3. Provas por indução de especificações recursivas

Muitas vezes queremos provar uma propriedade sobre uma especificação equacional recursiva de uma função. Em especial queremos demonstrar que a pós condição apresentada para uma determinada função está correta. O princípio da indução pode ser utilizado nestes casos. Os exemplos a seguir foram construídos sobre funções de números Naturais, Listas e Árvores Binárias (todos com base nas definições indutivas dos respectivos conjuntos).

### Exemplo 1:

Uma possível especificação equacional recursiva para a função potência de dois é:

$Pot2: \mathbb{N} \rightarrow \mathbb{N}$

*requer: true*

*garante:  $Pot2(n) = 2^n$*

$$Pot2(0) = 1 \quad (pot2\_1)$$

$$Pot2(n + 1) = 2 \times Pot2(n) \quad (pot2\_2)$$

Deseja-se provar a correção da pós condição, ou seja:

$$\forall n \in \mathbb{N}. Pot2(n) = 2^n$$

Da mesma forma, provar via indução nos Naturais a seguinte propriedade:

$$P(n) \triangleq Pot2(n) = 2^n$$

#### Caso base:

Demonstrar  $P(0)$ :

$$P(0) \triangleq Pot2(0) = 2^0$$

Passos da demonstração:

$$Pot2(0)$$

$$= 1 \quad (por \ pot2\_1)$$

$$= 2^0 \quad (por \ alg. \ arit.)$$

*q. e. d*

Caso indutivo:

Seja  $x_0 \in \mathbb{N}$  uma variável arbitrária.

Assumir por hipótese de indução que:

$$P(x_0) \triangleq Pot2(x_0) = 2^{x_0} \quad (HI)$$

Demonstrar  $P(x_0 + 1)$ :

$$P(x_0 + 1) \triangleq Pot2(x_0 + 1) = 2^{x_0+1} \quad (HI)$$

Passos da demonstração:

$$\begin{aligned} Pot2(x_0 + 1) &= 2 \times Pot2(x_0) && \text{(por pot2\_2)} \\ &= 2 \times 2^{x_0} && \text{(por HI)} \\ &= 2^{x_0+1} && \text{(por alg. arit.)} \end{aligned}$$

q. e. d.

### Exemplo 2:

Uma possível especificação equacional recursiva para o somatório

$$\sum_{k=l}^u 2k$$

é dada por:

$$Sum2k: \mathbb{N} \times \mathbb{N} \rightarrow \mathbb{N}$$

$$requer: l \leq u$$

$$garante: Sum2k(l, u) = \sum_{k=l}^u 2k$$

$$Sum2k(l, l) = 2 * l \quad (\text{sum2k\_1})$$

$$Sum2k(l, u) = 2 * u + sum2k(l, u - 1), \text{ se } l < u \quad (\text{sum2k\_2})$$

Estamos interessados em provar pelo princípio de indução que a especificação equacional recursiva corresponde a um somatório desejado. O somatório desejado é:

$$P(n) \triangleq Sum2k(0, n) = \sum_{k=0}^n 2k$$

Importante: neste exemplo, estamos interessados em provar uma determinada propriedade assumindo que a função já foi provada correta anteriormente!

Observe que muitas vezes a propriedade (e consequentemente a equação) que queremos demonstrar envolve o uso de funções com mais de um argumento. Nesse caso, a utilização da seguinte heurística é recomendada: “Caso a função possua mais de um argumento, realizar a indução no argumento de posição  $i$  se a função é definida por recursão no argumento de posição  $i$ ”. Assim, no caso de exemplo, a indução será no segundo argumento.

Caso base:

Demonstrar  $P(0)$ :

$$P(0) \triangleq \text{Sum2k}(0,0) = \sum_{k=0}^0 2k$$

Passos da demonstração:

$$\begin{aligned} \text{Sum2k}(0,0) &= 2 \times 0 \quad (\text{por sum2k\_1}) \\ &= \sum_{k=0}^0 2k \quad (\text{por definição do somatório}) \end{aligned}$$

*q. e. d.*

Caso indutivo:

Seja  $x_0 \in \mathbb{N}$  uma variável arbitrária.

Assumir como hipótese de indução (HI) que:

$$P(x_0) \triangleq \text{Sum2k}(0, x_0) = \sum_{k=0}^{x_0} 2k \quad (\text{HI})$$

Demonstrar  $P(x_0 + 1)$ :

$$P(x_0 + 1) \triangleq \text{Sum2k}(0, (x_0 + 1)) = \sum_{k=0}^{x_0+1} 2k$$

Passos da demonstração:

$$\begin{aligned} \text{Sum2k}(0, (x_0 + 1)) &= 2(x_0 + 1) + \text{Sum2k}(0, x_0) \quad (\text{por sum2k\_2}) \\ &= 2(x_0 + 1) + \sum_{k=0}^{x_0} 2k \quad (\text{por HI}) \\ &= \sum_{k=0}^{x_0} 2k + 2(x_0 + 1) \quad (\text{por alg. arit.}) \end{aligned}$$

$$= \sum_{k=0}^{x_0+1} 2k \quad (\text{por definição do somatório})$$

*q.e.d.*
