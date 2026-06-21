<!-- EXEC_SUMMARY_START -->
## Sumário
> *Leia antes de varrer o arquivo. Vá direto à seção relevante para a pergunta do aluno.*

- **Triplas de Hoare**
  - Exemplo 1:
  - Exemplo 2:
  - Exercícios:
- **Linguagem de Programação Simplificada**
  - SINTAXE (BNF):
  - Expressões aritméticas:
  - Expressões lógicas:
  - Comandos:
  - Exercício:
- **Cálculo de Floyd-Hoare**
  - Exemplo:
- **ATRIBUIÇÃO**
  - Exemplo:
- **CONSEQUÊNCIA (PreForte e PosFraco)**
  - Exemplo:
  - Exercício:
- **COMPOSIÇÃO**
  - Exemplo:
  - Exemplo completo com o uso de Atribuição + PreForte + Composicao:
  - Exercício:
- **CONDICIONAL**
  - Exemplo:
  - Exemplo completo com o uso de Atribuição + PreForte + Condicional:
  - Exercícios:
  - Exercícios:

<!-- EXEC_SUMMARY_END -->
{0}------------------------------------------------

# Lógica de Floyd-Hoare

- Método axiomático para provar que determinados programas são corretos.
- Introduzido por Charles Antony Richard Hoare e Robert Floyd na década de 1960.
- Também utilizado para especificar a semântica (axiomática) de linguagens de programação.
- Por que devemos especificar e verificar código?
  - Para redução de falhas que são introduzidas durante a especificação do sistema e, assim, reduzir o seu custo final;
  - Código bem especificado e verificado é mais fácil de reutilizar, uma vez que temos um claro entendimento do que o sistema deve fazer;
  - Para sistemas críticos (aviões, usinas nucleares, ...) isto se torna muito mais importante, pois se espera que os sistemas possam sofrer auditorias sobre o quanto eles garantem que irão funcionar conforme desejado;
  - A especificação de um sistema auxilia na documentação do mesmo e, feita de uma maneira formal, auxilia no processo de implementação final do sistema;
  - Atualmente empresas enfrentam problemas com sistemas legados, pois os responsáveis pelo seu desenvolvimento não os documentam de uma maneira precisa e, na maioria das vezes, não se encontram mais na empresa;
  - Sistemas de software têm um tempo de vida muitas vezes maior do que as pessoas – o *bug* do milênio (ano 2000) é apenas um exemplo.
- Abordagem que usaremos:
  - ➔ aplicar o método de Floyd-Hoare sobre uma linguagem de programação imperativa simplificada.

[Dados de Entrada] → [Programa] → [Dados de Saída]

{1}------------------------------------------------
## Triplas de Hoare

$\boxed{ \langle P \rangle \ C \ \langle Q \rangle } ,$  onde:

- P e Q são asserções (fórmulas na lógica de predicados de primeira ordem com igualdade);
- P : precondição (asserções definidas sobre o estado inicial do programa, que denotam sob quais restrições o programa está preparado para funcionar);
- Q : pós-condição (asserções sobre o estado final do programa, que denotam condições sobre os dados resultantes do programa);
- C : comandos de uma linguagem de programação.

Exemplo:

$\langle x > 4 \rangle \quad x := x + 1 \quad \langle x > 5 \rangle$
### Exemplo 1:

Problema: dados dois valores de entrada sobre o domínio dos números inteiros maiores ou iguais a 10, o programa deverá calcular a soma desses dois valores.

Especificação:

- sejam x o primeiro valor de entrada e y o segundo valor de entrada.
- seja z o valor calculado pelo programa.

Solução (A) - OK

precondição:  $\langle (x \geq 10) \wedge (y \geq 10) \rangle$   
 pós-condição:  $\langle (z = x + y) \rangle$

Solução (B) – Exemplo de super-especificação

precondição:  $\langle (x \geq 10) \wedge (y \geq 10) \wedge ((x+y) \geq 0) \text{ desnecessário} \rangle$   
 pós-condição:  $\langle (z = x + y) \wedge (z \geq 20) \text{ desnecessário} \rangle$

Solução (C) – Exemplo de especificação desnecessariamente complexa

precondição:  $\langle (x \geq 10) \wedge ((x+y) \geq (10+x)) \text{ não é claro} \rangle$   
 pós-condição:  $\langle (z = x + y) \rangle$

