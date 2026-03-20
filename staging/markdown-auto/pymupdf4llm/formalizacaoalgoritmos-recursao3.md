---
entry_id: "formalizacaoalgoritmos-recursao3"
title: "Formalizacaoalgoritmos Recursao3"
backend: "pymupdf4llm"
source_pdf: "raw/pdfs/material-de-aula/formalizacaoalgoritmos-recursao3.pdf"
page_range: "1-2"
---
**Prof. Júlio Machado** 

## **Métodos Formais** 

## **Funções Recursivas sobre Árvores** 

## **1. Árvores polimórficas (definição indutiva)** 

Uma aplicação chave da recursão é a manipulação de árvores, já que as mesmas possuem uma definição inerentemente recursiva. 

Informalmente, uma definição recursiva para uma árvore binária pode ser: 

- Uma árvore vazia ou 

- Uma árvore composta por duas sub-árvores, sendo uma esquerda e outra direita. 

Uma definição formal pode ser dada através da definição de um conjunto indutivo para todas as árvores sobre um determinado tipo 𝜏 : 

𝑣𝑎𝑧𝑖𝑎 〈 〉∈𝐴𝑟𝑣𝐵𝑖𝑛(𝜏) 

𝐿∈𝐴𝑟𝑣𝐵𝑖𝑛(𝜏)     𝑅∈𝐴𝑟𝑣𝐵𝑖𝑛(𝜏), 𝑥∈𝜏 

𝑐𝑜𝑛𝑠 〈𝐿, 𝑥, 𝑅〉∈𝐴𝑟𝑣𝐵𝑖𝑛(𝜏) 

São exemplos de árvores de números naturais (elementos do conjunto 𝐴𝑟𝑣𝐵𝑖𝑛(ℕ ): 〈 〉, 〈〈 〉, 0, 〈 〉〉, 〈〈〈 〉, 1, 〈 〉〉, 0, 〈〈 〉, 2, 〈 〉〉〉 

## **2. Árvores polimórficas (equações recursivas)** 

Um exemplo de especificação recursiva é o seguinte algoritmo para o cálculo do número de nodos de uma árvore binária: 

𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠: 𝐴𝑟𝑣𝐵𝑖𝑛(𝜏) →ℕ 

𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈 〉) = 0                                                                                       (1) 

𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈𝐿, 𝑥, 𝑅〉) = 1 + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(𝐿) + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(𝑅)             (2) 

Um exemplo de computação para 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈〈〈 〉, 1, 〈 〉〉, 0, 〈〈 〉, 2, 〈 〉〉〉) : 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈〈〈 〉, 1, 〈 〉〉, 0, 〈〈 〉, 2, 〈 〉〉〉) = 1 + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈〈 〉, 1, 〈 〉〉) + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈〈 〉, 2, 〈 〉〉) (pela regra 2) = 1 + (1 + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈 〉) + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈 〉)) + (1 + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠( ) + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠( )) (pela regra 2) 

--- end of page.page_number=1 ---

- = 1 + (1 + 0 + 0) + (1 + 0 + 0) (pela regra 1) 

- = 3 (por aritmética) 

--- end of page.page_number=2 ---
