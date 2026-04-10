## **Funções Recursivas sobre Listas**

## **1. Introdução**

Listas são um dos tipos de coleções mais básicos que podemos encontrar em diversas linguagens de programação.

Nosso objetivo é definir um tipo de dado indutivo para representar listas e diversas operações sobre a mesma. Essa formalização se dará na forma de equações recursivas, um modelo matemático adequado aos nossos objetivos.

## **2. Listas polimórficas (definição indutiva)**

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

## **3. Listas polimórficas (equações recursivas)**

Como um exemplo de formalização recursiva sobre as listas, assuma uma função que recebe duas listas e retorna uma nova lista como resultado da concatenação das listas recebidas como parâmetros:

$$cat: List(\tau) \times List(\tau) \rightarrow List(\tau)$$

$$cat([ ], l) = l$$
(1)

$$cat(h:T,l) = h: cat(T,l)$$
 (2)

Um exemplo de computação para ([1,2],[3,4]):

$$cat([1,2],[3,4]) = cat(1:[2],[3,4])$$
 (pela simplificação sintática)  
= 1: $cat([2],[3,4])$  (por 2)

= 1:*cat*(2:[],[3,4]) (pela simplificação sintática)

= 1:2:*cat*([],[3,4]) (por 2)

= 1:2:[3,4] (por 1)

= [1,2,3,4] (pela simplificação sintática)
