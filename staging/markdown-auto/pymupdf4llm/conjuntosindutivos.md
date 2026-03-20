---
entry_id: "conjuntosindutivos"
title: "Conjuntosindutivos"
backend: "pymupdf4llm"
source_pdf: "raw/pdfs/material-de-aula/conjuntosindutivos.pdf"
page_range: "1-9"
---
## **Métodos Formais** 

## **Prof. Júlio Machado** 

## **Conjuntos Indutivos** 

## **1. Revisão** 

## **Introdução** 

Como em qualquer assunto a ser estudado, a Matemática também exige uma linguagem adequada para o seu desenvolvimento. 

A **Teoria dos Conjuntos** representa instrumento de grande utilidade nos diversos desenvolvimentos da Matemática, bem como em outros ramos das ciências físicas e humanas. 

Devemos aceitar, inicialmente, a existência de alguns conceitos primitivos (noções que adotamos sem definição) e que estabelecem a linguagem do estudo da Teoria dos Conjuntos. 

Adotaremos a existência de três conceitos primitivos: **elemento** , **conjunto** e **pertinência** . Assim é preciso entender que, cada um de nós é um elemento do conjunto de moradores desta cidade, ou melhor, cada um de nós é um elemento que pertence ao conjunto de habitantes da cidade, mesmo que não tenhamos definido o que é conjunto, o que é elemento e o que é pertinência. 

## **Notação e Representação** 

A notação dos conjuntos é feita mediante a utilização de uma letra maiúscula do nosso alfabeto e a representação de um conjunto pode ser feita de diversas maneiras, como veremos a seguir. 

O conjunto vazio não possui elementos e pode ser representado por { } ou Ø. 

O conjunto universo é o conjunto de todos os elementos do contexto sendo trabalhado e pode ser representado pela letra maiúscula U. 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0001-13.png)


--- end of page.page_number=1 ---

## **Representação por enumeração** 

Apresentamos um conjunto por meio da listagem de seus elementos quando relacionamos todos os elementos que pertencem ao conjunto considerado e envolvemos essa lista por um par de chaves. Os elementos de um conjunto, quando apresentados na forma de listagem, devem ser separados por vírgula ou por ponto-e-vírgula, caso tenhamos a presença de números decimais. 

Exemplos: 

a) Seja A o conjunto das cores da bandeira brasileira, então: 

A = {verde, amarelo, azul, branco} 

b) Seja B o conjunto das vogais do nosso alfabeto, então: 

B = {a, e, i, o, u} 

c) Seja C o conjunto dos algarismos do sistema decimal de numeração, então: 

C = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9} 

d) Seja ℕ o conjunto dos números Naturais, então: 

ℕ = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, ...} 

## **Representação pelas propriedades dos elementos** 

A apresentação de um conjunto por meio da listagem de seus elementos traz o inconveniente de não ser uma notação prática para os casos em que o conjunto apresenta uma infinidade de elementos. Para estas situações, podemos fazer a apresentação do conjunto por meio de uma propriedade que sirva a todos os elementos do conjunto e somente a estes elementos. 

Exemplo 1: conjunto dos números naturais, pares, maiores que zero e menores que 15. 

- Representação por enumeração: 

𝐴= {2, 4, 6, 8, 10, 12, 14} 

- Representação pelas propriedades dos elementos: 

𝐴= {𝑥𝑥⁄ ∈ℕ⋀𝑥é 𝑝𝑎𝑟⋀ 𝑥> 0 ⋀𝑥< 15} 

--- end of page.page_number=2 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0003-00.png)


Exemplo 2: conjunto dos números naturais menores que 20: 

- Representação por enumeração: 

𝐵= {0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20} 

- Representação pelas propriedades dos elementos: 

𝐵= {𝑥𝑥 ∈ℕ ⋀𝑥< 20⁄ } 

Exemplo 3: conjunto resultante da intersecção entre os conjuntos _A_ e _B_ definidos anteriormente: 

- Representação por enumeração: 

𝐶= { 2,4,6,8,10,12,14 } 

- Representação pelas propriedades dos elementos: 

𝐶= {𝑥𝑥 ∈(𝐴 ⋂𝐵)⁄ } 

## **Relação de pertinência** 

