---
entry_id: "formalizacaoalgoritmos-recursao"
title: "Formalizacaoalgoritmos Recursao"
backend: "pymupdf4llm"
source_pdf: "raw/pdfs/material-de-aula/formalizacaoalgoritmos-recursao.pdf"
page_range: "1-8"
---
## **Métodos Formais** 

## **Prof. Júlio Machado** 

## **Formalizando a Noção de Algoritmo Via Equações Recursivas** 

## **1. Introdução** 

Nosso objetivo é definir uma maneira de formalizar a noção de algoritmo de maneira a permitir, futuramente, a análise e prova de propriedades funcionais sobre estes algoritmos. Essa formalização se dará, inicialmente, na forma de equações recursivas, um modelo matemático adequado aos nossos objetivos. 

## **2. Um primeiro algoritmo** 

Supondo que a soma de dois valores inteiros é a única operação aritmética que um determinado agente computacional é capaz de executar (lembre-se que a operação de subtração pode ser vista como uma soma de um número negativo), vamos analisar um algoritmo para multiplicar dois números inteiros positivos (de forma equivalente dois números naturais). 

Dadas as restrições do agente computacional, uma forma de computar a multiplicação entre dois números inteiros (𝑚× 𝑛, 𝑚≥0, 𝑛≥0) é a que segue: 

|5 *3|=|5 * 3 + 0||4 * 4|=|4 * 4 + 0|
|---|---|---|---|---|---|---|
||=|4 * 3 + 3|||=|3 * 4 + 4|
||=|3 * 3 + 6|||=|2 * 4 + 8|
||=|2 * 3 + 9|||=|1 * 4 + 12|
||=|1 * 3 + 12|||=|0 * 4 + 16|
||=|0 * 3 + 15|||=|16|
||=|15|||||



Note que o exemplo acima permite intuir um algoritmo de multiplicação baseado apenas em somas sucessivas. Esse algoritmo pode ser escrito em língua natural como segue: 

- Entrada: 𝑚, 𝑛 ∈ ℕ 

- Saída: 𝑚× 𝑛 ∈ ℕ 

1. Colocar o valor de _a_ igual a zero; 

2. Enquanto m > 0, repetir os passos 2.1 e 2.2; 

   - 2.1. Adicionar _n_ ao valor de _a_ ; 

   - 2.2. Subtrair 1 do valor de _m_ ; 

3. A resposta é o valor de _a_ ; 

4. Parar. 

--- end of page.page_number=1 ---

Esse algoritmo satisfaz a todas as propriedades que permitem classificar um procedimento como um algoritmo (coleção ordenada de operações, não ambíguas, efetivamente computáveis, produzem um resultado e termina em um tempo finito). 

## **3. Algoritmos especificações equacionais** 

Existem várias formas de formalizar o processo intuitivo para a multiplicação de dois números apresentado na seção 2. Utilizaremos aqui funções recursivas definidas por equações. 

Uma especificação equacional de uma função 𝑓: 𝐴⟶𝐵 é dada por equações da forma 

## 𝑓(𝑥) = 𝑒 

onde a variável _x_ (argumento da função) pode ocorrer 0 ou mais vezes na expressão _e_ . Se na expressão _e_ houver uma ou mais ocorrências de _f_ , então _f_ é dita recursiva. Funções definidas por equações são avaliadas por substituição e simplificação. Se 𝑎 ∈𝐴 , então 𝑓(𝑎) é avaliada da seguinte forma: substituir todas as ocorrências de _x_ em _e_ por _a_ . A notação para esta operação é representada como 

## 𝑒[𝑥→𝑎] 

A utilização de equações recursivas é a maneira pela qual podemos repetir sequências de ações em um laço. 

Exemplo: algoritmo de multiplicação formalizado usando equações recursivas 

