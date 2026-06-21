<!-- EXEC_SUMMARY_START -->
## Sumário
> *Leia antes de varrer o arquivo. Vá direto à seção relevante para a pergunta do aluno.*

- **1. Introdução**
- **2. Um primeiro algoritmo**
- **3. Algoritmos como sequências de estados**
- **4. Máquina de estados**
- **5. Princípio da invariante**
- **6. Invariante de laço**
- **7. Um segundo algoritmo**
- **8. Um terceiro algoritmo**

<!-- EXEC_SUMMARY_END -->
{0}------------------------------------------------

# Invariantes de Laço
## 1. Introdução

Nosso objetivo é definir uma maneira de formalizar a noção de especificação de algoritmo de maneira a permitir, futuramente, a análise e prova de propriedades (tal como a correção) sobre estes algoritmos. Estes conceitos são chamados de pré-condições, pós-condições e invariantes. Além disso, o conceito de correção de um algoritmo sempre será uma noção relativa, ou seja, um algoritmo é correto ou não sempre em relação à sua especificação.

Uma pré-condição é uma condição sobre a entrada que o usuário do algoritmo ou função deve respeitar. A pré-condição é um predicado (expressão booleana) que deve ser sempre verdadeira antes da execução do algoritmo ou avaliação da função. Se esta condição for violada, o efeito do algoritmo ou função torna-se indefinido e, portanto, pode ou não executar aquilo para o qual foi projetado.

Uma pós-condição é a condição sobre a saída do algoritmo ou função que é garantida pelo programador (ou quem projetou o algoritmo ou função). A pós-condição também é uma asserção ou predicado que deve ser sempre verdadeira após a execução do algoritmo.

Uma invariante é também uma asserção lógica que deve ser sempre verdadeira durante uma certa fase da execução do algoritmo. Veremos na sequência que invariantes são fundamentais para a demonstração da correção de algoritmos.
## 2. Um primeiro algoritmo

Supondo que a soma de dois valores inteiros é a única operação aritmética que um determinado agente computacional é capaz de executar, vamos analisar um algoritmo para multiplicar dois números inteiros positivos (de forma equivalente dois números naturais).

Dadas as restrições do agente computacional, uma forma de computar a multiplicação entre dois números inteiros ( $m \geq 0, n \geq 0$ ) é a que segue:

|       |   |            |  |       |   |            |
|-------|---|------------|--|-------|---|------------|
| 5 * 3 | = | 5 * 3 + 0  |  | 4 * 4 | = | 4 * 4 + 0  |
|       | = | 4 * 3 + 3  |  |       | = | 3 * 4 + 4  |
|       | = | 3 * 3 + 6  |  |       | = | 2 * 4 + 8  |
|       | = | 2 * 3 + 9  |  |       | = | 1 * 4 + 12 |
|       | = | 1 * 3 + 12 |  |       | = | 0 * 4 + 16 |
|       | = | 0 * 3 + 15 |  |       | = | 16         |
|       | = | 15         |  |       |   |            |

{1}------------------------------------------------

Note que o exemplo acima permite intuir um algoritmo iterativo de multiplicação baseado apenas em somas sucessivas. Esse algoritmo pode ser escrito em língua natural como segue:

- $Mult: \mathbb{Z} \times \mathbb{Z} \rightarrow \mathbb{Z}$
- Requer:  $m \geq 0, n \geq 0$
- Garante:  $Mult(m, n) = m * n$
- 1. Colocar o valor de  $a$  igual a zero;
- 2. Enquanto  $m > 0$ , repetir os passos 2.1 e 2.2;
  - 2.1. Adicionar  $n$  ao valor de  $a$ ;
  - 2.2. Subtrair 1 do valor de  $m$  (subtrair equivale a somar -1);
- 3. A resposta é o valor de  $a$ ;
- 4. Parar.

Esse algoritmo satisfaz a todas as propriedades que permitem classificar um procedimento como um algoritmo (coleção ordenada de operações, não ambíguas, efetivamente computáveis, produzem um resultado e termina em um tempo finito).

