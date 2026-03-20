Métodos Formais

Prof. Júlio Machado

## Formalizando a Noção de Algoritmo Via Equações Recursivas

## 1. Introdução

Nosso objetivo é definir uma maneira de formalizar a noção de algoritmo de maneira a permitir, futuramente, a análise e prova de propriedades funcionais sobre estes algoritmos. Essa  formalização  se  dará,  inicialmente,  na  forma  de  equações  recursivas,  um  modelo matemático adequado aos nossos objetivos.

## 2. Um primeiro algoritmo

Supondo  que  a  soma  de  dois  valores  inteiros  é  a  única  operação  aritmética  que  um determinado  agente  computacional é  capaz  de  executar  (lembre-se  que  a  operação  de subtração pode ser vista como uma soma de um número negativo), vamos analisar um algoritmo  para  multiplicar  dois  números  inteiros  positivos  (de  forma  equivalente  dois números naturais).

Dadas as restrições do agente computacional, uma forma de computar a multiplicação entre dois números inteiros (𝑚 × 𝑛, 𝑚 ≥ 0, 𝑛 ≥ 0) é a que segue:

| 5 *3   | =   | 5 * 3 + 0   | 4 * 4   | =   | 4 * 4 + 0   |
|--------|-----|-------------|---------|-----|-------------|
|        | =   | 4 * 3 + 3   |         | =   | 3 * 4 + 4   |
|        | =   | 3 * 3 + 6   |         | =   | 2 * 4 + 8   |
|        | =   | 2 * 3 + 9   |         | =   | 1 * 4 + 12  |
|        | =   | 1 * 3 + 12  |         | =   | 0 * 4 + 16  |
|        | =   | 0 * 3 + 15  |         | =   | 16          |
|        | =   | 15          |         |     |             |

Note que o exemplo acima permite intuir um algoritmo de multiplicação baseado apenas em somas sucessivas. Esse algoritmo pode ser escrito em língua natural como segue:

- Entrada:

𝑚,𝑛  ∈  ℕ

- Saída: 𝑚×𝑛  ∈  ℕ

1. Colocar o valor de a igual a zero;

2. Enquanto m &gt; 0, repetir os passos 2.1 e 2.2;

- 2.1. Adicionar n ao valor de a ;

- 2.2. Subtrair 1 do valor de m ;

3. A resposta é o valor de a ;

4. Parar.

Esse algoritmo satisfaz a todas as propriedades que permitem classificar um procedimento como  um  algoritmo  (coleção  ordenada  de  operações,  não  ambíguas,  efetivamente computáveis, produzem um resultado e termina em um tempo finito).

## 3. Algoritmos especificações equacionais

Existem  várias  formas  de  formalizar  o  processo  intuitivo  para  a  multiplicação  de  dois números  apresentado  na  seção  2.  Utilizaremos  aqui  funções  recursivas  definidas  por equações.

Uma especificação equacional de uma função 𝑓: 𝐴 ⟶ 𝐵 é dada por equações da forma

$$f ( x ) = e$$

onde a variável x (argumento da função) pode ocorrer 0 ou mais vezes na expressão e . Se na expressão e houver  uma ou mais ocorrências de f ,  então f é  dita  recursiva.  Funções definidas por equações são avaliadas por substituição e simplificação. Se 𝑎  ∈ 𝐴 , então 𝑓(𝑎) é avaliada da seguinte forma: substituir todas as ocorrências de x em e por a . A notação para esta operação é representada como

$$e [ x \rightarrow a ]$$

A utilização de equações recursivas é a maneira pela qual podemos repetir sequências de ações em um laço.

Exemplo: algoritmo de multiplicação formalizado usando equações recursivas

𝑚𝑢𝑙𝑡: ℕ × ℕ → ℕ

$$\ m u l t ( \langle m , n \rangle ) = m u l t a c c ( \langle m , x , 0 \rangle ) \quad \langle 1 \rangle$$

onde

𝑚𝑢𝑙𝑡𝑎𝑐𝑐: ℕ × ℕ × ℕ → ℕ

$$\ m u l t a c { c } ( \langle 0 , y , a \rangle ) = a$$

