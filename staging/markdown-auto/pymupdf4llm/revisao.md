---
entry_id: "revisao"
title: "Revisao"
backend: "pymupdf4llm"
source_pdf: "raw/pdfs/material-de-aula/revisao.pdf"
page_range: "1-22"
---
![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0001-00.png)


## MÉTODOS FORMAIS 

Prof. Júlio Machado 

--- end of page.page_number=1 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0002-00.png)


# CONJUNTOS E FUNÇÕES Revisão 

--- end of page.page_number=2 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0003-00.png)


## Conjuntos 

- Um conjunto é uma coleção de elementos 

- A={0,1} 

- B=={} é o conjunto vazio 

--- end of page.page_number=3 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0004-00.png)


## Conjuntos 

- Os elementos também são chamados de membros desse conjunto 

- A={0,1} 

- 0A, 0 é um elemento do conjunto A, 0 pertence a A 

- 2 A, 2 não é um elemento do conjunto A, 2 não pertence 

- a A 

--- end of page.page_number=4 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0005-00.png)


## Conjuntos 

- Conjuntos podem também ser descritos através de uma especificação das propriedades dos seus elementos 

-  

- A={x N/x<5}, onde N é o conjunto dos números naturais 

-  

- B={x N/x mod 2 = 0} 

--- end of page.page_number=5 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0006-00.png)


## Conjuntos 

- Um conjunto A é subconjunto de um conjunto B, AB, se cada elemento de A também é elemento de B 

- A={0,1,2} 

- N={0,1,2,3,...} 

- A N  

- A A  

- A, o vazio está contido em qualquer conjunto 

--- end of page.page_number=6 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0007-00.png)


## Conjuntos 

- União AB = {x / xA ou xB} 

   - A={0,1,2} 

   - B={0,2,4,6} 

   - A B={0,1,2,4,6} 

- Intersecção AB = {x / xA e xB} 

   - A={0,1,2} 

   - B={0,2,4,6} 

   - A B={0,2} 

- A e x 

- Diferença A-B ou A/B = {x / x B} 

   - A={0,1,2} 

   - B={0,2,4,6} 

   - A-B={1} 

--- end of page.page_number=7 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0008-00.png)


## Conjuntos 

- Conjunto das partes, ou conjunto potência, de um conjunto A, escrito (A), é o conjunto de todos os subconjuntos do conjunto A 

- A={0,1} 

- (A)={,{0},{1},{0,1}} 

--- end of page.page_number=8 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0009-00.png)


## Conjuntos 

- O produto cartesiano entre dois conjuntos A e B, escrito AxB, é o conjunto de todos os pares ordenados (a,b) tal A e bB 

- que a 

- A={0,1} 

- B={x,y} 

- AxB={(0,x),(0,y),(1,x),(1,y)} 

--- end of page.page_number=9 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0010-00.png)


## Conjuntos 

- O produto cartesiano generalizado A[n] , com n≥0 é definido como 

   - A[0] = {()} 

   - A[n+1] = AxA[n] 

- A={0,1} 

- A[3] =AxA[2] =AxAxA[1] =AxAxAxA[0] 

--- end of page.page_number=10 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0011-00.png)


## Relações 

- Uma relação binária R entre dois conjuntos A e B, escrita R:A↔B, é um subconjunto do produto cartesiano AxB 

   - Conjunto A é chamado de domínio 

   - Conjunto B é chamado de codomínio 

- A={0,1,2} 

- B={x,y} 

- R1={(0,x),(1,x),(2,y)} 

- R2={(0,x),(0,y),(1,y),(2,y)} 

- R3={(1,x)} 

--- end of page.page_number=11 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0012-00.png)


## Relações 

- Seja uma relação binária R:A↔B 

   -     

   - Domínio de definição de R é {x A | y B e (x,y) R} 

   -  x  

   - Imagem de R é {y B | A e (x,y) R} 