Solução (D) – Exemplo de especificação incompleta

precondição:  $\langle (x \geq 10) \text{ ??? falta algo!} \rangle$   
 pós-condição:  $\langle (z = x + y) \rangle$
### Exemplo 2:

Problema: dado um número inteiro, calcular o fatorial do número de forma iterativa (não recursiva).

Especificação:

- x: o número (entrada)

{2}------------------------------------------------

- fat: o resultado do programa

Solução:

precondição:  $(| (x \geq 0) \wedge (\text{temp} = x) |)$   
 pós-condição:  $(| (\text{fat} = \text{temp}!) |)$

Exemplo de possível programa em Java:

```
int fatorial (int x){
    int fat = 1;
    while (x != 1){
        fat = fat * x;
        x = x - 1;
    }
    return fat;
}
```

*Note que x será alterado no programa, portanto reservamos uma cópia lógica em temp.*
### Exercícios:

- 1) Formular uma especificação para um programa que, dados dois números naturais, deverá calcular o máximo divisor comum para eles (considere uma função matemática MDC).

x e y: os dois valores de entrada

mdc: o resultado do programa

precondição:  $(| (x > 0) \wedge (y > 0) |)$

pós-condição:  $(| (\text{mdc} = \text{MDC}(x,y)) |)$

- 2) Formular uma especificação para um programa que, dados dois números inteiros de entrada, a soma desses dois números no estado inicial deverá ser idêntica à soma deles no estado final do programa. Note que o programa poderá eventualmente modificar os valores das variáveis de entrada.

x e y: os números de entrada

S: variável para garantir o que foi especificado

precondição:  $(| (S = x + y) |)$

pós-condição:  $(| (S = x + y) |)$

{3}------------------------------------------------
## Linguagem de Programação Simplificada

- Paradigma: Linguagem do tipo imperativa
- Tipos de dados: int e bool
- Comandos: atribuição ( $:=$ ), sequência (;), condição (if), laço (while)
### SINTAXE (BNF):
### Expressões aritméticas:

$$E ::= n \mid x \mid E+E \mid E-E \mid E * E \mid -E$$

Onde n é um número inteiro, x é qualquer variável
### Expressões lógicas:

$$B ::= \text{true} \mid \text{false} \mid !B \mid B \& B \mid B \mid B \mid E < E \mid E == E \mid E != E$$
### Comandos:

$$C ::= x := E \mid C ; C \mid \text{if } B \{C\} \mid \text{if } B \{C\} \text{ else } \{C\} \mid \text{while } B \{C\}$$
### Exercício:

- 1) Dê alguns exemplos de programas utilizando a sintaxe definida.
## Cálculo de Floyd-Hoare

Para cada comando possível em um programa teremos uma regra que define sua “semântica axiomática”.

Além disso, teremos regras extras de consequências, chamadas de PreForte e PosFraco. O cálculo de demonstração a ser utilizado em uma demonstração  $\vdash_{\text{parcial}} (|\phi_0|)C(|\phi_n|)$  será composto por uma sequência entremeando fórmulas e códigos de programa. A cada fórmula escreve-se uma justificativa.

$$\begin{array}{l} (|\phi_0|) \\ C_1 \\ (|\phi_1|) \text{ justificativa} \\ C_2 \\ \dots \\ (|\phi_{n-1}|) \text{ justificativa} \\ C_n \\ (|\phi_n|) \text{ justificativa} \end{array}$$

Como encontrar as fórmulas intermediárias? É mais conveniente começar a demonstração de trás para frente! Procure refazer os exemplos apresentados usando essa técnica.

{4}------------------------------------------------

O Cálculo de Floyd-Hoare, na versão aqui apresentada, irá obter a chamada “pré-condição mais fraca”. Essa condição é a “mais fraca” no sentido de que qualquer outra pré-condição possível implicará nela.
### Exemplo:

$$\begin{array}{l} (| y \leq 4 |) \quad x := y+1 \quad (| x \leq 5 |) \\ y \leq 4 \wedge z = 0 \Rightarrow y \leq 4 \end{array}$$
## ATRIBUIÇÃO

$$\begin{array}{l} (| P |) \quad x := 4 \quad (| y > x |) \\ (| y > 4 |) \quad x := 4 \quad (| y > x |) \end{array} \quad (\text{Qual fórmula deve ser } P ?)$$

