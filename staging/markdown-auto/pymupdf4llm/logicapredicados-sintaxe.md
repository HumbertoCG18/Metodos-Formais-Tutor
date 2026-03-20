---
entry_id: "logicapredicados-sintaxe"
title: "Logicapredicados Sintaxe"
backend: "pymupdf4llm"
source_pdf: "raw/pdfs/material-de-aula/logicapredicados-sintaxe.pdf"
page_range: "1-21"
---
![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0001-00.png)


## MÉTODOS FORMAIS 

Prof. Júlio Machado 

--- end of page.page_number=1 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0002-00.png)


## LÓGICA DE PREDICADOS 

Sintaxe 

Baseado nos materiais do Prof. Alfio Martini 

--- end of page.page_number=2 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0003-00.png)


## Sintaxe 

- Devido ao poder da lógica de predicados, sua linguagem é mais complexa do que a lógica proposicional 

- Conceitos: 

   - Assinaturas 

   - Termos (denotam objetos) 

   - Fórmulas (denotam valores lógicos) 

--- end of page.page_number=3 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0004-00.png)


## Assinatura 

- Assinaturas são declarações dos símbolos utilizados para a construção da linguagem específica 

- Dividida em duas partes: 

   - Assinatura para os termos 

   - Assinatura para as fórmulas 

--- end of page.page_number=4 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0005-00.png)


## Assinatura 

- Uma assinatura de primeira ordem para a lógica de predicados é uma tupla =(OP, R) onde 

   - OP = (C, F, ArF) tal que 

      - C é um conjunto de símbolos de constantes 

      - F é um conjunto de símbolos de funções 

      - ArF:F→ N é uma função de aridade que indica o número de argumentos 

      - de cada símbolo de função fF 

   - R = (P, ArP) tal que 

      - P é um conjunto de símbolos de predicados 

      - ArP:P→ N é uma função de aridade que indica o número de argumentos 

      - de cada símbolo de predicado pP 

- Para cada assinatura assumimos um conjunto contável de identificadores para variáveis X={x, y, z, ...} 

--- end of page.page_number=5 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0006-00.png)


## Exemplo 

- Assinatura para aritmética: 

   - OP=(C,F,ArF) 

      - C={0} 

      - F={add, mult, succ} 

      - ArF={add  2, mult  2, succ  1} 

   - R=(P,ArP) 

      - P={menor, meneq, maieq} 

      -    

      - ArP={menor 2, meneq 2, maieq 2} 

--- end of page.page_number=6 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0007-00.png)


## Exemplo 

- Assinatura para família: 

   - OP=(C,F,ArF) 

      - C={andre, beto, ana} 

      - F={} 

      - ArF={} 

   - R=(P,ArP) 

      - P={pai, mae, irmao} 

      - ArP={pai  2, mae  2, irmao  2} 

--- end of page.page_number=7 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0008-00.png)


## Termos 

- Termos são objetos sintáticos que servem para representar elementos do domínio de uma determinada aplicação 

- Um termo ou é uma constante, uma variável, ou então um símbolo de função aplicado a argumentos que são termos 

--- end of page.page_number=8 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0009-00.png)


## Termos 

- Seja OP=(C,F,ArF) uma assinatura para termos. O conjunto de termos sobre OP com variáveis X, denotado T(X), é definido pelas seguintes regras de construção (definição por indução): 

   - Toda variável 𝑣∈𝑋 é um termo 

   - Toda constante 𝑐∈𝐶 é um termo 

   - Se 𝑓∈𝐹 é uma função de aridade 𝑛 e 𝑡1, … , 𝑡𝑛 são termos, então 𝑓(𝑡1, … , 𝑡𝑛) é um termo 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0009-06.png)


--- end of page.page_number=9 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0010-00.png)


## Exemplo 

- Assinatura para aritmética: 

   - OP=(C,F,ArF) 

      - C={0} 

      - F={add, mult, succ} 

      - ArF={add  2, mult  2, succ  1} 

   - R=(P,ArP) 

      - P={menor, meneq, maieq} 

      -    

      - ArP={menor 2, meneq 2, maieq 2} 

- Termos sobre a assinatura: 

   - 0 

   - succ(0) 

   - succ(succ(0)) 

   - add(x,succ(0)) 

--- end of page.page_number=10 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0011-00.png)


## Fórmulas 

