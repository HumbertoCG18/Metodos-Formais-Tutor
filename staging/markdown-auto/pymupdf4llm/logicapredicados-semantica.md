---
entry_id: "logicapredicados-semantica"
title: "Logicapredicados Semantica"
backend: "pymupdf4llm"
source_pdf: "raw/pdfs/material-de-aula/logicapredicados-semantica.pdf"
page_range: "1-18"
---
![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0001-00.png)


## MÉTODOS FORMAIS 

Prof. Júlio Machado 

--- end of page.page_number=1 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0002-00.png)


## LÓGICA DE PREDICADOS 

Semântica 

Baseado nos materiais do Prof. Alfio Martini 

--- end of page.page_number=2 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0003-00.png)


## Motivação 

- Definir a noção de interpretação para uma assinatura da Lógica de Predicados 

- Aprender a calcular o valor semântico de termos e fórmulas 

## • Revisando... 

- Termos são elementos sintáticos que servem para representar elementos do domínio de uma determinada aplicação 

   - Símbolos de variáveis, constantes e funções 

- Fórmulas são elementos sintáticos que denotam certas propriedades booleanas que determinados elementos do domínio possam ter 

   - Símbolos de predicados, conectivos proposicionais, quantificador universal, quantificador existencial 

--- end of page.page_number=3 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0004-00.png)


## Interpretação 

- Os elementos básicos de uma interpretação para uma assinatura da lógica de predicados são: 

   - Um domínio, o qual é uma coleção não vazia de elementos, no qual as fórmulas serão avaliadas. 

   - Um elemento do domínio, para cada constante da assinatura. 

   - Um conjunto de funções sobre o domínio, uma para cada símbolo de função presente na assinatura. 

   - Um conjunto de relações sobre o domínio, uma para cada símbolo de predicado na assinatura. 

--- end of page.page_number=4 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0005-00.png)


## Interpretação 

- Seja =(OP, R) uma assinatura para a lógica de predicados 

- Uma interpretação I para  consiste de: 

   - Um conjunto não-vazio D de valores chamado de domínio 

   - Para cada símbolo constante c  C, um valor c[I]  D 

   -  :D[n] → 

   - Para cada símbolo de função f F, uma função f[I] D tal que ArF(f) = n 

   - Para cada símbolo de predicado p  P, uma relação p[I]  D[n] , tal que ArP(p) = n 

--- end of page.page_number=5 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0006-00.png)


## Exemplo 

- Assinatura para aritmética: 

   - OP=(C,F,ArF) 

      - C={0, 1, 2, ...} 

      - F={add, mult, ...} 

      - ArF={add2, mult2, ...} 

   - R=(P,ArP) 

      - P={menor, meneq, maieq, ...} 

      -    

      - ArP={menor 2, meneq 2, maieq 2, ...} 

--- end of page.page_number=6 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0007-00.png)


## Exemplo 

- Interpretação para assinatura aritmética: 

   - D = Naturais = {0,1,2,...} 

   - Constantes 

      - 0  0[I] =0 

      - 1  1[I] =1 

      - ... 

   - Funções 

      - add  add[I] :NxN→N, tal que add(x,y)=x+y 

      - ... 

## • Predicados 

- menor  menor[I] N[2] ={(0,1),(0,2),(0,3),...}=x<y 

- ... 

--- end of page.page_number=7 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0008-00.png)


## Ambiente 

- Uma interpretação permite atribuir o significado dos símbolos de constantes, funções e predicados 

- Para definir o valor de variáveis se utiliza o conceito de ambiente 

- Essencialmente, ambientes funcionam como uma tabela de consulta para os valores das variáveis 

- IMPORTANTE: ambiente define o valor das variáveis chamadas livres, ou seja, aquelas que não estão no contexto de um quantificador; uma variável que está no contexto de um quantificador é chamada de variável ligada 

--- end of page.page_number=8 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0009-00.png)


## Ambiente 

- Seja =(OP, R) uma assinatura para a lógica de predicados e X um conjunto de variáveis para a assinatura 

- Um ambiente é uma função a: X →D que atribui valores do domínio às variáveis 

--- end of page.page_number=9 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0010-00.png)


## Ambiente 

- Exemplo ambiente para assinatura aritmética: 

   - X ={x,y} 

   -   

   - a={x 0,y 1} 

--- end of page.page_number=10 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0011-00.png)


## Avaliação de Termos 

- Seja  uma assinatura, I uma interpretação para a assinatura, e a um ambiente 

- A função de avaliação de termos [.]a:T(X)→D é definida indutivamente por: 

   - Se o termo t é uma variável x, então [x]a=a(x) 

   - Se o termo t é uma constante c, então [c]a=c[I] 

   - Se o termo t é da forma f(t1,...,tn), então [f(t1,...,tn)]a=f[I] ([t1]a,..., [tn]a) 

--- end of page.page_number=11 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0012-00.png)


## Exemplo 