Constrói-se a pré-condição a partir da pós-condição:

|                                                       |
|-------------------------------------------------------|
| Atribuição                                            |
| $\frac{}{(   Q[x/t]  ) \quad x := t \quad (   Q   )}$ |
### Exemplo:

$$\begin{array}{l} (| \quad ???? \quad |) \quad x := x + 1 \quad (| (x < 5) |) \\ 3. (| \quad x < 4 \quad |) \quad x := x + 1 \quad (| (x < 5) |) \\ 2. (| \quad x+1 < 5 \quad |) \quad x := x + 1 \quad (| (x < 5) |) \\ 1. (| \quad (x < 5)_{[x/(x+1)]} \quad |) \quad x := x + 1 \quad (| (x < 5) |) \text{ Atrib} \end{array}$$
## CONSEQUÊNCIA (PreForte e PosFraco)

Algumas vezes, as pré e pós condições que obtemos pelas regras do Cálculo de Hoare podem não ser exatamente a que desejamos. Elas podem ser logicamente equivalentes, mas ter uma forma sintática diferente ou podem ser logicamente mais fracas (no caso de pré-condições) ou logicamente mais fortes (no caso de pós-condições).
### Exemplo:

Verifique o que acontece quando obtemos uma pré-condição por *Atrib* que não corresponde exatamente ao que precisávamos para uma dada prova...

Provar que o seguinte programa está correto:

$$( | \quad x < 3 \quad | ) \quad x := x + 1 \quad ( | (x < 5) | )$$
#### Resolução:

$$\begin{array}{l} ( | \quad x+1 < 5 \quad | ) \quad x := x + 1 \quad ( | (x < 5) | ) \\ ( | \quad (x < 5)_{[x/(x+1)]} \quad | ) \quad x := x + 1 \quad ( | (x < 5) | ) \text{ Atrib} \end{array}$$

{5}------------------------------------------------

Repare que queríamos provar  $x < 3$ , porém obtivemos  $x+1 < 5$  depois de aplicar *Atrib.* Então temos que usar outra regra:

$$\frac{P \Rightarrow Q, (|Q|) \text{ C } (|R|), R \Rightarrow S}{(|P|) \text{ C } (|S|)} \text{ Consequência}$$

Observe que esta regra pode ser separada em duas (uma para o fortalecimento da pré-condição e outra para o enfraquecimento da pós-condição):

$$\frac{P \Rightarrow Q, (|Q|) \text{ C } (|R|)}{(|P|) \text{ C } (|R|)} \text{ PreForte}$$

$$\frac{(|P|) \text{ C } (|Q|), Q \Rightarrow R}{(|P|) \text{ C } (|R|)} \text{ PosFraco}$$

Veja o exemplo de aplicação da regra de fortalecimento da pré-condição. Agora temos que provar que:

$$(x < 3) \Rightarrow (x+1 < 5)$$

... ou seja, que o primeiro é um caso especial do segundo (o segundo é uma asserção mais fraca, portanto).

Venn diagram showing that x < 3 implies x + 1 < 5. A small blue circle labeled 'x < 3' is entirely contained within a larger orange circle labeled 'x + 1 < 5'.

Observe que a asserção obtida pela aplicação da regra do Cálculo de Hoare para a Atribuição é uma asserção mais fraca. A aplicação da regra da Consequência para Fortalecimento da pré-condição é que permite obtermos a prova desejada.

Exemplo completo com o uso de Atribuição + PreForte:

Prove:  $(|x < 3|) \quad x := x + 1 \quad (|x < 5|)$

|    |                 |                 |
|----|-----------------|-----------------|
| 4. | $( x < 3 )$     |                 |
| 3. | $( x + 1 < 5 )$ | <b>PreForte</b> |
| 2. | $x := x + 1$    |                 |

{6}------------------------------------------------

|    |             |            |
|----|-------------|------------|
| 1. | $( x < 5 )$ | Atribuição |
|----|-------------|------------|

Observe que a implicação  $(x < 3) \Rightarrow (x+1 < 5)$  não será provada, pois estamos interessados na estrutura do Cálculo de Hoare e não em provas de teorias aritméticas. Assumimos que um provador de teoremas automatizado será capaz de construir tais provas (por exemplo, em um sistema automatizado como Dafny).