As pré e pós condições foram anotadas com as palavras “Requer” e “Garante” na descrição do algoritmo.
## 3. Algoritmos como sequências de estados

Até agora vimos que um procedimento pode ser descrito como uma sequência de passos. Durante a execução desta sequência, o estado da computação é definido pelo conjunto dos valores de suas variáveis.

Por exemplo, no algoritmo da computação da soma, podemos determinar o estado da computação, a qualquer momento, consultando o valor das variáveis  $m$ ,  $n$  e  $a$  como segue:

| m | n | a  |
|---|---|----|
| 5 | 3 | 0  |
| 4 | 3 | 3  |
| 3 | 3 | 6  |
| 2 | 3 | 9  |
| 1 | 3 | 12 |
| 0 | 3 | 15 |

Neste caso, o estado da computação pode ser representado por uma tripla  $s: \mathbb{Z} \times \mathbb{Z} \times \mathbb{Z} \triangleq \langle m, n, a \rangle$ . Assim, executando o algoritmo  $Mult$  com os valores 5 e 3 teremos como resultado a seguinte sequência de estados (note que as tuplas de valores que representam os estados da computação estão indicadas entre “ $\langle \ \rangle$ ” e os sucessivos estados separados por “ $\rightarrow$ ”):

$$\langle 5, 3, 0 \rangle \rightarrow \langle 4, 3, 3 \rangle \rightarrow \langle 3, 3, 6 \rangle \rightarrow \langle 2, 3, 9 \rangle \rightarrow \langle 1, 3, 12 \rangle \rightarrow \langle 0, 3, 15 \rangle$$

Assumindo que  $s_0 = \langle 5, 3, 0 \rangle$  é o estado inicial e  $s_5 = \langle 0, 3, 15 \rangle$  é o estado final da computação desejada, é possível observar que a transição entre estados é definida pela regra:

$$\langle m, n, a \rangle \rightarrow \langle m - 1, n, a + n \rangle$$

{2}------------------------------------------------

| Estados                                                                 | Variáveis                       |
|-------------------------------------------------------------------------|---------------------------------|
| $s_0 = \langle m, n, 0 \rangle = \langle 5, 3, 0 \rangle$               | $\langle m_0, n_0, a_0 \rangle$ |
| $s_1 = \langle m - 1, n, n \rangle = \langle 4, 3, 3 \rangle$           | $\langle m_1, n_1, a_1 \rangle$ |
| $s_2 = \langle m - 2, n, n + n \rangle = \langle 3, 3, 6 \rangle$       | $\langle m_2, n_2, a_2 \rangle$ |
| ...                                                                     | ...                             |
| $s_k = \langle 0, n, {}^k_0\Sigma n \rangle = \langle 0, 3, 15 \rangle$ | $\langle m_k, n_k, a_k \rangle$ |

Note que analisando o estado da computação a cada iteração do laço conseguimos definir uma propriedade (uma asserção, uma afirmação) a respeito da evolução destes estados durante as sucessivas iterações. No caso é possível deduzir que:

$$m_0 \times n_0 = m_k \times n_k + a_k, k \in \mathbb{N}$$

Onde  $m_0, n_0$  são os valores iniciais de  $m$  e  $n$  e  $m_k, n_k$  e  $a_k$  são os valores de  $m, n$  e  $a$  após a iteração  $k$ , isto é, após  $k \in \mathbb{N}$  repetições do laço. Esta asserção é verdadeira no início quando  $m = 5, n = 3, a = 0$  e continua sendo verdadeira durante todas as iterações do laço. Dito de outra forma, esta asserção continua sendo invariavelmente verdadeira durante todas as iterações e ainda será verdadeira após a última iteração. Esta asserção invariante expressa a essência deste procedimento computacional iterativo e também é chamada de invariante de laço. Observe a tabela a seguir:

| Estados                                                          | Invariante                     |
|------------------------------------------------------------------|--------------------------------|
| $s_0 = \langle 5, 3, 0 \rangle = \langle m_0, n_0, a_0 \rangle$  | $5 \times 3 = 5 \times 3 + 0$  |
| $s_1 = \langle 4, 3, 3 \rangle = \langle m_1, n_1, a_1 \rangle$  | $5 \times 3 = 4 \times 3 + 3$  |
| $s_2 = \langle 3, 3, 6 \rangle = \langle m_2, n_2, a_2 \rangle$  | $5 \times 3 = 3 \times 3 + 6$  |
| $s_3 = \langle 2, 3, 9 \rangle = \langle m_3, n_3, a_3 \rangle$  | $5 \times 3 = 2 \times 3 + 9$  |
| $s_4 = \langle 1, 3, 12 \rangle = \langle m_4, n_4, a_4 \rangle$ | $5 \times 3 = 1 \times 3 + 12$ |
| $s_5 = \langle 0, 3, 15 \rangle = \langle m_5, n_5, a_5 \rangle$ | $5 \times 3 = 0 \times 3 + 15$ |
## 4. Máquina de estados

Uma máquina de estados é um modelo abstrato adequado para um algoritmo iterativo cuja computação se dá passo a passo. A seguir será definido mais formalmente a noção apresentada no capítulo anterior.

Formalmente, uma máquina de estados é definida por:

- Um conjunto de estados  $S$ ;
- Uma relação de transição entre estados dada por uma relação binária  $\rightarrow \subseteq S \times S$ ;
- Um estado inicial  $s_0 \in S$ .

A execução de um algoritmo/programa é representada pela máquina de estado onde, a partir de um estado inicial, as instruções do programa induzem as transições de estado da máquina. A sequência de estados obtida a partir do estado inicial é um modelo que representa uma determinada computação realizada.

De maneira mais formal, uma execução de uma máquina de estados (ou traço, do inglês *trace*) é uma sequência (possivelmente infinita) de estados tais que:

{3}------------------------------------------------

- Começa com o estado inicial  $s_0$ ;
- Se  $s$  e  $s'$  são estados consecutivos na sequência, então existe uma transição  $s \rightarrow s'$  entre os dois estados.

Por fim, diz-se que um estado é alcançável se ele aparece em uma sequência que corresponde a uma possível execução da máquina de estados.
## 5. Princípio da invariante

O Princípio da Invariante foi formulado por Robert W. Floyd em 1967. Resumidamente, ele é uma versão do Princípio da Indução especificamente criado para a construção de provas de propriedades sobre máquinas de estado.

Um dos usos mais importantes da indução na Ciência da Computação envolve provar que uma ou mais propriedades desejadas continuam a valer a cada passo de uma computação. Uma propriedade que é preservada através de uma série de passos de computação é chamada de invariante preservada. Formalmente, dada uma máquina de estados, um predicado  $P: S \rightarrow \mathbb{B}$  (onde  $\mathbb{B} = \{true, false\}$ ) sobre um estado da máquina é uma invariante preservada:

- Se  $P(s)$  é verdadeiro para um estado  $s$ ;
- E  $s \rightarrow s'$  é uma transição de estado da máquina;
- Então  $P(s')$  é verdadeiro para o estado  $s'$ .

O Princípio da Invariante diz que: “Se uma invariante preservada é verdadeira para o estado inicial, então ela é verdadeira para cada estado alcançável”. Ou seja:

- $P(s_0)$  é verdadeiro;
- $\forall s \in S. P(s) \wedge s \rightarrow s' \Rightarrow P(s')$ .

Em resumo, o Princípio da Invariante mostra como a indução no número de passos necessários para alcançar um determinado estado é aplicado ao conceito de invariante. Mostrar que uma propriedade vale para o estado inicial corresponde ao caso base da indução, e mostrar que a propriedade é uma invariante preservada corresponde ao passo de indução. Assim, quando se fala em invariante, estamos nos referindo realmente a uma hipótese de indução a ser provada pelo Princípio da Indução.
## 6. Invariante de laço

Na construção de algoritmos iterativos uma das invariantes de maior importância é a chamada invariante de laço conforme apresentada no exemplo da seção 3. Se focalizarmos a atenção a um “pedaço” de um algoritmo que corresponde a um laço de repetição, então estamos interessados em definir uma propriedade que demonstre uma relação entre os elementos do estado de uma computação que deve ser verdadeira antes de cada iteração do laço e que permanece verdadeira ao final da iteração do laço.