$$m u l t a c c ( \langle x + 1 , y , a \rangle ) = m u l t a c c ( \langle x , y , a + y \rangle ) \quad \langle 3 \rangle$$

## Observações:

- multacc é uma função auxiliar que só é conhecida por mult e não pode ser usada diretamente;
- mult é indiretamente recursiva;
- as variáveis são locais às equações;
- as linhas &lt;2&gt; e &lt;3&gt; são mutuamente exclusivas;

## 4. Tipos de recursão

Uma função f é dita recursiva na cauda se os resultados de quaisquer chamadas de f são usados imediatamente como resultado de f , sem quaisquer computações adicionais. Desta forma, em uma definição recursiva na cauda a recursão é usada simplesmente para chamar a 'mesma função' só que com argumentos diferentes.

As funções recursivas na cauda são uma subclasse das funções recursivas normais. O uso de funções recursivas na cauda vem do fato de que elas podem ser traduzidas diretamente para laços de repetição em algoritmos descritos no paradigma imperativo.

Exemplo: algoritmo para calcular a função potência

| Versão recursiva convencional                                              | Versão recursiva na cauda                                                                                                                         |
|----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| 𝑝𝑜𝑡:ℕ×ℕ→ℕ 𝑝𝑜𝑡(〈𝑏, 𝑝〉) = 1,𝑠𝑒 𝑝 = 0 𝑝𝑜𝑡(〈𝑏, 𝑝〉) = 𝑏×𝑝𝑜𝑡(〈𝑏,𝑝 -1〉), 𝑠𝑒 𝑝 > 0 | 𝑝𝑜𝑡:ℕ×ℕ→ℕ 𝑝𝑜𝑡(〈𝑏, 𝑝〉) = 𝑝𝑜𝑡𝐴𝑢𝑥(〈𝑏, 𝑝, 1〉) onde 𝑝𝑜𝑡𝐴𝑢𝑥:ℕ×ℕ×ℕ→ℕ 𝑝𝑜𝑡𝐴𝑢𝑥(〈𝑏, 𝑝, 𝑎〉) = 𝑎, 𝑠𝑒 𝑝 = 0 𝑝𝑜𝑡𝐴𝑢𝑥(〈𝑏, 𝑝, 𝑎〉) = 𝑝𝑜𝑡𝐴𝑢𝑥(〈𝑏,𝑝 -1,𝑎 ∗ 𝑏〉),𝑠𝑒 𝑝 > 0 |

## 5. Computação como uma sequência de estados

Até agora vimos que um procedimento pode ser descrito como uma sequência de passos. Durante a execução desta sequência, o estado da computação é definido pelo conjunto dos valores de suas variáveis. Por exemplo, no algoritmo:

$$\ m u l t \colon \mathbb { N } \times \mathbb { N } & \to \mathbb { N } \\ \ m u l t ( \langle m , n \rangle ) & = \ m u l t a c c ( \langle m , n , 0 \rangle ) \\ \text {ode} & \\ \ m u l t a c c \colon \mathbb { N } \times \mathbb { N } & \to \mathbb { N } \\ \ m u l t a c c ( \langle 0 , y , a \rangle ) & = a \\ \ m u l t a c c ( \langle x + 1 , y , a \rangle ) & = \ m u l t a c c ( \langle x , y , a + y \rangle )$$

Podemos determinar o estado da computação, a qualquer momento, consultando o valor das variáveis x , y e a como segue (ao lado de cada chamada está indicada a regra aplicada e a forma como os valores foram substituídos):

$$\begin{array} { r l r } { \quad m u l t ( 5 , 3 ) = } & { \quad m u t a c ( 5 , 3 , 0 ) \ ( 1 , [ m \rightarrow 5 , n \rightarrow 3 ] ) } \\ & { = } & { \quad m u t a c ( 4 , 3 , 3 ) \ ( 3 , [ x \rightarrow 5 , y \rightarrow 3 , a \rightarrow 0 ] ) } \\ & { = } & { \quad m u t a c ( 3 , 3 , 6 ) \ ( 3 , [ x \rightarrow 4 , y \rightarrow 3 , a \rightarrow 3 ] ) } \\ & { = } & { \quad m u t a c ( 2 , 3 , 9 ) \ ( 3 , [ x \rightarrow 3 , y \rightarrow 3 , a \rightarrow 6 ] ) } \\ & { = } & { \quad m u t a c ( 1 , 3 , 1 2 ) \ ( 3 , [ x \rightarrow 2 , y \rightarrow 3 , a \rightarrow 9 ] ) } \\ & { = } & { \quad m u t a c ( 0 , 3 , 1 5 ) \ ( 3 , [ x \rightarrow 1 , y \rightarrow 3 , a \rightarrow 1 2 ] ) } \\ & { = } & { 1 5 } & { ( 2 , [ x \rightarrow 0 , y \rightarrow 3 , a \rightarrow 1 5 ] ) } \end{array}$$