<!-- IMAGE_DESCRIPTION: datalab-5d76c2e9976aaf97001ee189908830fb_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Venn diagram showing that x < 3 implies x + 1 < 5.
<!-- /IMAGE_DESCRIPTION -->
### Exercício:

1) Prove:  $(|x < 5|) \quad x := x + 1 \quad (|x < 7|)$
## COMPOSIÇÃO

Agora vamos ver como combinar dois comandos em sequência:

|                                  |            |
|----------------------------------|------------|
| $( P ) C1 ( Q ), ( Q ) C2 ( R )$ | Composição |
| $( P ) C1; C2 ( R )$             |            |

A regra Composição permite a sequência de comandos. Determinamos a asserção intermediária  $(|Q|)$  a partir da pós-condição.
### Exemplo:

Determinar a precondição:

$(| \quad ? \quad |) \quad x := x + 1 ; y := y + x \quad (| y > 6 |)$

3.  $(| y + x + 1 > 6 |) \quad x := x + 1 ; y := y + x \quad (| y > 6 |) \quad \text{Comp 1,2}$
2.  $(| y + x + 1 > 6 |) \quad x := x + 1 \quad (| y + x > 6 |) \quad \text{Atrib (em C1)}$
1.  $(| y + x > 6 |) \quad y := y + x \quad (| y > 6 |) \quad \text{Atrib (em C2)}$
### Exemplo completo com o uso de Atribuição + PreForte + Composicao:

Prove:  $(|x > 2 \wedge y > 3|) \quad x := x + 1 ; y := y + x \quad (|y > 6|)$

|  |                          |            |
|--|--------------------------|------------|
|  | $( x > 2 \wedge y > 3 )$ |            |
|  | $( y+x+1 > 6 )$          | PreForte   |
|  | $x := x + 1$             |            |
|  | $( y+x > 6 )$            | Atribuição |
|  | $y := y + x$             |            |
|  | $( y > 6 )$              | Atribuição |

Procure descrever informalmente por que a implicação indicada é válida. Ou seja, a condição de prova que será necessária é provar  $x > 2 \wedge y > 3 \Rightarrow y+x+1 > 6$ .
### Exercício:

1) Prove:  $(|a > 0 \wedge b > 0|) \quad x := a ; y := b \quad (|x+y > 0|)$

{7}------------------------------------------------

2) Prove:  $(|a > b|) \quad x := -a ; y := -b \quad (|x < y|)$

3) Os dois programas a seguir realizam a troca de valores entre suas variáveis. Mostre que ambos estão corretos.

a) Prove:  $(|x < y|) \quad \text{temp} := x ; x := y ; y := \text{temp} \quad (|y < x|)$

b) Prove:  $(|x < y|) \quad y := y + x ; x := y - x ; y := y - x \quad (|y < x|)$
## CONDICIONAL

Com relação aos condicionais, vamos primeiro lidar com a versão mais simples. Nesta regra, a primeira premissa trata do caso em que a expressão booleana  $B$  é avaliada como *true*. A segunda premissa, portanto, leva em conta o caso em que  $B$  é *false*.

$$\frac{(|P \wedge B|) C \quad (|Q|), \quad P \wedge \neg B \Rightarrow Q}{(|P|) \text{ if } B \{C\} \quad (|Q|)} \text{ Condicional1}$$
### Exemplo:

$(|T|) \quad \text{if } x < 0 \{x := -x\} \quad (|x \geq 0|)$

As premissas para a regra, então, seriam (devemos provar **as duas**):

a)  $(|T \wedge x < 0|) \quad x := -x \quad (|x \geq 0|)$

b)  $(| (T \wedge \neg(x < 0)) \Rightarrow (x \geq 0) |)$

Observe que queremos calcular a condição mais fraca  $\phi$  tal que:

$(|\phi|) \text{ if } B \{C\} \quad (|Q|)$

Esta  $\phi$  pode ser calculada da seguinte maneira:

a) Empurre  $Q$  para cima através de  $C$ ; vamos chamar o resultado de  $\phi_1$ .

b) Defina  $\phi$  como  $(B \Rightarrow \phi_1) \wedge (\neg B \Rightarrow Q)$ .
### Exemplo completo com o uso de Atribuição + PreForte + Condicional:

Prove:  $(|T|) \quad \text{if } x < 0 \{x := -x\} \quad (|x \geq 0|)$

|  |                                                                           |                     |
|--|---------------------------------------------------------------------------|---------------------|
|  | $( T )$                                                                   |                     |
|  | $( x < 0 \Rightarrow -x \geq 0 \wedge \neg(x < 0) \Rightarrow x \geq 0 )$ | <b>PreForte</b>     |
|  | if (x < 0)                                                                |                     |
|  | }                                                                         |                     |
|  | $(  -x \geq 0  )$                                                         | <b>Condicional1</b> |
|  | $x := -x$                                                                 |                     |
|  | $(  x \geq 0  )$                                                          | <b>Atribuição</b>   |
|  | }                                                                         |                     |

{8}------------------------------------------------

|                |              |
|----------------|--------------|
| $( x \geq 0 )$ | Condiciona11 |
|----------------|--------------|

Procure descrever informalmente porquê a implicação indicada é válida.
### Exercícios:

- 1) Prove:  $(|x < 10|) \quad \text{if } x \geq 5 \{x := 4\} \quad (|x < 5|)$
- 2) Prove:  $(|T|) \quad \text{if } x < y \{x := y\} \quad (|x \geq y|)$
- 3) Prove:  $(|T|) \quad \text{if } x > y \{x := y+1; y := x+1\} \quad (|x \leq y|)$

Agora vamos ver a regra para o condicional completo (com *else*).

|                                                                                                                       |             |
|-----------------------------------------------------------------------------------------------------------------------|-------------|
| $\frac{( P \wedge B ) C1 ( Q ), ( P \wedge \neg B ) C2 ( Q )}{( P ) \text{ if } B \{C1\} \text{ else } \{C2\} ( Q )}$ | Condiciona2 |
|-----------------------------------------------------------------------------------------------------------------------|-------------|

Observe que queremos calcular a condição mais fraca  $\phi$  tal que:

$$(|\phi|) \text{ if } B \{C1\} \text{ else } \{C2\} (|Q|)$$

Esta  $\phi$  pode ser calculada da seguinte maneira:

- a) Empurre  $Q$  para cima através de  $C1$ ; vamos chamar o resultado de  $\phi_1$ .
- b) Empurre  $Q$  para cima através de  $C2$ ; vamos chamar o resultado de  $\phi_2$ .
- b) Defina  $\phi$  como  $(B \Rightarrow \phi_1) \wedge (\neg B \Rightarrow \phi_2)$ .
#### Exemplo completo com o uso de Atribuição + PreForte + Condicional:

Prove:

```
(|T|)
a:=x+1;
if (a-1 == 0) {
  y:=1;
} else {
  Y:=a;
}
(| y = x+1 |)
```

|                                                                          |             |
|--------------------------------------------------------------------------|-------------|
| $( T )$                                                                  |             |
| $( x+1-1=0 \Rightarrow 1=x+1 \wedge \neg(x+1-1=0) \Rightarrow x+1=x+1 )$ | PreForte    |
| $a := x+1;$                                                              |             |
| $( a-1=0 \Rightarrow 1=x+1 \wedge \neg(a-1=0) \Rightarrow a=x+1 )$       | Atribuição  |
| if (a-1 == 0) {                                                          |             |
| $( 1 = x + 1 )$                                                          | Condiciona2 |
| $y := 1;$                                                                |             |
| $( y = x + 1 )$                                                          | Atribuição  |
| }                                                                        |             |
| $( a = x + 1 )$                                                          | Condiciona2 |
| $y := a;$                                                                |             |

{9}------------------------------------------------

|  |                         |                     |
|--|-------------------------|---------------------|
|  | $(\mid y = x + 1 \mid)$ | <b>Atribuição</b>   |
|  | }                       |                     |
|  | $(\mid y = x + 1 \mid)$ | <b>Condiciona12</b> |

Procure descrever informalmente porquê a implicação indicada é válida.
### Exercícios:
#### 1) Prove:

```

( $\mid T \mid$ )
if (x<y) {
    max := y
}else{
    max := x
}
( $\mid \max \geq x \wedge \max \geq y \mid$ )

```
#### 2) Prove:

```

( $\mid T \mid$ )
if (x<y) {
    y := y-1
}else{
    x := -x;
    y := -y
}
( $\mid x \leq y \mid$ )

```