{4}------------------------------------------------

Observe onde se encontra a invariante de laço em um esquema para um algoritmo iterativo:

```

begin algoritmo
  <pré-condição algoritmo>
  instruções pré-laço
  loop
    <invariante de laço>
    exit when (condição de saída do laço)
    instruções do laço
  end loop
  instruções pós-laço
  <pós-condição algoritmo>
end algoritmo

```

Reescrevendo o algoritmo de soma de números naturais apresentado na seção 2 de acordo com esse esquema tem-se:

```

begin Mult(m,n)
  <m $\geq$ 0, n $\geq$ 0>
  a=0;
  loop
    <m $\geq$ 0, n $\geq$ 0>
    <m0 $\times$ n0 = mk $\times$ nk + ak, k $\in$ $\mathbb{N}$ >
    exit when (m=0)
    a=a+n;
    m=m-1;
  end loop
  return a;
  <a = m * n>
end

```
## 7. Um segundo algoritmo

No exemplo que segue, estamos interessados em um algoritmo eficiente para computar a potência de um número de números Naturais. O algoritmo utiliza uma técnica conhecida como “exponenciação rápida” ou “exponenciação por quadrados”. A definição recursiva de  $a^b$  a ser utilizada é a seguinte:

$$a^b = \begin{cases} 1 & \text{se } b = 0 \\ a \times (a^2)^{\frac{b-1}{2}} & \text{se } b \text{ é ímpar} \\ (a^2)^{\frac{b}{2}} & \text{se } b \text{ é par} \end{cases}$$

O algoritmo iterativo para o cálculo fica então:

{5}------------------------------------------------

```

begin Potencia(a,b)
  <true>
  c=a;
  i=b;
  r=1;
  loop
    <i $\geq$ 0, i $\leq$ b>
    <r * ci = ab>
    exit when (i=0)
    if (i é ímpar)
      r=r*c;
      i=i-1;
    c=c*c;
    i=i/2;
  end loop
  return r;
  <r = ab>
end

```

Define-se o estado como sendo  $s \triangleq \mathbb{N} \times \mathbb{N} \times \mathbb{N} = \langle c, i, r \rangle$  e o estado inicial  $\langle a, b, 1 \rangle$ . As seguintes sequências de estados demonstram os passos de computação para o cálculo de  $2^4$  e  $2^3$ :

| Estados                                                            | Invariante de Laço $r * c^i = a^b$ |
|--------------------------------------------------------------------|------------------------------------|
| $s_0 = \langle 2, 4, 1 \rangle = \langle c_0, i_0, r_0 \rangle$    | $1 \times 2^4 = 2^4$               |
| $s_1 = \langle 4, 2, 1 \rangle = \langle c_1, i_1, r_1 \rangle$    | $1 \times 4^2 = 2^4$               |
| $s_2 = \langle 16, 1, 1 \rangle = \langle c_2, i_2, r_2 \rangle$   | $1 \times 16^1 = 2^4$              |
| $s_3 = \langle 256, 0, 16 \rangle = \langle c_3, i_3, r_3 \rangle$ | $16 \times 256^0 = 2^4$            |

| Estados                                                          | Invariante de Laço $r * c^i = a^b$ |
|------------------------------------------------------------------|------------------------------------|
| $s_0 = \langle 2, 3, 1 \rangle = \langle c_0, i_0, r_0 \rangle$  | $1 \times 2^3 = 2^3$               |
| $s_1 = \langle 4, 1, 2 \rangle = \langle c_1, i_1, r_1 \rangle$  | $2 \times 4^1 = 2^3$               |
| $s_2 = \langle 16, 0, 8 \rangle = \langle c_2, i_2, r_2 \rangle$ | $8 \times 16^0 = 2^3$              |

Observe que a transição entre estados é dada pelo seguinte esquema:

$$\langle c, i, r \rangle \rightarrow \begin{cases} \langle c^2, i/2, r \rangle, & \text{se } i \neq 0 \text{ e } i \text{ é par} \\ \langle c^2, \frac{i-1}{2}, c * r \rangle, & \text{se } i \neq 0 \text{ e } i \text{ é ímpar} \end{cases}$$

A invariante preservada, que é a invariante de laço, é  $P(c, i, r)$  tal que:

$$r * c^i = a^b$$

{6}------------------------------------------------
## 8. Um terceiro algoritmo

Neste exemplo, estamos interessados em analisar um algoritmo que efetua uma busca binária sobre um array de elementos. Assume-se que o array possa ser indexado por posição, de 0 a tamanho do array -1.

Um algoritmo de busca binária pode ser descrito da seguinte forma:

*Inicia-se a busca por x examinando-se o elemento médio de um array ordenado de forma crescente. Se esse elemento é menor que x, então x deve estar na metade superior do array (se ele estiver realmente lá); se esse elemento é maior que x, então x deve estar na metade inferior do array (se ele estiver realmente lá). Continua-se a busca restringindo-se o espaço de comparação a um subarray correspondente à metade inferior ou superior do array. Termina-se quando se encontra o x, ou o tamanho do subarray chegou a zero, o que corresponde ao caso de x não estar no array.*

Uma possível especificação de pré e pós condições para tal algoritmo é:

- Pré:
  - O array está ordenado de forma crescente.
$$\forall i \in \mathbb{N}. 0 \leq i < \text{array.tamanho} \Rightarrow \text{array}[i] \leq \text{array}[i + 1]$$
- Pós:
  - Retorna valor < 0 se o elemento não estiver dentro do array.
$$\text{resultado} < 0 \Rightarrow (\forall i \in \mathbb{N}. 0 \leq i < \text{array.tamanho} \Rightarrow \text{array}[i] \neq x)$$
  - Retorna um índice que contém a posição do elemento (IMPORTANTE: a pós-condição não estabelece nenhuma condição adicional sobre o índice do elemento em relação a um array que contenha cópias do mesmo).
$$0 \leq \text{resultado} \Rightarrow \text{resultado} < \text{array.tamanho} \wedge \text{array}[\text{resultado}] = x$$

```
begin BuscaBinaria(array a, elemento x)
    <array está ordenado em ordem crescente >
    ?
    <retorna o índice do elemento no array, ou <0 caso contrário>
end algoritmo
```

Para a caracterização do subarray, utiliza-se duas variáveis *lo* e *hi*, que possuem o valor dos índices inferior e superior do subarray respectivamente. Para esta versão do algoritmo, as variáveis serão inicializadas com os valores 0 e *n*, de tal maneira que o subintervalo que define o subarray é [*lo*..*hi*), ou seja, inclui *lo* e exclui *hi*. Na discussão que segue *n* irá representar o tamanho do array. Veja um exemplo:

{7}------------------------------------------------

![Diagram of an array A with indices 0 to 10. The array contains the values [5, 7, 11, 19, 34, 42, 65, 65, 89, 123]. A red box highlights the subarray from index 2 to 6, containing [11, 19, 34, 42, 65]. Arrows indicate: 'A' points to index 0; '0' points to index 0; 'lo' points to index 2; 'hi' points to index 6; 'n' points to index 10.](3121ebddccf183ca63bb9781be440a7e_img.jpg)

| 0 | 1 | 2  | 3  | 4  | 5  | 6  | 7  | 8  | 9   | 10 |
|---|---|----|----|----|----|----|----|----|-----|----|
| 5 | 7 | 11 | 19 | 34 | 42 | 65 | 65 | 89 | 123 |    |

Diagram of an array A with indices 0 to 10. The array contains the values [5, 7, 11, 19, 34, 42, 65, 65, 89, 123]. A red box highlights the subarray from index 2 to 6, containing [11, 19, 34, 42, 65]. Arrows indicate: 'A' points to index 0; '0' points to index 0; 'lo' points to index 2; 'hi' points to index 6; 'n' points to index 10.

Assim, o algoritmo fica:

```

begin BuscaBinaria(array a, elemento x)
    <array está ordenado em ordem crescente >
    lo = 0
    hi = n
    <retorna o índice do elemento no array, ou <0 caso contrário>
end algoritmo
  
```

O algoritmo que está em construção é iterativo e, portanto, a definição de invariante de laço para caracterizar o bloco de repetição é de suma importância para garantir a construção correta da solução. Assim, pode-se iniciar a definição da invariante de laço como uma asserção sobre os valores de *lo* e *hi*. A cada nova análise vamos tornar a invariante “mais forte” até que seja adequada para mostrar que o algoritmo está correto. Note que a condição de saída do laço de repetição é quando o intervalo do subarray tem tamanho zero.

```

begin BuscaBinaria(array a, elemento x)
    <array está ordenado em ordem crescente >
    lo = 0
    hi = n
    loop
        <x está em a se e somente se está no subarray [lo..hi]>
        <0 $\leq$ lo $\land$ lo $\leq$ hi $\land$ hi $\leq$ n>
        exit when (lo=hi)
        ?
    end loop
    return -1;
    <retorna o índice do elemento no array, ou <0 caso contrário>
end algoritmo
  
```

No corpo do laço, primeiramente se calcula o ponto médio do subarray atual. A seguir, já é possível realizar um teste pelo elemento *x* e executar uma saída, pois a busca pode ter sido concluída.

{8}------------------------------------------------

```

begin BuscaBinaria(array a, elemento x)
  <array está ordenado em ordem crescente >
  lo = 0
  hi = n
  loop
    <x está em a se e somente se está no subarray [lo..hi]>
    < $0 \leq lo \wedge lo \leq hi \wedge hi \leq n$ >
    <?>
    exit when (lo=hi)
    int mid = lo + (hi - lo)/2;
    if (a[mid] = x) return mid
    ?
  end loop
  return -1;
  <retorna o índice do elemento no array, ou <0 caso contrário>
end algoritmo

```

Por que calcular  
dessa forma?

O que está faltando para completar a especificação da invariante? O que se sabe sobre cada etapa de busca e que deve ser preservado após a execução do laço? A melhor forma de observar a relação entre as variáveis do algoritmo é através de diagramas. Observa novamente a figura:

![Diagrama de um array A com 11 elementos (índices 0 a 10). Os valores são: 5, 7, 11, 19, 34, 42, 65, 65, 89, 123. O subarray [lo..hi] é destacado em vermelho, onde lo=2 e hi=6. Setas indicam que elementos menores que x (índices 0, 1) foram 'retirados' e elementos maiores que x (índices 7, 8, 9, 10) também foram 'retirados'.](bedcca5cdf168e3508ef511d94ec514c_img.jpg)

| Índice | 0 | 1 | 2  | 3  | 4  | 5  | 6  | 7  | 8  | 9   | 10 |
|--------|---|---|----|----|----|----|----|----|----|-----|----|
| Valor  | 5 | 7 | 11 | 19 | 34 | 42 | 65 | 65 | 89 | 123 |    |
| lo     |   |   |    |    |    |    |    |    |    |     |    |
| hi     |   |   |    |    |    |    |    |    |    |     |    |

Diagrama de um array A com 11 elementos (índices 0 a 10). Os valores são: 5, 7, 11, 19, 34, 42, 65, 65, 89, 123. O subarray [lo..hi] é destacado em vermelho, onde lo=2 e hi=6. Setas indicam que elementos menores que x (índices 0, 1) foram 'retirados' e elementos maiores que x (índices 7, 8, 9, 10) também foram 'retirados'.

A área destacada representa o subintervalo atualmente sendo analisado, definido pelos valores de  $lo$  e  $hi$ . Observe que todos elementos à esquerda de  $lo$  (não incluindo) foram “retirados” do próximo passo do laço pois sabe-se que são estritamente menores que o elemento  $x$ ; da mesma forma, foram “retirados” da comparação todos os elementos à direita de  $hi$  (incluindo) pois sabe-se que são estritamente maiores que  $x$ . A parte do “meio” ainda não foi explorada. Assim tem-se:

| Índice | 0 | 1 | 2  | 3  | 4  | 5  | 6  | 7  | 8  | 9   | 10 |
|--------|---|---|----|----|----|----|----|----|----|-----|----|
| Valor  | 5 | 7 | 11 | 19 | 34 | 42 | 65 | 65 | 89 | 123 |    |
| lo     |   |   |    |    |    |    |    |    |    |     |    |
| hi     |   |   |    |    |    |    |    |    |    |     |    |

Diagrama similar ao anterior, mas com setas e rótulos (< x, ?, > x) indicando a lógica de exclusão de elementos com base na comparação com x.

Resumido as informações da imagem tem-se que  $a[lo - 1] < x$  e  $a[hi] > x$ . Isso implica que  $x$  não pode estar nos intervalos  $a[0..lo)$  nem  $a[hi..n)$  já que o array está ordenado. Contudo, usar tal condição diretamente na invariante induz a um erro. Observe que tais condições podem não ser verdadeiras ao se entrar no laço a primeira vez (ou em alguma iteração futura), como demonstra o caso inicial, o qual resulta numa quebra dessa invariante:

{9}------------------------------------------------

![Diagram of a binary search on an array. The array has 11 elements: [5, 7, 11, 19, 34, 42, 65, 65, 89, 123]. The search range is from index 0 to 10. A bracket above the array indicates the search range [lo..hi] with a question mark. Labels '<x?' and '>x?' are at the ends of the bracket. An arrow labeled 'A' points to the first element (5). Arrows point to the first and last elements with labels 'lo = 0' and 'hi = n' respectively.](a5ee5c23b6dc52ec1d724b76d5a5f58f_img.jpg)

Diagram illustrating a binary search on an array. The array contains elements: 5, 7, 11, 19, 34, 42, 65, 65, 89, 123. The search range is from index 0 to 10. A bracket above the array indicates the search range [lo..hi] with a question mark. Labels '<x?' and '>x?' are at the ends of the bracket. An arrow labeled 'A' points to the first element (5). Arrows point to the first and last elements with labels 'lo = 0' and 'hi = n' respectively.

Diagram of a binary search on an array. The array has 11 elements: [5, 7, 11, 19, 34, 42, 65, 65, 89, 123]. The search range is from index 0 to 10. A bracket above the array indicates the search range [lo..hi] with a question mark. Labels 'x?' are at the ends of the bracket. An arrow labeled 'A' points to the first element (5). Arrows point to the first and last elements with labels 'lo = 0' and 'hi = n' respectively.

Assim, completa-se a invariante de laço com condições adequadas para os diversos casos:

```

begin BuscaBinaria(array a, elemento x)
    <array está ordenado em ordem crescente >
    lo = 0
    hi = n
    loop
        <x está em a se e somente se está no subarray [lo..hi]>
        <0 $\leq$ lo $\land$ lo $\leq$ hi $\land$ hi $\leq$ n>
        <lo = 0 $\lor$ a[lo - 1] < x>
        <hi = n $\lor$ a[hi] > x>
        exit when (lo=hi)
        int mid = lo + (hi - lo)/2
        if (a[mid] = x) return mid
        ?
    end loop
    return -1;
    <retorna o índice do elemento no array, ou <0 caso contrário>
end algoritmo
  
```

Como a invariante deve ser preservada pelo laço iterativo, tem-se dois casos a considerar para que o código seja completado a fim de ser calculado o novo intervalo para a próxima iteração:  $a[mid] < x$  ou  $a[mid] > x$ . Se  $a[mid] < x$ , então tem-se um novo valor para o limite inferior do subintervalo e, portanto, coloca-se  $lo$  com o valor  $mid+1$ . Se  $a[mid] > x$ , então tem-se um novo valor para o limite superior do subintervalo e, portanto, coloca-se  $hi$  com o valor de  $mid$ . Certifique-se que tal alteração de valores não quebra a invariante! O algoritmo obtido:

{10}------------------------------------------------

