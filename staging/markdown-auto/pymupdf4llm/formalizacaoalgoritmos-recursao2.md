---
entry_id: "formalizacaoalgoritmos-recursao2"
title: "Formalizacaoalgoritmos Recursao2"
backend: "pymupdf4llm"
source_pdf: "raw/pdfs/material-de-aula/formalizacaoalgoritmos-recursao2.pdf"
page_range: "1-2"
---
## **Métodos Formais** 

## **Prof. Júlio Machado** 

## **Funções Recursivas sobre Listas** 

## **1. Introdução** 

Listas são um dos tipos de coleções mais básicos que podemos encontrar em diversas linguagens de programação. 

Nosso objetivo é definir um tipo de dado indutivo para representar listas e diversas operações sobre a mesma. Essa formalização se dará na forma de equações recursivas, um modelo matemático adequado aos nossos objetivos. 

## **2. Listas polimórficas (definição indutiva)** 

Um tipo indutivo para representar listas _polimórficas_ ou _genéricas_ , representada por 𝐿𝑖𝑠𝑡(𝜏) , onde 𝜏 é um conjunto arbitrário (representando os elementos que podem pertencer à lista), pode ser representado por dois construtores: 

- Um _construtor base_ para representar a lista vazia, representado pelo símbolo “ [ ] ”; 

- Um _construtor indutivo_ para representar a anexação de um elemento à esquerda de uma lista, representado pelo símbolo ” : ”. 

Assim, os elementos do tipo indutivo 𝐿𝑖𝑠𝑡(𝜏) são gerados pelas seguintes regras: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/formalizacaoalgoritmos-recursao2/formalizacaoalgoritmos-recursao2.pdf-0001-11.png)


A fim de facilitar a descrição de listas, vamos assumir a seguinte simplificação de sintaxe (em inglês, utiliza-se o temo _syntatic sugar_ ): 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/formalizacaoalgoritmos-recursao2/formalizacaoalgoritmos-recursao2.pdf-0001-13.png)


Note que a declaração utilizada para listas polimórficas implica, na verdade, em uma família de listas indexadas pelo tipo do parâmetro 𝜏 . Por exemplo: 

|de listas indexadas pelo tipo|do parâmetro𝜏. Por exemplo:|
|---|---|
|Instância|Elementos do Conjunto|
|𝐿𝑖𝑠𝑡(ℕ)|[], [0], [1], [0,1],...|
|𝐿𝑖𝑠𝑡(ℤ)|[], [-1], [-2,-1],...|
|𝐿𝑖𝑠𝑡(ℕ× ℤ)|[], [<2,0>], [<-1,-10>,<0,7>],...|



--- end of page.page_number=1 ---

## **3. Listas polimórficas (equações recursivas)** 

Como um exemplo de formalização recursiva sobre as listas, assuma uma função que recebe duas listas e retorna uma nova lista como resultado da concatenação das listas recebidas como parâmetros: 

𝑐𝑎𝑡: 𝐿𝑖𝑠𝑡(𝜏) × 𝐿𝑖𝑠𝑡(𝜏) →𝐿𝑖𝑠𝑡(𝜏) 

𝑐𝑎𝑡([ ], 𝑙) = 𝑙                                                (1) 𝑐𝑎𝑡(ℎ: 𝑇, 𝑙) = ℎ: 𝑐𝑎𝑡(𝑇, 𝑙)                             (2) Um exemplo de computação para 𝑐𝑎𝑡([1,2], [3,4]) : 

_cat_ ([1,2],[3,4])  = _cat_ (1:[2],[3,4]) (pela simplificação sintática) = 1: _cat_ ([2],[3,4]) (por 2) = 1: _cat_ (2:[],[3,4]) (pela simplificação sintática) = 1:2: _cat_ ([],[3,4]) (por 2) = 1:2:[3,4] (por 1) = [1,2,3,4] (pela simplificação sintática) 

--- end of page.page_number=2 ---