- A={0,1,2} 

- B={x,y} 

- R3={(1,x)} 

   - dd(R3)={1} 

   - img(R3)={x} 

--- end of page.page_number=12 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0013-00.png)


## Relações de Equivalência 

- Seja uma relação binária R:A↔A, diz-se que ela é uma relação de equivalência caso seja: 

   - Reflexiva: xA.(x,x)R 

   - Simétrica: xA, yA. (x,y)R  (y,x)R 

   - Transitiva: xA, yA, zA,. (x,y)R  (y,z)R  (x,z)R 

--- end of page.page_number=13 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0014-00.png)


## Relações de Ordem Parcial 

- Seja uma relação binária R:A↔A, diz-se que ela é uma relação de ordem parcial caso seja: 

   - Reflexiva: xA.(x,x)R 

   - Antissimétrica: xA, yA. (x,y)R  (y,x)R  x=y 

   - Transitiva: xA, yA, zA,. (x,y)R  (y,z)R  (x,z)R 

--- end of page.page_number=14 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0015-00.png)


## Relações de Ordem Total 

- Seja uma relação de ordem parcial R:A↔A, diz-se que ela é uma relação de ordem total caso : 

   - Qualquer elemento possa ser comparado, ou seja, xA, yA. (x,y)R  (y,x)R 

--- end of page.page_number=15 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0016-00.png)


## Funções Parciais 

- Uma função parcial f entre dois conjuntos A e B, escrito ⇀ 

- f:A B, é uma relação entre os conjuntos A e B tal que existe somente um par ordenado com a primeira componente em A 

   -   

   - Ou seja, se (x,y) f e (x,z) f então y=z 

- A={0,1,2} 

- B={x,y} 

- R1={(0,x),(1,x),(2,y)} é função 

   - Escreve-se R1(0)=x ou {0 ⟼ x}R1 

- R2={(0,x),(0,y),(1,y),(2,y)} não é função 

- R3={(1,x)} é função 

--- end of page.page_number=16 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0017-00.png)


## Funções Totais 

- Uma função total F:A→B é uma função parcial que é definida para todo elemento do conjunto de partida, ou seja, para todo elemento xA existem um elemento yB tal que F(x)=y 

--- end of page.page_number=17 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0018-00.png)


# LINGUAGENS FORMAIS Revisão 

--- end of page.page_number=18 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0019-00.png)


## Alfabeto e palavra 

- Um _**alfabeto**_ é um conjunto finito, não vazio, de elementos (símbolos) 

- Toda linguagem tem um alfabeto associado 

- Uma _**palavra**_ (cadeia de caracteres ou _string_ ) sobre um alfabeto  é uma sequência finita de símbolos justapostos 

- O _w w_ **tamanho de uma palavra** , representado por | |, é 

- o número de símbolos da palavra 

- A  **palavra vazia** ( ), é uma palavra sem símbolo, ou seja, 

- 

- | | = 0 

--- end of page.page_number=19 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0020-00.png)


## Linguagem sobre um alfabeto 

- Uma linguagem sobre um alfabeto  é um conjunto de palavras sobre  

-  como 

- Denotanto o conjunto de todas as palavras sobre *, dizemos que uma linguagem sobre  é qualquer subconjunto de * 

--- end of page.page_number=20 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0021-00.png)


## Linguagens artificiais 

## Uma linguagem artificial pode ser vista de duas formas: 

   - como uma _entidade livre_ , ou seja, sem qualquer significado 

   - associado (SINTAXE); 

   - como uma _entidade_ juntamente _com uma interpretação do seu_ SEMÂNTICA 

   - _significado_ ( ). 

- Métodos Formais lida com ambos aspectos das linguagens 

--- end of page.page_number=21 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0022-00.png)


## Hierarquia de Chomsky 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/revisao/revisao.pdf-0022-02.png)


--- end of page.page_number=22 ---