- Fórmulas são objetos sintáticos que denotam valores lógicos que determinados elementos do domínio possam ou não possuir 

   - Fórmulas atômicas são construídas com símbolos de predicados aplicados a termos, com um predicado especial de igualdade (=), além dos símbolos para verdade ( ⊤ ) e falsidade ( ⊥ ) 

   - Fórmulas compostas são construídas através das fórmulas atômicas, dos conectivos proposicionais e dos quantificadores universal () e existencial () 

--- end of page.page_number=11 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0012-00.png)


## Fórmulas 

- Seja R=(P, ArP) uma assinatura para fórmulas. O conjunto de fórmulas sobre R com variáveis X, denotado por Form(X) é definido pelas seguintes regras de construção (definição por indução): 

- Fórmulas atômicas: 

   - ⊥ e ⊤ são fórmulas 

   - Se 𝑡1 e 𝑡2 são termos, então 𝑡1 = 𝑡2 é uma fórmula 

   - Se 𝑝∈𝑃 é um predicado de aridade 𝑛 e 𝑡1, … , 𝑡𝑛 são termos, então 𝑝(𝑡1, … , 𝑡𝑛) é uma fórmula 

--- end of page.page_number=12 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0013-00.png)


## Fórmulas 

- Fórmulas atômicas: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0013-03.png)



![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0013-04.png)


--- end of page.page_number=13 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0014-00.png)


## Fórmulas 

- Seja R=(P, ArP) uma assinatura para fórmulas. O conjunto de fórmulas sobre R com variáveis X, denotado por Form(X) é definido pelas seguintes regras de construção (definição por indução): 

- : 

- Fórmulas compostas 

   - Se 𝐴 é uma fórmula, então (¬𝐴) é uma fórmula 

   - Se 𝐴 e 𝐵 são fórmulas, então (𝐴∧𝐵) , (𝐴∨𝐵) , (𝐴→𝐵) e (𝐴↔𝐵) também são fórmulas 

   - Se 𝐴 é uma fórmula e v ∈𝑋 , então (∀𝑣. 𝐴) e (∃𝑣. 𝐴) são fórmulas 

--- end of page.page_number=14 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0015-00.png)


## Fórmulas 

- : 

- Fórmulas compostas 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0015-03.png)


𝑏𝑜𝑝∈{→, ↔,∧,∨} 

--- end of page.page_number=15 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0016-00.png)


## Exemplo 

- Assinatura para aritmética: 

   - OP=(C,F,ArF) 

      - C={0} 

      - F={add, mult, succ} 

      - ArF={add  2, mult  2, succ  1} 

   - R=(P,ArP) 

      - P={menor, meneq, maieq} 

      -    

      - ArP={menor 2, meneq 2, maieq 2} 

- Fórmulas sobre a assinatura: 

   - menor(0,0) 

   - x=0 

   - maieq(x,add(x,succ(x))) 

   - ∀𝑥. (∃𝑦. 𝑚𝑎𝑖𝑜𝑟(𝑦, 𝑥)) 

--- end of page.page_number=16 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0017-00.png)


# LÓGICA DE PREDICADOS Formalização 

--- end of page.page_number=17 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0018-00.png)


## Formalização 

- Usaremos os quantificadores e também variáveis, que representam indivíduos no mundo que estamos representando 

- Os predicados e funções serão grafados com letras maiúsculas, enquanto que as variáveis deverão ser grafadas em letras minúsculas 

- Usaremos as letras do fim do alfabeto para designar as variáveis, por exemplo: x, y, z, etc 

- Usaremos as letras do início do alfabeto para designar indivíduos (constantes), por exemplo: a, b, c, etc 

--- end of page.page_number=18 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0019-00.png)


## Formalização 

- Exemplo: Jones é um ladrão 

   - Primeiro devemos criar um predicado para designar que algo é (ou possui a propriedade de ser) ladrão: 

      - L(x) = “x é um ladrão” 

   - Agora vamos usar uma letra do início do alfabeto para designar o indivíduo: 

      - j = “Jones” 

   - Formalizando: 

      - L(j) 

--- end of page.page_number=19 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0020-00.png)


## Formalização 

- Exemplo: Jones é um ladrão 

   - Domínio = conjunto de todas as pessoas 

   - OP=(C,F,ArF) 

      - C={j} 

      - F={} 

      - ArF={} 

   - R=(P,ArP) 

      - P={L} 

      -  

      - ArP={L 1} 

--- end of page.page_number=20 ---


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/logicapredicados-sintaxe/logicapredicados-sintaxe.pdf-0021-00.png)


## Formalização 

- Exemplo: Bob ama Cathy 

--- end of page.page_number=21 ---