𝑚𝑢𝑙𝑡: ℕ× ℕ→ℕ 𝑚𝑢𝑙𝑡(⟨𝑚, 𝑛⟩) = 𝑚𝑢𝑙𝑡𝑎𝑐𝑐(⟨𝑚, 𝑛, 0⟩)                                         〈1〉 onde 𝑚𝑢𝑙𝑡𝑎𝑐𝑐: ℕ× ℕ× ℕ→ℕ 𝑚𝑢𝑙𝑡𝑎𝑐𝑐(〈0, 𝑦, 𝑎〉) = 𝑎                                                                〈2〉 𝑚𝑢𝑙𝑡𝑎𝑐𝑐(〈𝑥+ 1, 𝑦, 𝑎〉) = 𝑚𝑢𝑙𝑡𝑎𝑐𝑐(〈𝑥, 𝑦, 𝑎+ 𝑦〉)                〈3〉 

Observações: 

- _multacc_ é uma função auxiliar que só é conhecida por _mult_ e não pode ser usada diretamente; 

- _mult_ é indiretamente recursiva; 

- as variáveis são locais às equações; 

- as linhas <2> e <3> são mutuamente exclusivas; 

--- end of page.page_number=2 ---

## **4. Tipos de recursão** 

Uma função _f_ é dita recursiva na cauda se os resultados de quaisquer chamadas de _f_ são usados imediatamente como resultado de _f_ , sem quaisquer computações adicionais. Desta forma, em uma definição recursiva na cauda a recursão é usada simplesmente para chamar a “mesma função” só que com argumentos diferentes. 

As funções recursivas na cauda são uma subclasse das funções recursivas normais. O uso de funções recursivas na cauda vem do fato de que elas podem ser traduzidas diretamente para laços de repetição em algoritmos descritos no paradigma imperativo. 

Exemplo: algoritmo para calcular a função potência 

|**Versão recursiva convencional**|**Versão recursiva na cauda**|
|---|---|
|𝑝𝑜𝑡: ℕ× ℕ→ℕ<br>𝑝𝑜𝑡(〈𝑏, 𝑝〉) = 1, 𝑠𝑒 𝑝= 0<br>𝑝𝑜𝑡(〈𝑏, 𝑝〉) = 𝑏× 𝑝𝑜𝑡(〈𝑏, 𝑝−1〉), 𝑠𝑒 𝑝> 0|𝑝𝑜𝑡: ℕ× ℕ→ℕ<br>𝑝𝑜𝑡(〈𝑏, 𝑝〉) = 𝑝𝑜𝑡𝐴𝑢𝑥(〈𝑏, 𝑝, 1〉)<br>onde<br>𝑝𝑜𝑡𝐴𝑢𝑥: ℕ× ℕ× ℕ→ℕ<br>𝑝𝑜𝑡𝐴𝑢𝑥(〈𝑏, 𝑝, 𝑎〉) = 𝑎, 𝑠𝑒 𝑝= 0<br>  𝑝𝑜𝑡𝐴𝑢𝑥(〈𝑏, 𝑝, 𝑎〉)=𝑝𝑜𝑡𝐴𝑢𝑥(〈𝑏, 𝑝−1, 𝑎∗𝑏〉), 𝑠𝑒 𝑝> 0|



## **5. Computação como uma sequência de estados** 

Até agora vimos que um procedimento pode ser descrito como uma sequência de passos. Durante a execução desta sequência, o estado da computação é definido pelo conjunto dos valores de suas variáveis. Por exemplo, no algoritmo: 

𝑚𝑢𝑙𝑡: ℕ× ℕ→ℕ 𝑚𝑢𝑙𝑡(〈𝑚, 𝑛〉) = 𝑚𝑢𝑙𝑡𝑎𝑐𝑐(〈𝑚, 𝑛, 0〉)                                             (1) onde 

𝑚𝑢𝑙𝑡𝑎𝑐𝑐: ℕ× ℕ× ℕ→ℕ 𝑚𝑢𝑙𝑡𝑎𝑐𝑐(〈0, 𝑦, 𝑎〉) = 𝑎                                                                   (2) 𝑚𝑢𝑙𝑡𝑎𝑐𝑐(〈𝑥+ 1, 𝑦, 𝑎〉) = 𝑚𝑢𝑙𝑡𝑎𝑐𝑐(〈𝑥, 𝑦, 𝑎+ 𝑦〉)                   (3) 

