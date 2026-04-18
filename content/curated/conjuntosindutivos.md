<!-- EXEC_SUMMARY_START -->
## Sumário
> *Leia antes de varrer o arquivo. Vá direto à seção relevante para a pergunta do aluno.*

- ****Métodos Formais****
- ****Prof. Júlio Machado****
- ****1. Revisão****
  - **Introdução**
- ****Representação por enumeração****
  - Exemplos:
  - **Igualdade de conjuntos**
- ****2. Definição por indução****
- **Axioma:**
- **3. Árvores de prova**
- ****4. Listas****

<!-- EXEC_SUMMARY_END -->
## **Métodos Formais**
## **Prof. Júlio Machado**

# **Conjuntos Indutivos**
## **1. Revisão**
### **Introdução**

Como em qualquer assunto a ser estudado, a Matemática também exige uma linguagem adequada para o seu desenvolvimento.

A **Teoria dos Conjuntos** representa instrumento de grande utilidade nos diversos desenvolvimentos da Matemática, bem como em outros ramos das ciências físicas e humanas.

Devemos aceitar, inicialmente, a existência de alguns conceitos primitivos (noções que adotamos sem definição) e que estabelecem a linguagem do estudo da Teoria dos Conjuntos.

Adotaremos a existência de três conceitos primitivos: **elemento**, **conjunto** e **pertinência**. Assim é preciso entender que, cada um de nós é um elemento do conjunto de moradores desta cidade, ou melhor, cada um de nós é um elemento que pertence ao conjunto de habitantes da cidade, mesmo que não tenhamos definido o que é conjunto, o que é elemento e o que é pertinência.
#### **Notação e Representação**

A notação dos conjuntos é feita mediante a utilização de uma letra maiúscula do nosso alfabeto e a representação de um conjunto pode ser feita de diversas maneiras, como veremos a seguir.

O conjunto vazio não possui elementos e pode ser representado por { } ou Ø.

O conjunto universo é o conjunto de todos os elementos do contexto sendo trabalhado e pode ser representado pela letra maiúscula U.
## **Representação por enumeração**

Apresentamos um conjunto por meio da listagem de seus elementos quando relacionamos todos os elementos que pertencem ao conjunto considerado e envolvemos essa lista por um par de chaves. Os elementos de um conjunto, quando apresentados na forma de listagem, devem ser separados por vírgula ou por ponto-e-vírgula, caso tenhamos a presença de números decimais.
### Exemplos:

a) Seja A o conjunto das cores da bandeira brasileira, então:

A = {verde, amarelo, azul, branco}

b) Seja B o conjunto das vogais do nosso alfabeto, então:

$$B = \{a, e, i, o, u\}$$

c) Seja C o conjunto dos algarismos do sistema decimal de numeração, então:

$$C = \{0, 1, 2, 3, 4, 5, 6, 7, 8, 9\}$$

d) Seja $\mathbb{N}$ o conjunto dos números Naturais, então:

$$\mathbb{N} = \{0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, ...\}$$
#### **Representação pelas propriedades dos elementos**

A apresentação de um conjunto por meio da listagem de seus elementos traz o inconveniente de não ser uma notação prática para os casos em que o conjunto apresenta uma infinidade de elementos. Para estas situações, podemos fazer a apresentação do conjunto por meio de uma propriedade que sirva a todos os elementos do conjunto e somente a estes elementos.

Exemplo 1: conjunto dos números naturais, pares, maiores que zero e menores que 15.

• Representação por enumeração:

$$A = \{2, 4, 6, 8, 10, 12, 14\}$$

• Representação pelas propriedades dos elementos:

$$A = \{x/x \in \mathbb{N} \land x \in par \land x > 0 \land x < 15\}$$

Exemplo 2: conjunto dos números naturais menores que 20:

• Representação por enumeração:

$$B = \{0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20\}$$

• Representação pelas propriedades dos elementos:

$$B = \{x/x \in \mathbb{N} \land x < 20\}$$

Exemplo 3: conjunto resultante da intersecção entre os conjuntos *A* e *B* definidos anteriormente:

• Representação por enumeração:

$$C = \{2,4,6,8,10,12,14\}$$

• Representação pelas propriedades dos elementos:

$$C = \{x/x \in (A \cap B)\}\$$
#### **Relação de pertinência**

Quando queremos indicar que um determinado elemento *x* faz parte de um conjunto *A*, dizemos que o elemento *x* pertence ao conjunto *A* e indicamos:

$$x \in A$$

em que o símbolo $\in$ é uma versão da letra grega épsilon e está consagrado em toda matemática como símbolo indicativo de pertinência. Para indicarmos que um elemento x não pertence ao conjunto *A*, indicamos:

$$x \notin A$$

Exemplo 1: Consideremos o conjunto A={0, 2, 4, 6, 8}

O algarismo 2 pertence ao conjunto *A*: 2 $\in$

O algarismo 7 não pertence ao conjunto *A*: 7 $\notin$
#### **Relação de inclusão/subconjuntos**

Dizemos que o conjunto *A* está contido no conjunto *B* se todo elemento que pertencer a *A*, pertencer também a *B*. Indicamos que o conjunto *A* está [contido](javascript:popGlossario() em *B* por meio da seguinte simbologia:

$\subset$ (lê-se: *A* contido em *B*)

Obs.: podemos encontrar em algumas publicações uma outra notação para a relação de inclusão:

$\supset$ (lê-se: *B* contém *A*)

O conjunto *A* não está contido em *B* quando existe pelo menos um elemento de *A* que não pertence a *B*. Indicamos que o conjunto *A* não está contido em *B* desta maneira:

$\not\subset$ (lê-se: *A* não está contido em *B*)

<!-- IMAGE_DESCRIPTION: conjuntosindutivos-_page_3_Picture_7.png -->
<!-- Tipo: diagrama -->
> **[Descrição de imagem]** O diagrama apresenta três configurações de diagramas de Venn que ilustram relações de inclusão entre conjuntos.
<!-- /IMAGE_DESCRIPTION -->
![](content/images/conjuntosindutivos-_page_3_Picture_7.png)

Se o conjunto *A* está contido no conjunto *B*, dizemos que *A* é um [subconjunto](javascript:popGlossario() de *B*. Como todo elemento do conjunto *A* pertence ao conjunto *A*, dizemos que *A* é subconjunto de *A* e, por extensão, todo conjunto é subconjunto dele mesmo.

Importante – a relação de pertinência relaciona um elemento a um conjunto e a relação de inclusão refere-se, sempre, a dois conjuntos.

Podemos notar que existe uma diferença entre 2 e {2}. O primeiro é o elemento 2, e o segundo é o conjunto formado pelo elemento 2. Um par de sapatos e uma caixa com um par de sapatos são coisas diferentes e como tal devem ser tratadas.

Podemos notar, também, que, dentro de um conjunto, um outro conjunto pode ser tratado como um de seus elementos. Vejamos o exemplo a seguir:

{1, 2} é um conjunto, porém no conjunto *A* = {1, 3, {1, 2}, 4} ele será considerado um elemento, ou seja, {1, 2}$\in$ .

Uma cidade é um conjunto de pessoas que representam os moradores da cidade, porém uma cidade é um elemento do conjunto de cidades que formam um Estado.
#### **Conjunto das partes**

Dado um conjunto *A*, dizemos que o seu conjunto de partes, representado por *P*(*A*) ou 2 , é o conjunto formado por todos os subconjuntos do conjunto *A*.

Vamos observar, com o exemplo a seguir, o procedimento que se deve adotar para a determinação do conjunto de partes de um dado conjunto *A*.

Seja o conjunto *A* = {2, 3, 5}. Para obtermos o conjunto de partes do conjunto *A*, basta escrevermos todos os seus subconjuntos:

- 1o) Subconjunto vazio: {}, pois o conjunto vazio é subconjunto de qualquer conjunto.
- 2o) Subconjuntos com um elemento: {2}, {3}, {5}.
- 3o) Subconjuntos com dois elementos: {2, 3}, {2, 5} e {3, 5}.
- 4o) Subconjuntos com três elementos: {2, 3, 5}, pois todo conjunto é subconjunto dele mesmo.

