---
entry_id: "logicaproposicional-semantica"
title: "Logicaproposicional Semantica"
backend: "pymupdf4llm"
source_pdf: "raw/pdfs/material-de-aula/logicaproposicional-semantica.pdf"
page_range: "1-25"
---
![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0001-00.png)


## MÉTODOS FORMAIS 

Prof. Júlio Machado 

--- end of page.page_number=1 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0002-00.png)


# LÓGICA PROPOSICIONAL Semântica 

Baseado nos materiais do Prof. Alfio Martini 

--- end of page.page_number=2 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0003-00.png)


## Semântica 

- O estudo da semântica da lógica proposicional consiste em atribuir valores verdade a fórmulas 

- Na lógica clássica há apenas dois valores: 

   - Verdadeiro – V 

   - Falso – F 

--- end of page.page_number=3 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0004-00.png)


## Interpretações 

- Os símbolos que não possuem significado fixo são chamados de variáveis proposicionais 

- Uma interpretação I para um conjunto de variáveis proposicionais  é uma função I:→B, onde B={V,F} 

- Exemplo: 

   - Se ={p,q}, então temos quatro interpretações possíveis: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0004-06.png)


--- end of page.page_number=4 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0005-00.png)


## Semântica dos Operadores 

• Os operadores proposicionais possuem um significado fixo, o qual pode ser definido através de uma tabelaverdade 

--- end of page.page_number=5 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0006-00.png)


## Semântica dos Operadores 

|𝒑|𝒒|¬𝒑|𝒑∧𝒒|𝒑∨𝒒|𝒑→𝒒|𝒑↔𝒒|
|---|---|---|---|---|---|---|
|V|V|F|V|V|V|V|
|V|F|F|F|V|F|F|
|F|V|V|F|V|V|F|
|F|F|V|F|F|V|V|



--- end of page.page_number=6 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0007-00.png)


## Fórmulas e Interpretações 

• Se _n_ é o número de variáveis proposicionais em uma fórmula, então temos _2[n]_ interpretações ou linhas na tabela-verdade correspondente à fórmula 

--- end of page.page_number=7 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0008-00.png)


## Fórmulas e Interpretações 

|𝒑|𝒒|𝒓|¬𝒑|¬𝒑→𝒒|(¬𝒑→𝒒)∨𝒓|
|---|---|---|---|---|---|
|V|V|V|F|V|V|
|V|V|F|F|V|V|
|V|F|V|F|V|V|
|V|F|F|F|V|V|
|F|V|V|V|V|V|
|F|V|F|V|V|V|
|F|F|V|V|F|V|
|F|F|F|V|F|F|



--- end of page.page_number=8 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0009-00.png)


## Modelos 

- Modelos são interpretações na qual uma fórmula (ou conjunto de fórmulas) é verdadeira (são verdadeiras) 

- Uma interpretação I:→B é um modelo para uma fórmula AP se somente se [A]I = V (ou seja, o valor da fórmula nessa interpretação é verdadeira) 

   - Nesse caso escrevemos 𝐼⊨𝐴 

- Uma interpretação I:→B não é um modelo para uma fórmula AP se somente se [A]I = F (ou seja, o valor da fórmula nessa interpretação é falsa) 

   - Nesse caso escrevemos 𝐼⊭𝐴 

--- end of page.page_number=9 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0010-00.png)


## Modelos 

- Uma interpretação I:→B é um modelo para um conjunto de fórmulas {A1,...,An} onde AiP se somente se [Ai]I = V para todo i=1,...,n 

   - Nesse caso escrevemos 𝐼⊨𝐴1, … , 𝐴𝑛 

- Uma interpretação I:→B não é um modelo para um conjunto de fórmulas {A1,...,An} onde AiP se somente se in 

- [Ai]I = F para algum 1 

   - Nesse caso escrevemos 𝐼⊭𝐴1, … , 𝐴𝑛 

--- end of page.page_number=10 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0011-00.png)


## Modelos 

- Sejam as seguintes interpretações: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0011-03.png)



![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0011-04.png)