Quando queremos indicar que um determinado elemento _x_ faz parte de um conjunto _A_ , dizemos que o elemento _x_ pertence ao conjunto _A_ e indicamos: 

x ∈A 

em que o símbolo ∈ é uma versão da letra grega épsilon e está consagrado em toda matemática como símbolo indicativo de pertinência. Para indicarmos que um elemento x não pertence ao conjunto _A_ , indicamos: 

x ∉A 

Exemplo 1: Consideremos o conjunto A={0, 2, 4, 6, 8} 

O algarismo 2 pertence ao conjunto _A_ : 2 ∈𝐴 

O algarismo 7 não pertence ao conjunto _A_ : 7 ∉𝐴 

--- end of page.page_number=3 ---

## **Relação de inclusão/subconjuntos** 

Dizemos que o conjunto _A_ está contido no conjunto _B_ se todo elemento que pertencer a _A_ , pertencer também a _B_ . Indicamos que o conjunto _A_ está contido em _B_ por meio da seguinte simbologia: 

𝐴⊂𝐵 (lê-se: _A_ contido em _B_ ) 

Obs.: podemos encontrar em algumas publicações uma outra notação para a relação de inclusão: 

𝐵⊃𝐴 (lê-se: _B_ contém _A_ ) 

O conjunto _A_ não está contido em _B_ quando existe pelo menos um elemento de _A_ que não pertence a _B_ . Indicamos que o conjunto _A_ não está contido em _B_ desta maneira: 

𝐴⊄𝐵 (lê-se: _A_ não está contido em _B_ ) 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0004-07.png)



![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0004-08.png)


Se o conjunto _A_ está contido no conjunto _B_ , dizemos que _A_ é um subconjunto de _B_ . Como todo elemento do conjunto _A_ pertence ao conjunto _A_ , dizemos que _A_ é subconjunto de _A_ e, por extensão, todo conjunto é subconjunto dele mesmo. 

Importante – a relação de pertinência relaciona um elemento a um conjunto e a relação de inclusão refere-se, sempre, a dois conjuntos. 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0004-11.png)


Podemos notar que existe uma diferença entre 2 e {2}. O primeiro é o elemento 2, e o segundo é o conjunto formado pelo elemento 2. Um par de sapatos e uma caixa com um par de sapatos são coisas diferentes e como tal devem ser tratadas. 

Podemos notar, também, que, dentro de um conjunto, um outro conjunto pode ser tratado como um de seus elementos. Vejamos o exemplo a seguir: 

--- end of page.page_number=4 ---

{1, 2} é um conjunto, porém no conjunto _A_ = {1, 3, {1, 2}, 4} ele será considerado um elemento, ou seja, {1, 2} ∈𝐴 . 

Uma cidade é um conjunto de pessoas que representam os moradores da cidade, porém uma cidade é um elemento do conjunto de cidades que formam um Estado. 

## **Conjunto das partes** 

Dado um conjunto _A_ , dizemos que o seu conjunto de partes, representado por _P_ ( _A_ ) ou 2[𝐴] , é o conjunto formado por todos os subconjuntos do conjunto _A_ . 

Vamos observar, com o exemplo a seguir, o procedimento que se deve adotar para a determinação do conjunto de partes de um dado conjunto _A_ . 

Seja o conjunto _A_ = {2, 3, 5}. Para obtermos o conjunto de partes do conjunto _A_ , basta escrevermos todos os seus subconjuntos: 

1o) Subconjunto vazio: {}, pois o conjunto vazio é subconjunto de qualquer conjunto. 

2o) Subconjuntos com um elemento: {2}, {3}, {5}. 

3o) Subconjuntos com dois elementos: {2, 3}, {2, 5} e {3, 5}. 

4o) Subconjuntos com três elementos: {2, 3, 5}, pois todo conjunto é subconjunto dele mesmo. 

Assim, o conjunto das partes do conjunto _A_ pode ser apresentado da seguinte forma: _P_ ( _A_ ) = {{}, {2}, {3}, {5}, {2, 3}, {2, 5}, {3, 5}, {2, 3, 5}}. 

## **Número de elementos do conjunto das partes** 