- Avaliação de termo na assinatura aritmética: 

   - [add(0,1)]a 

--- end of page.page_number=12 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0013-00.png)


## Avaliação de Fórmulas 

- Seja  uma assinatura, I uma interpretação para a assinatura, a um ambiente e A uma fórmula 

- 𝐼⊨ 𝐴 

- Defini-se a relação de satisfação 𝑎 por indução estrutural sobre A 

   - 𝐼⊨ 𝐴 

   - A expressão 𝑎 diz que a fórmula A é V na interpretação I e ambiente a 

   - A expressão 𝐼⊭𝑎 𝐴 diz que a fórmula A é F na interpretação I e ambiente a 

--- end of page.page_number=13 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0014-00.png)


## Avaliação de Fórmulas 

- Fórmulas atômicas: 

   - 𝐼⊨ ⊤ 𝑎 

   - 𝐼⊭𝑎 ⊥ 

   - 𝐼⊨𝑎 𝑝(𝑡1, … , 𝑡𝑛) se e somente se ([t1]a,...,[tn]a)p[I] 

   - 𝐼⊭𝑎 𝑝(𝑡1, … , 𝑡𝑛) se e somente se ([t1]a,...,[tn]a)p[I] 

   - 𝐼⊨ 𝑡 = 𝑡 𝑎 1 2 se e somente se [t1]a=[t2]a 

   - 𝐼⊭𝑎 𝑡1 = 𝑡2 se e somente se [t1]a[t2]a 

--- end of page.page_number=14 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0015-00.png)


## Avaliação de Fórmulas 

- Quantificadores: 

   - 𝐼⊨ ∀𝑥. 𝐵 se e somente se 𝐼⊨ 𝐵 D 𝑎 𝑎[𝑥↦𝑑] para todo d 

   - 𝐼⊭∀𝑥. 𝐵 se e somente se 𝐼⊭𝑎[𝑥↦𝑑] 𝐵 para algum dD 

   - 𝐼⊨ ∃𝑥. 𝐵 se e somente se 𝐼⊨ 𝐵 D 𝑎 𝑎[𝑥↦𝑑] para algum d 

   - 𝐼⊭𝑎 ∃𝑥. 𝐵 se e somente se 𝐼⊭𝑎[𝑥↦𝑑] 𝐵 para todo dD 

--- end of page.page_number=15 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0016-00.png)


## Avaliação de Fórmulas 

- Conectivos proposicionais: 

   - 𝐼⊨𝑎 ¬𝐵 se e somente se 𝐼⊭𝑎 𝐵 

   - 𝐼⊭𝑎 ¬𝐵 se e somente se 𝐼⊨𝑎 𝐵 

   - 𝐼⊨ 𝐵 se e somente se 𝐼⊨ 𝐵 ou 𝐼⊨ 𝐵 𝑎 1 ∨𝐵2 𝑎 1 𝑎 2 

   - 𝐼⊭𝑎 𝐵1 ∨𝐵2 se e somente se 𝐼⊭𝑎 𝐵1 e 𝐼⊭𝑎 𝐵2 

   - 𝐼⊨ 𝐵 se e somente se 𝐼⊨ 𝐵 e 𝐼⊨ 𝐵 𝑎 1 ∧𝐵2 𝑎 1 𝑎 2 

   - 𝐼⊭𝑎 𝐵1 ∧𝐵2 se e somente se 𝐼⊭𝑎 𝐵1 ou 𝐼⊭𝑎 𝐵2 

--- end of page.page_number=16 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0017-00.png)


## Avaliação de Fórmulas 

- Operadores proposicionais: 

   - 𝐼⊨𝑎 𝐵1 →𝐵2 se e somente se 𝐼⊭𝑎 𝐵1 ou 𝐼⊨𝑎 𝐵2 

   - 𝐼⊭𝑎 𝐵1 →𝐵2 se e somente se 𝐼⊨𝑎 𝐵1 e 𝐼⊭𝑎 𝐵2 

   - 𝐼⊨𝑎 𝐵1 ↔𝐵2 se e somente se ( 𝐼⊨𝑎 𝐵1 e 𝐼⊨𝑎 𝐵2 ) ou ( 𝐼⊭𝑎 𝐵1 e 

   - 𝐼⊭𝑎 𝐵2 ) 

   - 𝐼⊭𝑎 𝐵1 ↔𝐵2 se e somente se ( 𝐼⊨𝑎 𝐵1 e 𝐼⊭𝑎 𝐵2 ) ou ( 𝐼⊭𝑎 𝐵1 e 

   - 𝐼⊨ 𝐵 𝑎 2 ) 

--- end of page.page_number=17 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-semantica/logicapredicados-semantica.pdf-0018-00.png)


## Exemplo 

- Avaliação de fórmula na assinatura aritmética: 

   - [menor(1,add(1,1))]a 

   - [x.menor(add(x,1),x)]a 

--- end of page.page_number=18 ---