```

begin BuscaBinaria(array a, elemento x)
    <array está ordenado em ordem crescente >
    lo = 0
    hi = n
    loop
        <x está em a se e somente se está no subarray [lo..hi]>
        <0 $\leq$ lo $\land$ lo $\leq$ hi $\land$ hi $\leq$ n>
        <lo = 0 $\lor$ a[lo - 1] < x>
        <hi = n $\lor$ a[hi] > x>
        exit when (lo=hi)
        int mid = lo + (hi - lo)/2
        if (a[mid] = x) return mid
        if (a[mid] < x) lo = mid + 1
        else hi = mid
    end loop
    return -1;
    <retorna o índice do elemento no array, ou <0 caso contrário>
end algoritmo

```

Para exemplificar a execução do algoritmo, seja a seguinte lista de elementos:

|    |    |    |    |    |    |    |
|----|----|----|----|----|----|----|
| -5 | 10 | 14 | 33 | 42 | 42 | 42 |
| 0  | 1  | 2  | 3  | 4  | 5  | 6  |

Define-se o estado como sendo  $s \triangleq \mathbb{Z} \times \mathbb{N} \times \mathbb{N} \times \mathbb{N} = \langle x, lo, hi, n \rangle$  e o estado inicial  $\langle x, 0, tamanho\ do\ array, tamanho\ do\ array \rangle$ . As seguintes seqüências de estados demonstram os passos de computação para a busca do elemento 14 e elemento 42:

| Estados                             | Invariante de Laço                                                    |
|-------------------------------------|-----------------------------------------------------------------------|
| $s_0 = \langle 14, 0, 7, 7 \rangle$ | $0 \leq lo \leq hi \leq 7, lo = 0, hi = 7$                            |
| $s_1 = \langle 14, 0, 3, 7 \rangle$ | $0 \leq lo \leq hi \leq 7, lo = 0, a[3] > 14$                         |
| $s_2 = \langle 14, 2, 3, 7 \rangle$ | $0 \leq lo \leq hi \leq 7, a[1] < 14, a[3] > 14$                      |
| $s_3 = \langle 14, 2, 3, 7 \rangle$ | $0 \leq lo \leq hi \leq 7, a[1] < 14, a[3] > 14$<br>Saída $a[2] = 14$ |

| Estados                             | Invariante de Laço                                                 |
|-------------------------------------|--------------------------------------------------------------------|
| $s_0 = \langle 42, 0, 7, 7 \rangle$ | $0 \leq lo \leq hi \leq 7, lo = 0, hi = 7$                         |
| $s_1 = \langle 42, 4, 7, 7 \rangle$ | $0 \leq lo \leq hi \leq 7, a[3] < 42, hi = 7$                      |
| $s_2 = \langle 42, 4, 7, 7 \rangle$ | $0 \leq lo \leq hi \leq 7, a[3] < 42, hi = 7$<br>Saída $a[5] = 42$ |

A seguinte seqüência de estados demonstra o caso da busca por um elemento que não está no array, por exemplo, o valor 0:

{11}------------------------------------------------

| Estados                         | Invariante de Laço                                         |
|---------------------------------|------------------------------------------------------------|
| $s_0 = \langle 0,0,7,7 \rangle$ | $0 \leq lo \leq hi \leq 7, lo = 0, hi = 7$                 |
| $s_1 = \langle 0,0,3,7 \rangle$ | $0 \leq lo \leq hi \leq 7, lo = 0, a[3] > 0$               |
| $s_2 = \langle 0,0,1,7 \rangle$ | $0 \leq lo \leq hi \leq 7, lo = 0, a[1] > 0$               |
| $s_3 = \langle 0,1,1,7 \rangle$ | $0 \leq lo \leq hi \leq 7, a[0] < 0, a[1] > 0$<br>Saída -1 |

<!-- IMAGE_DESCRIPTION: datalab-925f55ce69802b9d3b00546382663ee2_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagrama similar ao anterior, mas com setas e rótulos (< x, ?, > x) indicando a lógica de exclusão de elementos com base na comparação com x.
<!-- /IMAGE_DESCRIPTION -->