Podemos determinar o número de elementos do conjunto de partes de um conjunto _A_ dado, ou seja, o número de subconjuntos do referido conjunto, sem que haja necessidade de escrevermos todos os elementos do conjunto _P_ ( _A_ ). Para isso, basta partirmos da ideia de que cada elemento do conjunto _A_ tem duas opções na formação dos subconjuntos: ou o elemento pertence ao subconjunto ou ele não pertence ao subconjunto e, pelo uso do princípio multiplicativo das regras de contagem, se cada elemento apresenta duas opções, teremos: 

|𝑃(𝐴)| = 2[|𝐴|] 

Observemos o exemplo anterior: o conjunto _A_ = {2, 3, 5} apresenta três elementos e, portanto, é de se supor, pelo uso da relação apresentada, que | _P_ ( _A_ )| = 2[3] = 8, o que de fato ocorreu. 

--- end of page.page_number=5 ---

## **Igualdade de conjuntos** 

Dois conjuntos são iguais se, e somente se, eles possuírem os mesmos elementos, em qualquer ordem. Vejamos os exemplos: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0006-02.png)


## **2. Definição por indução** 

No contexto de Ciência da Computação é interessante dispor de uma maneira “algorítmica” de definir conjuntos pois desta forma poderemos não apenas automatizar a construção de um conjunto, mas também verificar de forma automatizada se um dado elemento pertence aquele conjunto ou não. Uma maneira “algorítmica” de se definir um conjunto é usar a indução matemática. 

Uma definição indutiva de um conjunto _I_ consiste sempre dos seguintes passos: 

- **Base** : listar alguns elementos específicos de _I_ ; pelo menos um elemento deve ser listado. 

- **Indução** : definir uma ou mais regras para a construção de novos elementos de _I_ a partir dos elementos já existentes. 

- **Fecho** : declarar que _I_ consiste exatamente dos elementos produzidos pelos passos da base e da indução. 

Mais especificamente define-se um subconjunto _I_ de um conjunto _U_ pela aplicação repetida de regras de inferência e axiomas. 

Axioma: 

`o` Definição de um conjunto base {𝑎/𝑎∈𝑈} 

- Representação gráfica: para cada elemento do conjunto base 

[𝑛𝑜𝑚𝑒 𝑑𝑜 𝑎𝑥𝑖𝑜𝑚𝑎] 𝑎∈𝐼 

Regra: 

`o` Corresponde a um par < _H_ , _c_ > onde: 

▪ _H_ é um subconjunto finito de _U_ (os elementos de _H_ são chamados de hipóteses da regra) ▪ _c_ é um elemento de _U_ (chamado de conclusão da regra) 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0006-17.png)


Exemplo: definição do conjunto dos números naturais 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0006-19.png)


--- end of page.page_number=6 ---

## **3. Árvores de prova** 

Pode-se determinar se um elemento faz parte de um conjunto indutivo usando uma árvore de prova. Dado um conjunto de regras 𝑅⊆(𝑃(𝑈) × 𝑈) sobre _U_ , uma árvore de prova é uma árvore finita _T_ com nodos rotulados por elementos de _U_ tal que para cada nodo _n_ de _T_ , se _H_ é o conjunto de rótulos dos filhos de _n_ e _c_ é o rótulo de _n_ , então < _H_ , _c_ > é uma regra em _R_ . 

Se _R_ é um conjunto de regras sobre _U_ , o conjunto 𝐼⊆𝑈 indutivamente definido por _R_ consiste nos elementos 𝑡∈𝑈 para os quais existe uma árvore de prova cujo nodo raiz é rotulado por 𝑡∈𝑈 . 

Dito de outra forma, _I_ é o menor conjunto gerado a partir da aplicação das regras de _R_ no seguinte sentido: 

- **Base:** para cada axioma < ∅, 𝑐> ∈𝑅, 𝑐∈𝐼 

- **Indução:** para cada regra < {ℎ1, … , ℎ𝑛}, 𝑐>∈𝑅, 𝑐𝑜𝑚 𝑛≥1, 𝑠𝑒 ℎ1 ∈𝐼, … , ℎ𝑛 ∈ 𝐼, 𝑒𝑛𝑡ã𝑜 𝑐 ∈𝐼 

- **Fecho:** nada mais está em _I_ exceto os elementos gerados pelos passos base e passos de indução. 

