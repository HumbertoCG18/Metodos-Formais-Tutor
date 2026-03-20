Métodos Formais

Prof. Júlio Machado

## 1. Introdução

Listas  são  um  dos  tipos  de  coleções  mais  básicos  que  podemos  encontrar  em  diversas linguagens de programação.

Nosso  objetivo  é  definir  um  tipo  de  dado  indutivo  para  representar  listas  e  diversas operações sobre a mesma. Essa formalização se dará na forma de equações recursivas, um modelo matemático adequado aos nossos objetivos.

## 2. Listas polimórficas (definição indutiva)

Um  tipo  indutivo  para  representar  listas polimórficas ou genéricas ,  representada  por 𝐿𝑖𝑠𝑡(𝜏) ,  onde 𝜏 é  um  conjunto  arbitrário  (representando  os  elementos  que  podem pertencer à lista), pode ser representado por dois construtores:

- Um construtor base para  representar  a  lista  vazia,  representado  pelo  símbolo ' [ ] ';
- Um construtor indutivo para representar a anexação de um elemento à esquerda de uma lista, representado pelo símbolo ' : '.

Assim, os elementos do tipo indutivo 𝐿𝑖𝑠𝑡(𝜏) são gerados pelas seguintes regras:

$$\overline { [ \, ] \in L i s t ( \tau ) } ^ { e m p t y } \\ \frac { L \in L i s t ( \tau ) , h \in \tau } { h \colon L \in L i s t ( \tau ) } c o n s$$

A fim de facilitar a descrição de listas, vamos assumir a seguinte simplificação de sintaxe (em inglês, utiliza-se o temo syntatic sugar ):

$$x _ { 1 } \colon x _ { 2 } \colon \dots \colon x _ { n } \colon [ \ ] = [ x _ { 1 } , x _ { 2 } , \dots , x _ { n } ]$$

Note que a declaração utilizada para listas polimórficas implica, na verdade, em uma família de listas indexadas pelo tipo do parâmetro 𝜏 . Por exemplo:

| Instância   | Elementos do Conjunto              |
|-------------|------------------------------------|
| 𝐿𝑖𝑠𝑡(ℕ)     | [], [0], [1], [0,1], ...           |
| 𝐿𝑖𝑠𝑡(ℤ)     | [], [-1], [-2,-1], ...             |
| 𝐿𝑖𝑠𝑡(ℕ ×ℤ)  | [], [<2,0>], [<-1,-10>,<0,7>], ... |

## Funções Recursivas sobre Listas

## 3. Listas polimórficas (equações recursivas)

Como um exemplo de formalização recursiva sobre as listas, assuma uma função que recebe duas listas e retorna uma nova lista como resultado da concatenação das listas recebidas como parâmetros:

$$c a t \colon L i s t ( \tau ) \times L i s t ( \tau ) \to L i s t ( \tau )$$

$$c a t ( [ \ ] , l ) = l$$

$$c a t ( h \colon T , l ) = h \colon c a t ( T , l )$$

Um exemplo de computação para 𝑐𝑎𝑡([1,2], [3,4]) :

cat ([1,2],[3,4])   = cat (1:[2],[3,4]) (pela simplificação sintática) = 1: cat ([2],[3,4]) (por 2) = 1: cat (2:[],[3,4]) (pela simplificação sintática) = 1:2: cat ([],[3,4]) (por 2) = 1:2:[3,4] (por 1)

= [1,2,3,4] (pela simplificação sintática)