• Verificar (via tabela-verdade): 𝐼1 ⊨(¬𝑝→𝑞) ∨𝑟 𝐼2 ⊭(¬𝑝→𝑞) ∨𝑟 

- Sejam as seguintes interpretações: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0011-07.png)



![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0011-08.png)


- Verificar (via tabela-verdade): 

𝐼1 ⊨𝑝→𝑞, ¬𝑝∨𝑞 𝐼2 ⊭𝑝→𝑞, ¬𝑝∨𝑞 

--- end of page.page_number=11 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0012-00.png)


## Classificação das Fórmulas 

- Uma fórmula A é uma tautologia (ou válida) se e somente se toda interpretação I:→B para A é modelo 

   - Ou seja, para toda interpretação I, [A]I=V 

   - Nesse caso escrevemos ⊨𝐴 

- Uma fórmula A é uma contradição (ou inválida) se e somente se nenhuma interpretação I:→B para A é modelo 

   - Ou seja, para toda interpretação I, [A]I=F 

   - Nesse caso escrevemos ⊭𝐴 

- Uma fórmula A é satisfatível se e somente se existe ao menos uma interpretação I:→B para A que é modelo 

   - Ou seja, existe pelo menos uma interpretação I, [A]I = V 

--- end of page.page_number=12 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0013-00.png)


## Classificação das Fórmulas 

- Verifique usando tabela-verdade: 

   - P P é tautologia 

   - PQ é satisfatível 

   - P P é contradição 

--- end of page.page_number=13 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0014-00.png)


## Classificação de Conjunto de Fórmulas 

- Seja {A1,...,An} um conjunto de fórmulas 

• O conjunto de modelos de {A1,...,An}, escrito _mod_ ({A1,...,An}), é definido como o conjunto de interpretações I:→B tal que I é modelo para cada fórmula do conjunto {A1,...,An} 

- Ou seja, os modelos de um conjunto de fórmulas são somente aquelas interpretações que satisfazem simultaneamente todas as fórmulas do conjunto 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0014-05.png)


--- end of page.page_number=14 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0015-00.png)


## Classificação de Conjunto de Fórmulas 

- Verifique usando tabelas-verdade quais os modelos de cada conjunto de fórmulas: 

- 𝑚𝑜𝑑({𝑝, 𝑝→𝑞, 𝑞}) 

- 𝑚𝑜𝑑({𝑝, ¬𝑝}) 

- 𝑚𝑜𝑑({𝑝→𝑞, 𝑞}) 

--- end of page.page_number=15 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0016-00.png)


## Classificação de Conjunto de Fórmulas 

- Um conjunto de fórmulas proposicionais {A1,...,An} é consistente quando existe pelo menos uma interpretação I:→B no conjunto de modelos _mod_ ({A1,...,An}) para as fórmulas 

- Um conjunto de fórmulas proposicionais {A1,...,An} é inconsistente quando não existe uma interpretação I:→B no conjunto de modelos _mod_ ({A1,...,An}) para as fórmulas, ou seja, _mod_ ({A1,...,An})= 

--- end of page.page_number=16 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0017-00.png)


## Classificação de Conjunto de Fórmulas 

- Verifique usando tabelas-verdade quais dos conjuntos de fórmulas abaixo são consistente e quais são inconsistentes: 

- 𝑝→𝑞, ¬𝑞 

- {𝑝→𝑞, ¬𝑞∨𝑟, 𝑝∧¬𝑟} 

- {(𝑝∨𝑞) →𝑟, ¬((¬𝑝∧¬𝑞) ∨𝑟)} 

--- end of page.page_number=17 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0018-00.png)


## Consequência Lógica/Semântica 

- Diz que uma fórmula proposicional _B_ é consequência lógica/semântica de um conjunto de fórmulas proposicionais {A1,...,An} se e somente se 𝑚𝑜𝑑({𝐴1, … , 𝐴𝑛}) ⊆𝑚𝑜𝑑({𝐵}) 

   - Nesse caso escrevemos 𝐴1, … , 𝐴𝑛 ⊨𝐵 

   - Ou seja, se para todos os valores nos quais todas as fórmulas de {A1,...,An} têm valor V, _B_ também tem valor V 

