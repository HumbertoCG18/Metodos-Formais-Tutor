## Provas por Indução de Especificações Recursivas

## 1. Princípio da indução matemática

O princípio da indução matemática sobre os Naturais pode ser definido como: supondo que P(x) é um predicado sobre os números naturais, para provar:

$$\forall x \in \mathbb{N}. P(x)$$
 (P(x) é verdadeiro para todo o natural x)

é suficiente provar:

- Caso base: P(0); isto é, o predicado é verdadeiro para x com valor 0.
- Caso indutivo:  $\forall x \in \mathbb{N}. (P(x) \to P(x+1))$ ; isto é, para um natural arbitrário  $x_0$ , assumimos que  $P(x_0)$  é verdadeiro (isso é chamado de HI Hipótese de Indução) e provamos que  $P(x_0+1)$  também é verdadeiro (isso é chamado de Passo da Indução).

$$\frac{ indução\ sobre\ \mathbb{N} }{ P(0) \begin{matrix} P(x_0) & (HI) \\ \dots \\ P(x_0+1) \end{matrix} } (x_0\ arbitrário) \\ \hline$$

# 2. Princípio da indução matemática generalizada

Muitas vezes queremos provar uma propriedade por indução sobre um determinado subconjunto dos números Naturais, ou um determinado subconjunto dos Inteiros que inclua o conjunto dos números Naturais. Dessa forma, o princípio da indução natural pode ser generalizado.

Seja  $m \in \mathbb{Z}$ . Suponha P(x) um predicado sobre  $\mathbb{Z}$ . Para provar:

$$\forall x \in \mathbb{Z}. (x \ge m \to P(x)) (P(x) \text{ \'e verdadeiro para todo } x \ge m)$$

é suficiente provar:

- Caso base: P(m); isto é, o predicado é verdadeiro para x com valor m.
- Caso indutivo:  $\forall x \in \mathbb{Z}. \left(\left(x \geq m \land P(x)\right) \rightarrow P(x+1)\right)$ ; isto é, para um inteiro arbitrário  $x_0 \geq m$ , assumimos que  $P(x_0)$  é verdadeiro (isso é chamado de HI Hipótese de Indução) e provamos que  $P(x_0+1)$  também é verdadeiro (isso é chamado de Passo da Indução).

<!-- IMAGE_DESCRIPTION: provasindutivas-especificacoesrecursivas-_page_1_Figure_0.png -->
<!-- Tipo: genérico -->
> **[Descrição de imagem]** A imagem apresenta um diagrama estruturado que ilustra o princípio da indução matemática generalizada.
<!-- /IMAGE_DESCRIPTION -->
![](content/images/provasindutivas-especificacoesrecursivas-_page_1_Figure_0.png)

## 3. Provas por indução de especificações recursivas

Muitas vezes queremos provar uma propriedade sobre uma especificação equacional recursiva de uma função. Em especial queremos demonstrar que a pós condição apresentada para uma determinada função está correta. O princípio da indução pode ser utilizado nestes casos. Os exemplos a seguir foram construídos sobre funções de números Naturais, Listas e Árvores Binárias (todos com base nas definições indutivas dos respectivos conjuntos).

### Exemplo 1:

Uma possível especificação equacional recursiva para a função potência de dois é:

 $Pot2: \mathbb{N} \to \mathbb{N}$ 

requer: true

 $garante: Pot2(n) = 2^n$ 

$$Pot2(0) = 1 (pot2_1)$$

$$Pot2(n+1) = 2 \times Pot2(n)$$
 (pot2\_2)

Deseja-se provar a correção da pós condição, ou seja:

$$\forall n \in \mathbb{N}. Pot2(n) = 2^n$$

Da mesma forma, provar via indução nos Naturais a seguinte propriedade:

$$P(n) \triangleq Pot2(n) = 2^n$$

#### Caso base:

Demonstrar P(0):

$$P(0) \triangleq Pot2(0) = 2^{0}$$

Passos da demonstração:

*Pot*2(0)

$$= 1$$
 (por pot2\_1)

$$= 2^0$$
 (por alg. arit.)

q.e.d

## Caso indutivo:

Seja  $x_0 \in \mathbb{N}$  uma variável arbitrária.

Assumir por hipótese de indução que:

$$P(x_0) \triangleq Pot2(x_0) = 2^{x_0} \ (HI)$$

Demonstrar  $P(x_0 + 1)$ :

$$P(x_0 + 1) \triangleq Pot2(x_0 + 1) = 2^{x_0 + 1}$$
 (HI)

Passos da demonstração:

$$Pot2(x_0 + 1)$$

$$= 2 \times Pot2(x_0) \qquad (por pot2_2)$$

$$= 2 \times 2^{x_0} \qquad (por HI)$$

$$= 2^{x_0+1} \qquad (por alg. arit.)$$

q.e.d.

## Exemplo 2:

Uma possível especificação equacional recursiva para o somatório

$$\sum_{k=1}^{u} 2k$$

é dada por:

 $Sum2k: \mathbb{N} \times \mathbb{N} \to \mathbb{N}$ 

requer:  $l \leq u$ 

$$garante: Sum2k(l, u) = \sum_{k=l}^{u} 2k$$

$$Sum2k(l, l) = 2 * l$$
 (sum2k\_1)

$$Sum2k(l, u) = 2 * u + sum2k(l, u - 1)$$
, se  $l < u$  (sum2k\_2)

Estamos interessados em provar pelo princípio de indução que a especificação equacional recursiva corresponde a um somatório desejado. O somatório desejado é:

$$P(n) \triangleq Sum2k(0,n) = \sum_{k=0}^{n} 2k$$

Importante: neste exemplo, estamos interessados em provar uma determinada propriedade assumindo que a função já foi provada correta anteriormente!

Observe que muitas vezes a propriedade (e consequentemente a equação) que queremos demonstrar envolve o uso de funções com mais de um argumento. Nesse caso, a utilização da seguinte heurística é recomendada: "Caso a função possua mais de um argumento, realizar a indução no argumento de posição *i* se a função é definida por recursão no argumento de posição *i*". Assim, no caso de exemplo, a indução será no segundo argumento.

### Caso base:

Demonstrar P(0):

$$P(0) \triangleq Sum2k(0,0) = \sum_{k=0}^{0} 2k$$

Passos da demonstração:

Sum2k(0,0)

$$= 2 \times 0 \quad (por sum 2k_1)$$

$$= \sum_{k=0}^{0} 2k \quad (por \ definição \ do \ somat{\'orio})$$

q.e.d.

### Caso indutivo:

Seja  $x_0 \in \mathbb{N}$  uma variável arbitrária.

Assumir como hipótese de indução (HI) que:

$$P(x_0) \triangleq Sum2k(0, x_0) = \sum_{k=0}^{x_0} 2k$$
 (HI)

Demonstrar  $P(x_0 + 1)$ :

$$P(x_0 + 1) \triangleq Sum2k(0, (x_0 + 1)) = \sum_{k=0}^{x_0 + 1} 2k$$

Passos da demonstração:

$$\begin{aligned} &Sum2k \big(0,(x_0+1)\big) \\ &= 2(x_0+1) + Sum2k(0,x_0) \quad (por \ sum2k\_2) \\ &= 2(x_0+1) + \sum_{k=0}^{x_0} 2k \ (por \ HI) \\ &= \sum_{k=0}^{x_0} 2k + 2(x_0+1) \quad (por \ alg. \ arit.) \end{aligned}$$

$$= \sum_{k=0}^{x_0+1} 2k \quad (por \ definição \ do \ somat\'orio)$$

q.e.d.