Podemos determinar o estado da computação, a qualquer momento, consultando o valor das variáveis _x_ , _y_ e _a_ como segue (ao lado de cada chamada está indicada a regra aplicada e a forma como os valores foram substituídos): 

mult(5,3) = multacc(5,3,0) (1, [𝑚→5, 𝑛→3]) = multacc(4,3,3) (3, [𝑥→5, 𝑦→3, 𝑎→0]) = multacc(3,3,6) (3, [𝑥→4, 𝑦→3, 𝑎→3]) = multacc(2,3,9) (3, [𝑥→3, 𝑦→3, 𝑎→6]) = multacc(1,3,12) (3, [𝑥→2, 𝑦→3, 𝑎→9]) = multacc(0,3,15) (3, [𝑥→1, 𝑦→3, 𝑎→12]) = 15 (2, [𝑥→0, 𝑦→3, 𝑎→15]) 

--- end of page.page_number=3 ---

Uma forma equivalente de descrever o algoritmo _multacc_ é através da descrição da mudança dos valores das variáveis, que normalmente é chamada de estado da computação. Neste caso, o estado pode ser representado por uma tripla 𝑠: ℕ× ℕ× ℕ≜〈𝑥, 𝑦, 𝑎〉 . 

Assim, executando o algoritmo 𝑚𝑢𝑙𝑡 com os valores 5 e 3 teremos como resultado a seguinte sequência de estados para 𝑚𝑢𝑙𝑡𝑎𝑐𝑐 (note que as tuplas de valores que representam os estados da computação estão indicadas entre “ 〈 〉 ” e os sucessivos estados separados por “ → ”): 

## 〈5,3,0〉→〈4,3,3〉→〈3,3,6〉→〈2,3,9〉→〈1,3,12〉→〈0,3,15〉 

Assumindo que 𝑠0 = 〈5,3,0〉 é o estado inicial e 𝑠5 = 〈0,3,15〉 é o estado final da computação desejada, é possível observar que a transição de estado é definida pela regra: 

〈𝑥, 𝑦, 𝑎〉→〈𝑥−1, 𝑦, 𝑎+ 𝑦〉 

|**Estados**|**Variáveis**|
|---|---|
|𝑠0 =〈𝑥, 𝑦, 0〉|〈𝑥0, 𝑦0, 𝑎0〉|
|𝑠1 =〈𝑥−1, 𝑦, 𝑦〉|〈𝑥1, 𝑦1, 𝑎1〉|
|𝑠2 =〈𝑥−2, 𝑦, 𝑦+ 𝑦〉|〈𝑥2, 𝑦2, 𝑎2〉|
|...|...|
|𝑠𝑘=〈0, 𝑦, Σ𝑦𝑘<br>0<br>𝑘<br>〉|〈𝑥𝑘, 𝑦𝑘,𝑎𝑘〉|



O estado s0 representa o estado inicial da computação e o estado _sk_ , o estado final. Para 𝑗 cada 𝑗= 0. . . 𝑘, 𝑠𝑗 = 〈𝑥−𝑗, 𝑦, 0Σ𝑦𝑗〉 é o estado após o _j_ -ésimo passo de computação. 

Note que essa sequência de estados é resultado da aplicação das regras na seguinte sequência: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/formalizacaoalgoritmos-recursao/formalizacaoalgoritmos-recursao.pdf-0004-08.png)


A aplicação recursiva da regra (3) denota um laço ou repetição de instruções que irá ocorrer até que a condição de parada da regra (2) ocorra. Cada aplicação da regra (3) corresponde a uma iteração do laço do algoritmo descrito anteriormente. 

Note que analisando o estado da computação a cada iteração do laço conseguimos definir uma asserção (uma afirmação) a respeito da evolução destes estados durante as sucessivas iterações. No caso é possível deduzir que: 


![](C:/Users/Humberto/Desktop/MetodosFormaisClaude/metodos_formais/staging/assets/inline-images/formalizacaoalgoritmos-recursao/formalizacaoalgoritmos-recursao.pdf-0004-11.png)