Assim, o conjunto das partes do conjunto *A* pode ser apresentado da seguinte forma: *P*(*A*) = {{}, {2}, {3}, {5}, {2, 3}, {2, 5}, {3, 5}, {2, 3, 5}}.
#### **Número de elementos do conjunto das partes**

Podemos determinar o número de elementos do conjunto de partes de um conjunto *A* dado, ou seja, o número de subconjuntos do referido conjunto, sem que haja necessidade de escrevermos todos os elementos do conjunto *P*(*A*). Para isso, basta partirmos da ideia de que cada elemento do conjunto *A* tem duas opções na formação dos subconjuntos: ou o elemento pertence ao subconjunto ou ele não pertence ao subconjunto e, pelo uso do princípio multiplicativo das regras de contagem, se cada elemento apresenta duas opções, teremos:

$$|P(A)| = 2^{|A|}$$

Observemos o exemplo anterior: o conjunto *A* = {2, 3, 5} apresenta três elementos e, portanto, é de se supor, pelo uso da relação apresentada, que |*P*(*A*)| = 2<sup>3</sup> = 8, o que de fato ocorreu.
### **Igualdade de conjuntos**

Dois conjuntos são iguais se, e somente se, eles possuírem os mesmos elementos, em qualquer ordem. Vejamos os exemplos:

$$\{1, 3, 7\} = \{1, 7, 3\} = \{3,1,7\} = \{3,7,1\} = \{7, 3, 1\} = \{7,1,3\}$$
## **2. Definição por indução**

No contexto de Ciência da Computação é interessante dispor de uma maneira "algorítmica" de definir conjuntos pois desta forma poderemos não apenas automatizar a construção de um conjunto, mas também verificar de forma automatizada se um dado elemento pertence aquele conjunto ou não. Uma maneira "algorítmica" de se definir um conjunto é usar a indução matemática.

Uma definição indutiva de um conjunto *I* consiste sempre dos seguintes passos:

- **Base**: listar alguns elementos específicos de *I*; pelo menos um elemento deve ser listado.
- **Indução**: definir uma ou mais regras para a construção de novos elementos de *I* a partir dos elementos já existentes.
- **Fecho**: declarar que *I* consiste exatamente dos elementos produzidos pelos passos da base e da indução.

Mais especificamente define-se um subconjunto *I* de um conjunto *U* pela aplicação repetida de regras de inferência e axiomas.
## Axioma:

- o Definição de um conjunto base {/ $\in$ }
- o Representação gráfica: para cada elemento do conjunto base $\in$ [ ]
#### Regra:

- o Corresponde a um par <*H*,*c*> onde:
  - *H* é um subconjunto finito de *U* (os elementos de *H* são chamados de hipóteses da regra)
  - *c* é um elemento de *U* (chamado de conclusão da regra)
- o Representação gráfica: 1$\ldots$ $\in$ $\in$ [ ]

Exemplo: definição do conjunto dos números naturais

$$\frac{x \in \mathbb{N}}{0 \in \mathbb{N}} Zero \qquad \frac{x \in \mathbb{N}}{x+1 \in \mathbb{N}} Suc$$
## 3. Árvores de prova

Pode-se determinar se um elemento faz parte de um conjunto indutivo usando uma árvore de prova. Dado um conjunto de regras  $R \subseteq (P(U) \times U)$  sobre U, uma árvore de prova é uma árvore finita T com nodos rotulados por elementos de U tal que para cada nodo n de T, se H é o conjunto de rótulos dos filhos de n e n e n0 e o rótulo de n0, então n0 e uma regra em n1.

Se R é um conjunto de regras sobre U, o conjunto  $I \subseteq U$  indutivamente definido por R consiste nos elementos  $t \in U$  para os quais existe uma árvore de prova cujo nodo raiz é rotulado por  $t \in U$ .

Dito de outra forma, *l* é o menor conjunto gerado a partir da aplicação das regras de *R* no seguinte sentido:

- Base: para cada axioma  $< \emptyset, c > \in R, c \in I$
- Indução: para cada regra  $<\{h_1,\dots,h_n\},c>\in R,com\ n\geq 1,se\ h_1\in I,\dots,h_n\in I,então\ c\in I$
- **Fecho:** nada mais está em *I* exceto os elementos gerados pelos passos base e passos de indução.

Exemplo 1: números naturais

Regras:

$$\frac{x \in \mathbb{N}}{0 \in \mathbb{N}} Zero \qquad \frac{x \in \mathbb{N}}{x+1 \in \mathbb{N}} Suc$$

Árvore de prova: mostrar que  $4 \in \mathbb{N}$ 

$$\frac{\frac{\overline{0 \in \mathbb{N}}^{Zero}}{1 \in \mathbb{N}} Suc}{\frac{2 \in \mathbb{N}}{3 \in \mathbb{N}} Suc} Suc}$$

$$\frac{3 \in \mathbb{N}}{4 \in \mathbb{N}} Suc}$$

Exemplo 2: conjunto das strings  $S1=\{a^nba^n|n\in\mathbb{N}\}=\{b,aba,aabaa,aaabaaa,...\}$ 

Regras:

$$\frac{}{b \in S1} base$$
  $\frac{w \in S1}{awa \in S1} plus$ 

Árvore de prova: mostrar que  $aabaa \in S1$  e que  $aaba \notin S1$ 

$$\frac{b \in S1}{aba \in S1} \frac{base}{plus}$$

$$\frac{aba \in S1}{aabaa \in S1} plus$$

$$\frac{\frac{?}{ab \in S1}?}{aaba \in S1}plus$$
## **4. Listas**

Listas são um dos tipos de coleções mais básicos que podemos encontrar em diversas linguagens de programação. Nosso objetivo é definir um tipo de dado indutivo para representar listas.

Um tipo indutivo para representar listas *polimórficas* ou *genéricas*, representada por (), onde é um conjunto arbitrário (representando os elementos que podem pertencer à lista), pode ser representado por dois construtores:

- Um *construtor base* para representar a lista vazia, representado pelo símbolo "[ ]";
- Um *construtor indutivo* para representar a anexação de um elemento à esquerda de uma lista, representado pelo símbolo " :".

Assim, os elementos do tipo indutivo () são gerados pelas seguintes regras:

$$\overline{[\ ]} \in List(\tau) empty$$

$$\underline{L} \in List(\tau), h \in \tau$$

$$\underline{h: L \in List(\tau)} cons$$

A fim de facilitar a descrição de listas, vamos assumir a seguinte simplificação de sintaxe (em inglês, utiliza-se o temo *syntatic sugar*):

$$x_1: x_2: ...: x_n: [ ] = [x_1, x_2, ..., x_n]$$

Note que a declaração utilizada para listas polimórficas implica, na verdade, em uma família de listas indexadas pelo tipo do parâmetro . Por exemplo:

| Instância         | Elementos do Conjunto          |
|-------------------|--------------------------------|
| 𝐿𝑖𝑠𝑡($\mathbb{N}$)           | [], [0], [1], [0,1],           |
| 𝐿𝑖𝑠𝑡($\mathbb{Z}$)           | [], [-1], [-2,-1],             |
| 𝐿𝑖𝑠𝑡($\mathbb{N}$<br>$\times$<br>$\mathbb{Z}$) | [], [<2,0>], [<-1,-10>,<0,7>], |

# **5. Árvores**

Informalmente, uma definição recursiva para uma árvore binária pode ser:

- Uma árvore vazia ou
- Uma árvore composta por duas sub-árvores, sendo uma esquerda e outra direita.

Uma definição formal pode ser dada através da definição de um conjunto indutivo para todas as árvores sobre um determinado tipo :

$$\frac{\langle \cdot \rangle \in ArvBin(\tau)}{\langle L, x, R \rangle \in ArvBin(\tau), \ x \in \tau} cons$$

São exemplos de árvores binárias de números naturais (elementos do conjunto ($\mathbb{N}$): 〈 〉,〈〈 〉, 0,〈 〉〉,〈〈〈 〉, 1,〈 〉〉, 0,〈〈 〉, 2,〈 〉〉〉