Exemplo 1: números naturais 

Regras: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0007-09.png)


Árvore de prova: mostrar que 4 ∈ℕ 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0007-11.png)


**----- Start of picture text -----**<br>
𝑍 𝑒𝑟𝑜<br>0∈ℕ<br>𝑆 𝑢𝑐<br>1∈ℕ<br>𝑆𝑢𝑐<br>2∈ℕ<br>𝑆𝑢𝑐<br>3∈ℕ  𝑆𝑢𝑐<br>4 ∈ ℕ<br>**----- End of picture text -----**<br>


Exemplo 2: conjunto das strings 𝑆1 = {𝑎[𝑛] 𝑏𝑎[𝑛] |𝑛∈ℕ} = {𝑏, 𝑎𝑏𝑎, 𝑎𝑎𝑏𝑎𝑎, 𝑎𝑎𝑎𝑏𝑎𝑎𝑎, … } 

Regras: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0007-14.png)


Árvore de prova: mostrar que 𝑎𝑎𝑏𝑎𝑎∈𝑆1 e que 𝑎𝑎𝑏𝑎∉𝑆1 

𝑏𝑎𝑠𝑒 𝑏∈𝑆1 𝑝𝑙𝑢𝑠 𝑎𝑏𝑎∈𝑆1 𝑝𝑙𝑢𝑠 𝑎𝑎𝑏𝑎𝑎∈𝑆1 

--- end of page.page_number=7 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0008-00.png)


## **4. Listas** 

Listas são um dos tipos de coleções mais básicos que podemos encontrar em diversas linguagens de programação. Nosso objetivo é definir um tipo de dado indutivo para representar listas. 

Um tipo indutivo para representar listas _polimórficas_ ou _genéricas_ , representada por 𝐿𝑖𝑠𝑡(𝜏) , onde 𝜏 é um conjunto arbitrário (representando os elementos que podem pertencer à lista), pode ser representado por dois construtores: 

- Um _construtor base_ para representar a lista vazia, representado pelo símbolo “ [ ] ”; 

- Um _construtor indutivo_ para representar a anexação de um elemento à esquerda de uma lista, representado pelo símbolo ” : ”. 

Assim, os elementos do tipo indutivo 𝐿𝑖𝑠𝑡(𝜏) são gerados pelas seguintes regras: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0008-07.png)


A fim de facilitar a descrição de listas, vamos assumir a seguinte simplificação de sintaxe (em inglês, utiliza-se o temo _syntatic sugar_ ): 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0008-09.png)


Note que a declaração utilizada para listas polimórficas implica, na verdade, em uma família de listas indexadas pelo tipo do parâmetro 𝜏 . Por exemplo: 

|e a declaração utilizada para<br>as pelo tipo do parâmetro𝜏.|listas polimórficas implica, na verdade, em uma família de listas<br>Por exemplo:|
|---|---|
|Instância|Elementos do Conjunto|
|𝐿𝑖𝑠𝑡(ℕ)|[], [0], [1], [0,1],...|
|𝐿𝑖𝑠𝑡(ℤ)|[], [-1], [-2,-1],...|
|𝐿𝑖𝑠𝑡(ℕ× ℤ)|[], [<2,0>], [<-1,-10>,<0,7>],...|



## **5. Árvores** 

Informalmente, uma definição recursiva para uma árvore binária pode ser: 

- Uma árvore vazia ou 

- Uma árvore composta por duas sub-árvores, sendo uma esquerda e outra direita. 

Uma definição formal pode ser dada através da definição de um conjunto indutivo para todas as árvores sobre um determinado tipo 𝜏 : 

--- end of page.page_number=8 ---

𝑣𝑎𝑧𝑖𝑎 〈 〉∈𝐴𝑟𝑣𝐵𝑖𝑛(𝜏) 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/conjuntosindutivos/conjuntosindutivos.pdf-0009-01.png)


São exemplos de árvores binárias de números naturais (elementos do conjunto 𝐴𝑟𝑣𝐵𝑖𝑛(ℕ ): 〈 〉, 〈〈 〉, 0, 〈 〉〉, 〈〈〈 〉, 1, 〈 〉〉, 0, 〈〈 〉, 2, 〈 〉〉〉 

--- end of page.page_number=9 ---