Onde temos os valores iniciais de _m_ e _n_ , e _xk_ , _yk_ e _ak_ são os valores das variáveis após a iteração _k_ , isto é, após 𝑘∈ℕ repetições do laço. Esta asserção é verdadeira no início quando 𝑥= 5, 𝑦= 3, 𝑎= 0 e continua sendo verdadeira durante todas as iterações do laço. Dito de outra forma, esta asserção continua sendo **invariavelmente verdadeira** durante todas 

--- end of page.page_number=4 ---

as iterações e ainda será verdadeira após a última iteração. Esta **asserção invariante** expressa a essência deste procedimento computacional (algoritmo) e também é chamada de invariante de laço, ou nesse caso, de invariante da recursão. 

No exemplo apresentado o invariante se confunde com a própria chamada recursiva, porém, nem sempre é tão direto. 

Observe a tabela a seguir: 

|**Estados**|**Invariante**|
|---|---|
|𝑠0 =〈5,3,0〉=〈𝑥0, 𝑦0, 𝑎0〉|5×3=5×3 + 0|
|𝑠1 =〈4,3,3〉=〈𝑥1, 𝑦1, 𝑎1〉|5×3= 4 ×3 + 3|
|𝑠2 =〈3,3,6〉=〈𝑥2, 𝑦2, 𝑎2〉|5×3=3×3 + 6|
|𝑠3 =〈2,3,9〉=〈𝑥3, 𝑦3, 𝑎3〉|5×3= 2 ×3 + 9|
|𝑠4 =〈1,3,12〉=〈𝑥4, 𝑦4, 𝑎4〉|5×3=1×3 + 12|
|𝑠5 =〈0,3,15〉=〈𝑥5, 𝑦5, 𝑎5〉|5×3=0×3 + 15|



Entender um algoritmo como uma sequência de estados não apenas facilita a compreensão da ideia de invariante como permite uma visão diferente da tradicional (sequência de passos). Dispor de duas formas para analisar um mesmo objeto fornece mais ferramentas para tratá-lo e uma compreensão mais profunda do mesmo. 

Pode-se definir outras invariantes para o algoritmo de multiplicação. Por exemplo: 

- ∀𝑘: ℕ. 𝑥𝑘 ≥0 ⋀𝑦𝑘 ≥0 

- ∀𝑘: ℕ. 𝑥0 ≥𝑦𝑘 

- ∀𝑘: ℕ. 𝑥𝑘 ≥𝑥𝑘+1 

Muitos asserções são invariante para uma computação em particular. Algumas ajudam a entender o problema, outras não. 

Diz-se que uma **invariante é adequada** se e somente se ela é uma proposição que expressa uma relação em termos do que pretendemos com uma determinada computação, isto é, se a invariante tem a forma 

## 𝐺= 𝐸 

Onde _G_ é o objetivo (do inglês _goal_ ) da computação e _E_ é uma expressão que usa valores do estado corrente. 

No caso do algoritmo da multiplicação temos: 

𝐺≜𝑚× 𝑛 

- 𝐸≜𝑥𝑘 × 𝑦𝑘 + 𝑎𝑘, 𝑘∈ℕ 

--- end of page.page_number=5 ---

## **6. Máquina de estados** 

Uma máquina de estados é um modelo abstrato adequado para um algoritmo cuja computação se dá passo a passo. A seguir será definido mais formalmente a noção apresentada no capítulo anterior. 

Formalmente, uma máquina de estados é definida por: 

- Um conjunto de estados 𝑆 ; 

- Uma relação de transição entre estados dada por uma relação binária →⊆𝑆× 𝑆 

- Um estado inicial 𝑠0 ∈𝑆 . 

A execução de um algoritmo/programa é representada pela máquina de estado onde, a partir de um estado inicial, os comandos do programa induzem as transições de estado da máquina. A sequência de estados obtidos a partir do estado inicial é um modelo que representa a computação realizada. 

De maneira mais formal, uma execução de uma máquina de estados (ou traço, do inglês _trace_ ) é uma sequência (possivelmente infinita) de estados tais que: 

- Começa com o estado inicial 𝑠0; 

- Se 𝑠 e 𝑠′ são estados consecutivos na sequência, então existe uma transição 𝑠→𝑠′ entre os dois estados. 