--- end of page.page_number=18 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0019-00.png)


## Consequência Lógica/Semântica 

## • ¬𝑝→𝑞, ¬𝑞⊨𝑝 

|𝒑|𝒒|¬𝑝|¬𝑝→𝑞|¬𝑞|
|---|---|---|---|---|
|V|V|F|V|F|
|V|F|F|V|V|
|F|V|V|V|F|
|F|F|V|F|V|



- 𝑚𝑜𝑑 ¬𝑝→𝑞 = {𝐼1, 𝐼2, 𝐼3} 

- = 

- 𝑚𝑜𝑑 ¬𝑞 I2, I4 

- 𝑚𝑜𝑑 ∩𝑚𝑜𝑑 ¬𝑝→𝑞 ¬𝑞 = {𝐼2} 

- 𝑚𝑜𝑑 𝑝 = {𝐼1, 𝐼2} 

- 𝐼2 ⊆{𝐼1, 𝐼2} , logo, é consequência semântica 

--- end of page.page_number=19 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0020-00.png)


## Conjectura e Consequência Lógica 

# • Uma conjectura é válida se e somente se a conclusão é consequência lógica/semântica das premissas 

--- end of page.page_number=20 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0021-00.png)


## Teoremas Importantes 

- Tautologia e Consequência Semântica: 

   - Seja A uma fórmula da Lógica Proposicional, então A é uma tautologia se e somente se 

- Teorema da Consequência: 

   - Sejam A1,...,An e B fórmulas da Lógica Proposicional, então temos 

      - 𝐴1, … , 𝐴𝑛 ⊨𝐵𝑠𝑠𝑒𝐴1 ∧⋯∧𝐴𝑛 →𝐵é 𝑢𝑚𝑎𝑡𝑎𝑢𝑡𝑜𝑙𝑜𝑔𝑖𝑎 

      - 𝐴1, … , 𝐴𝑛 ⊨𝐵𝑠𝑠𝑒𝐴1 ∧⋯∧𝐴𝑛 ∧¬𝐵é 𝑢𝑚𝑎𝑐𝑜𝑛𝑡𝑟𝑎𝑑𝑖çã𝑜 

𝐴1, … , 𝐴𝑛 ⊨𝐵𝑠𝑠𝑒{𝐴1, … , 𝐴𝑛, ¬𝐵} é 𝑖𝑛𝑐𝑜𝑛𝑠𝑖𝑠𝑡𝑒𝑛𝑡𝑒 

--- end of page.page_number=21 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0022-00.png)


## Equivalências 

- O conceito de equivalência entre fórmulas permite a abstração de certas diferenças sintáticas entre as fórmulas 

- Sejam A e B duas fórmulas da Lógica Proposicional 

-  

- Diz-se que A e B são equivalentes, denotado A B, se e somente se _mod_ ({A})= _mod_ ({B}) 

--- end of page.page_number=22 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0023-00.png)


## Equivalências 

## • Mostre que ¬𝑝∨𝑞≡𝑝→𝑞 

|𝒑|𝒒|¬𝒑|¬𝒑∨𝒒|𝒑→𝒒|
|---|---|---|---|---|
|V|V|F|V|V|
|V|F|F|F|F|
|F|V|V|V|V|
|F|F|V|V|V|



• A equivalência está correta pois = 𝑚𝑜𝑑 ¬𝑝∨𝑞 𝐼1, 𝐼3, 𝐼4 = 𝑚𝑜𝑑({𝑝→𝑞}) 

--- end of page.page_number=23 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0024-00.png)


## Equivalências 

- Mostre que 𝑝→𝑞≡¬𝑞→¬𝑝 

--- end of page.page_number=24 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicaproposicional-semantica/logicaproposicional-semantica.pdf-0025-00.png)


## Teoremas Importantes 

- Equivalência e Consequência Semântica: 

   - Sejam A e B fórmulas da Lógica Proposicional; então AB 

   - se e somente se 𝐴⊨𝐵 e 𝐵⊨𝐴 

   - se e somente se 𝐴↔𝐵 é uma tautologia 

--- end of page.page_number=25 ---