Uma  forma  equivalente  de  descrever  o  algoritmo multacc é  através  da  descrição  da mudança dos valores das variáveis, que normalmente é chamada de estado da computação. Neste caso, o estado pode ser representado por uma tripla 𝑠: ℕ × ℕ × ℕ ≜ 〈𝑥, 𝑦, 𝑎〉 .

Assim,  executando  o  algoritmo 𝑚𝑢𝑙𝑡 com  os  valores  5  e  3  teremos  como  resultado  a seguinte  sequência  de  estados  para 𝑚𝑢𝑙𝑡𝑎𝑐𝑐 (note  que  as  tuplas  de  valores  que repres entam os estados da computação estão indicadas entre ' 〈 〉 ' e os sucessivos estados separados por ' → ' ):

$$\langle 5 , 3 , 0 \rangle \rightarrow \langle 4 , 3 , 3 \rangle \rightarrow \langle 3 , 3 , 6 \rangle \rightarrow \langle 2 , 3 , 9 \rangle \rightarrow \langle 1 , 3 , 1 2 \rangle \rightarrow \langle 0 , 3 , 1 5 \rangle$$

Assumindo  que 𝑠0 = 〈5,3,0〉 é  o  estado  inicial  e 𝑠5 = 〈0,3,15〉 é  o  estado  final  da computação desejada, é possível observar que a transição de estado é definida pela regra:

$$\langle x , y , a \rangle \rightarrow \langle x - 1 , y , a + y \rangle$$

| Estados                 | Variáveis        |
|-------------------------|------------------|
| 𝑠 0 = 〈𝑥, 𝑦, 0〉         | 〈𝑥 0 ,𝑦 0 ,𝑎 0 〉 |
| 𝑠 1 = 〈𝑥 -1,𝑦,𝑦〉        | 〈𝑥 1 ,𝑦 1 ,𝑎 1 〉 |
| 𝑠 2 = 〈𝑥 -2,𝑦,𝑦 +𝑦〉     | 〈𝑥 2 ,𝑦 2 ,𝑎 2 〉 |
| ...                     | ...              |
| 𝑠 𝑘 = 〈0, 𝑦, Σ𝑦 𝑘 0 𝑘 〉 | 〈𝑥 𝑘 ,𝑦 𝑘 ,𝑎 𝑘 〉 |

O estado s0 representa o estado inicial da computação e o estado sk , o estado final. Para cada 𝑗 = 0. . . 𝑘, 𝑠 𝑗 = 〈𝑥 - 𝑗, 𝑦, Σ𝑦𝑗 0 𝑗 〉 é o estado após o j -ésimo passo de computação.

Note  que  essa  sequência  de  estados  é  resultado  da  aplicação  das  regras  na  seguinte sequência:

$$( 3 ) \rightarrow ( 3 ) \rightarrow ( 3 ) \rightarrow ( 3 ) \rightarrow ( 3 ) \rightarrow ( 2 )$$

A aplicação recursiva da regra (3) denota um laço ou repetição de instruções que irá ocorrer até que a condição de parada da regra (2) ocorra. Cada aplicação da regra (3) corresponde a uma iteração do laço do algoritmo descrito anteriormente.

Note que analisando o estado da computação a cada iteração do laço conseguimos definir uma asserção (uma afirmação) a respeito da evolução destes estados durante as sucessivas iterações. No caso é possível deduzir que:

$$m \times n = x _ { k } \times y _ { k } + a _ { k } , k \in \mathbb { N }$$