Por fim, diz-se que um estado é alcançável se ele aparece em uma sequência que corresponde a uma possível execução da máquina de estados. 

## **7. Completando a especificação formal de algoritmos** 

Observe o algoritmo que segue que decrementa um número natural de uma unidade: 

𝑑𝑒𝑐𝑁𝑎𝑡: ℕ→ℕ 𝑑𝑒𝑐𝑁𝑎𝑡(𝑚) = 𝑚 −1 

O que acontece se aplicamos essa função sobre o valor zero? 

Note que a função _decNat_ é uma função parcial que não está definida para o valor zero. Se for aplicada com este valor irá cair em um estado de indefinição. 

Existem duas formas usuais de contornar este problema: 

a) Prever todos os casos no corpo da função: 

𝑑𝑒𝑐𝑁𝑎𝑡: ℕ→ℕ 𝑑𝑒𝑐𝑁𝑎𝑡(0) = 0 𝑑𝑒𝑐𝑁𝑎𝑡(𝑚) = 𝑚 − 1, 𝑠𝑒 𝑚> 0 

--- end of page.page_number=6 ---

- b) Especificar formalmente quais são as condições nas quais a função se aplica, isto é, quais são as pré-condições de aplicação da função: 

𝑑𝑒𝑐𝑁𝑎𝑡: ℕ→ℕ 𝑟𝑒𝑞𝑢𝑒𝑟: 𝑚≥1 𝑑𝑒𝑐𝑁𝑎𝑡(𝑚) = 𝑚 − 1 

Note que neste exemplo em particular o custo de especificar a pré-condição é o mesmo de prever todas as possibilidades no corpo da função. Em situações mais complexas, porém, não apenas é mais simples especificar as pré-condições de aplicação da função como a especificação das mesmas as torna mais explícitas e fáceis de verificar. Desta forma a especificação das pré-condições de aplicação de uma função é uma boa prática que deve ser observada sempre. 

- Outra boa prática é a especificação das pós condições, isto é, qual o resultado esperado a partir da aplicação da função. Além de explicitar o objetivo do algoritmo, facilita a comprovação de que os resultados são alcançados. 

Especificando-se as pré e pós condições nossa função _decNat_ fica da seguinte forma: 

𝑑𝑒𝑐𝑁𝑎𝑡: ℕ→ℕ 𝑟𝑒𝑞𝑢𝑒𝑟: 𝑚≥1 𝑔𝑎𝑟𝑎𝑛𝑡𝑒: 𝑑𝑒𝑐𝑁𝑎𝑡(𝑥) = 𝑥−1 𝑑𝑒𝑐𝑁𝑎𝑡(𝑚) = 𝑚 −1 

## **8. Conclusão** 

Nosso objetivo foi definir uma maneira de formalizar a noção de especificação de algoritmo de maneira a permitir, futuramente, a análise e prova de propriedades (tal como a correção e terminação) sobre estes algoritmos. Além disso, o conceito de correção de um algoritmo sempre será uma noção relativa, ou seja, um algoritmo é correto ou não sempre em relação à sua especificação. 

Uma pré-condição é uma asserção sobre a entrada que o usuário do algoritmo ou função deve respeitar. A pré-condição é uma asserção que deve ser sempre ser verdadeira antes da execução do algoritmo ou avaliação da função. Se esta condição for violada, o efeito do algoritmo ou função torna-se indefinido e, portanto, pode ou não executar aquilo para o qual foi projetado. 

Uma pós-condição é uma asserção sobre a saída do algoritmo ou função que é garantida pelo programador (ou quem projetou o algoritmo ou função). A pós-condição também é uma asserção que deve ser sempre verdadeira após a execução do algoritmo. 

Uma invariante é também uma asserção lógica que deve ser sempre verdadeira durante uma certa fase da execução do algoritmo (nos casos apresentados ela é verdadeira antes e 

--- end of page.page_number=7 ---

depois de um determinado algoritmo). Veremos na sequência que invariantes são fundamentais para a demonstração da correção de algoritmos. 

--- end of page.page_number=8 ---