Onde temos os valores iniciais de m e n ,  e xk , yk e ak são os valores das variáveis após a iteração k , isto é, após 𝑘 ∈ ℕ repetições do laço. Esta asserção é verdadeira no início quando 𝑥 = 5, 𝑦 = 3, 𝑎 = 0 e continua sendo verdadeira durante todas as iterações do laço. Dito de outra forma, esta asserção continua sendo invariavelmente verdadeira durante todas as  iterações  e  ainda  será  verdadeira  após  a  última  iteração.  Esta asserção  invariante expressa a essência deste procedimento computacional (algoritmo) e também é chamada de invariante de laço, ou nesse caso, de invariante da recursão.

No  exemplo  apresentado  o  invariante  se  confunde  com  a  própria  chamada  recursiva, porém, nem sempre é tão direto.

Observe a tabela a seguir:

| Estados                           | Invariante   |
|-----------------------------------|--------------|
| 𝑠 0 = 〈5,3,0〉 = 〈𝑥 0 ,𝑦 0 ,𝑎 0 〉  | 5×3 = 5×3+0  |
| 𝑠 1 = 〈4,3,3〉 = 〈𝑥 1 ,𝑦 1 ,𝑎 1 〉  | 5×3 = 4×3+3  |
| 𝑠 2 = 〈3,3,6〉 = 〈𝑥 2 ,𝑦 2 ,𝑎 2 〉  | 5×3 = 3×3+6  |
| 𝑠 3 = 〈2,3,9〉 = 〈𝑥 3 ,𝑦 3 ,𝑎 3 〉  | 5×3 = 2×3+9  |
| 𝑠 4 = 〈1,3,12〉 = 〈𝑥 4 ,𝑦 4 ,𝑎 4 〉 | 5×3 = 1×3+12 |
| 𝑠 5 = 〈0,3,15〉 = 〈𝑥 5 ,𝑦 5 ,𝑎 5 〉 | 5×3 = 0×3+15 |

Entender um algoritmo como uma sequência de estados não apenas facilita a compreensão da  ideia  de  invariante  como  permite  uma  visão  diferente  da  tradicional  (sequência  de passos). Dispor de duas formas para analisar um mesmo objeto fornece mais ferramentas para tratá-lo e uma compreensão mais profunda do mesmo.

Pode-se definir outras invariantes para o algoritmo de multiplicação. Por exemplo:

- ∀𝑘:ℕ.𝑥𝑘 ≥ 0⋀𝑦𝑘 ≥ 0
- ∀𝑘:ℕ.𝑥0 ≥ 𝑦𝑘
- ∀𝑘:ℕ.𝑥𝑘 ≥ 𝑥𝑘+1

Muitos asserções são invariante para uma computação em particular. Algumas ajudam a entender o problema, outras não.

Diz-se que uma invariante é adequada se e somente se ela é uma proposição que expressa uma relação em termos do que pretendemos com uma determinada computação, isto é, se a invariante tem a forma

$$G = E$$

Onde G é o objetivo (do inglês goal ) da computação e E é uma expressão que usa valores do estado corrente.

No caso do algoritmo da multiplicação temos:

𝐺 ≜ 𝑚 × 𝑛

$$E \triangle q x _ { k } \times y _ { k } + a _ { k } , k \in \mathbb { N }$$

## 6. Máquina de estados

Uma  máquina  de  estados  é  um  modelo  abstrato  adequado  para  um  algoritmo  cuja computação  se  dá  passo  a  passo.  A  seguir  será  definido  mais  formalmente  a  noção apresentada no capítulo anterior.

Formalmente, uma máquina de estados é definida por:

- Um conjunto de estados 𝑆 ;
- Uma relação de transição entre estados dada por uma relação binária →⊆ 𝑆 × 𝑆 ;
- Um estado inicial 𝑠0 ∈ 𝑆 .

A execução de um algoritmo/programa é representada pela máquina de estado onde, a partir de um estado inicial, os comandos do programa induzem as transições de estado da máquina.  A  sequência  de  estados  obtidos  a  partir  do  estado  inicial  é  um  modelo  que representa a computação realizada.

De maneira mais formal, uma execução de uma máquina de estados (ou traço, do inglês trace ) é uma sequência (possivelmente infinita) de estados tais que:

- Começa com o estado inicial 𝑠0 ;
- Se 𝑠 e 𝑠′ são estados consecutivos na sequência, então existe uma transição 𝑠 → 𝑠′ entre os dois estados.

Por  fim,  diz-se  que  um  estado  é  alcançável  se  ele  aparece  em  uma  sequência  que corresponde a uma possível execução da máquina de estados.

## 7. Completando a especificação formal de algoritmos

Observe o algoritmo que segue que decrementa um número natural de uma unidade:

$$\begin{bmatrix} d e c N a t \colon \mathbb { N } \to \mathbb { N } \\ d e c N a t ( m ) = m - 1 \end{bmatrix}$$

O que acontece se aplicamos essa função sobre o valor zero?

Note que a função decNat é uma função parcial que não está definida para o valor zero. Se for aplicada com este valor irá cair em um estado de indefinição.

Existem duas formas usuais de contornar este problema:

- a) Prever todos os casos no corpo da função:

$$\begin{bmatrix} d e c N a t \colon \mathbb { N } \to \mathbb { N } \\ d e c N a t ( 0 ) = 0 \\ d e c N a t ( m ) = m - 1 , s e \, m > 0 \end{bmatrix}$$

- b) Especificar formalmente quais são as condições nas quais a função se aplica, isto é, quais são as pré-condições de aplicação da função:

```
𝑑𝑒𝑐𝑁𝑎𝑡: ℕ → ℕ 𝑟𝑒𝑞𝑢𝑒𝑟: 𝑚 ≥ 1 𝑑𝑒𝑐𝑁𝑎𝑡(𝑚) = 𝑚 - 1
```

Note que neste exemplo em particular o custo de especificar a pré-condição é o mesmo de prever todas as possibilidades no corpo da função. Em situações mais complexas, porém, não apenas é mais simples especificar as pré-condições de aplicação da função como a especificação  das  mesmas  as  torna  mais  explícitas  e  fáceis  de  verificar.  Desta  forma  a especificação das pré-condições de aplicação de uma função é uma boa prática que deve ser observada sempre.

Outra boa prática é a especificação das pós-condições, isto é, qual o resultado esperado a partir  da  aplicação  da  função.  Além  de  explicitar  o  objetivo  do  algoritmo,  facilita  a comprovação de que os resultados são alcançados.

Especificando-se as pré e pós condições nossa função decNat fica da seguinte forma:

```
𝑑𝑒𝑐𝑁𝑎𝑡: ℕ → ℕ 𝑟𝑒𝑞𝑢𝑒𝑟: 𝑚 ≥ 1 𝑔𝑎𝑟𝑎𝑛𝑡𝑒: 𝑑𝑒𝑐𝑁𝑎𝑡(𝑥) = 𝑥 - 1 𝑑𝑒𝑐𝑁𝑎𝑡(𝑚) = 𝑚 - 1
```

## 8. Conclusão

Nosso objetivo foi definir uma maneira de formalizar a noção de especificação de algoritmo de maneira a permitir, futuramente, a análise e prova de propriedades (tal como a correção e terminação) sobre estes algoritmos. Além disso, o conceito de correção de um algoritmo sempre será uma noção relativa, ou seja, um algoritmo é correto ou não sempre em relação à sua especificação.

Uma pré-condição é uma asserção sobre a entrada que o usuário do algoritmo ou função deve respeitar. A pré-condição é uma asserção que deve ser sempre ser verdadeira antes da execução do algoritmo ou avaliação da função. Se esta condição for violada, o efeito do algoritmo ou função torna-se indefinido e, portanto, pode ou não executar aquilo para o qual foi projetado.

Uma pós-condição é uma asserção sobre a saída do algoritmo ou função que é garantida pelo programador (ou quem projetou o algoritmo ou função). A pós-condição também é uma asserção que deve ser sempre verdadeira após a execução do algoritmo.

Uma invariante é também uma asserção lógica que deve ser sempre verdadeira durante uma certa fase da execução do algoritmo (nos casos apresentados ela é verdadeira antes e depois  de  um  determinado  algoritmo).  Veremos  na  sequência  que  invariantes  são fundamentais para a demonstração da correção de algoritmos.
