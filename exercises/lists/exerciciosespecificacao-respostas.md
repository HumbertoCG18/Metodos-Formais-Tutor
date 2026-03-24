## Métodos Formais

## Especificação Formal

## 1) Seja a seguinte especificação:

Foi solicitado a um programador a implementação de uma função para verificar a presença ou ausência de um valor x em um array a.

Antes de prosseguir, pense nos requisitos que precisamos antes de iniciar a implementação da solução.

Assuma as seguintes perguntas e suas respectivas respostas:

- Qual é o segmento de posições do array que deve ser pesquisado?
  - O array deve ser pesquisado dentro de um intervalo inteiro [0;n-1], onde n é o número de instâncias de valores que pertencem à busca. Note que n não pode ser maior que o tamanho atual do array. Assumir que n corresponde exatamente ao tamanho do array.
- Qual é o tipo de x e como ele deve ser comparado?
  - O array será composto por números inteiros e comparado através da igualdade usual entre inteiros.
- · Como o resultado deve ser informado?
  - A função deverá retornar um valor booleano *true* se *x* ocorre no array e *false* caso contrário.
- O segmento do array a ser pesquisado está, por exemplo, ordenado, de modo a permitir um algoritmo mais eficiente de pesquisa?
  - O conteúdo do array não apresenta nenhuma ordem em particular.
- É possível que x possua mais de uma ocorrência e, se sim, tal fato deve ser relevante?
  - O array pode possuir várias ocorrências do valor x, mas tal fato é irrelevante.
- É possível que o segmento do array esteja vazio e, se sim, isso é um erro ou um estado normal?
  - O segmento do array pode estar vazio (tamanho igual a 0) e tal fato não deve ser considerado um erro. No caso de um segmento de array vazio, a busca sempre irá retornar *false*.
- O array pode ou não ser alterado de alguma forma?
  - Ao final da execução da função, o array deve estar no mesmo estado anterior à execução da função, ou seja, não deve ocorrer mutação nos parâmetros de entrada do método. Observação: isso se refere ao conceito de função pura, onde os parâmetro de entrada são somente de leitura.

Com base nessas respostas, construa uma especificação formal, utilizando fórmulas em lógica de predicados, para pré e pós condições para uma função que realiza a tarefa solicitada. Dica: utilize fórmulas enriquecidas com construções sintáticas usuais de linguagens de programação e qualquer operador adicional que julgar necessário (desde que apresente uma definição informal de sua semântica).

- 2) Construa fórmulas em lógica de predicados sobre um segmento de array no intervalo [0;n-1] para:
  - a. Todas entradas com valor igual a x.
  - b. Todas entradas são iguais entre si.
  - c. As entradas estão em ordem crescente.
  - d. O valor *x* ocorre exatamente uma única vez.
- 3) Dada a seguinte assinatura de uma função para realizar uma busca binária para encontrar o índice onde um elemento se encontra no array, apresente fórmulas em lógica de predicados para pré e pós condições:

 $buscaBinaria: Array(\mathbb{Z}) \times \mathbb{Z} \to \mathbb{Z}$ 

buscaBinaria(array, chave)

4) Dada a seguinte assinatura de uma função para realizar uma busca para encontrar o índice onde o primeiro valor zero se encontra no array, apresente fórmulas em lógica de predicados para pré e pós condições:

 $encontrar Primeiro Zero : Array \langle \mathbb{Z} \rangle \rightarrow \mathbb{Z}$ 

encontrarPrimeiroZero(array)

```
RESPOSTAS:
1)
Seja \mathbb{B} = \{true, false\}
buscar: Array(\mathbb{Z}) \times \mathbb{Z} \to \mathbb{B}
Pré condição:
true
Pós condição (versão 1):
Dado buscar(array, x) = b temos
b \leftrightarrow \exists i \in \mathbb{N}. (i < array. tamanho \land array[i] = x)
ou sendo | array | a notação para o tamanho do array
b \leftrightarrow \exists i \in \mathbb{N}. (i < |array| \land array[i] = x)
Pós condição (versão 2):
(b = true \rightarrow \exists i \in \mathbb{Z}. (0 \le i < |array| \land array[i] = x)) \land
(b = false \rightarrow \forall i \in \mathbb{Z}. (0 \le i < |array| \rightarrow array[i] \ne x))
2)
a)
\forall i \in \mathbb{N}. (i < |array| \rightarrow array[i] = x)
b)
\forall i \in \mathbb{N}. (i < |array| - 1 \rightarrow array[i] = array[i + 1])
c)
\forall i \in \mathbb{N}. (i < |array| - 1 \rightarrow array[i] \leq array[i + 1])
ou
\forall i, j \in \mathbb{N}. (i < j < |array| \rightarrow array[i] \leq array[j])
d)
Noção "somente um x tem propriedade P":
\exists x. (P(x) \land \forall y. (P(y) \rightarrow y = x))
Logo:
\exists i \in \mathbb{N}. (i < |array| \land array[i] = x \land \forall j \in \mathbb{N}. (j < |array| \land array[j] = x \rightarrow j = i))
```

```
3)  \begin{array}{l} \text{Pré condição:} \\ \forall i,j \in \mathbb{N}. \ (i < j < |array| \rightarrow array[i] \leq array[j]) \\ \text{Pós condição:} \\ \text{Dado} buscaBinaria(array,x) = r \text{temos} \\ r < 0 \rightarrow (\forall i \in \mathbb{N}. \ (i < |array| \rightarrow array[i] \neq x)) \land \\ r \geq 0 \rightarrow (r < |array| \land array[r] = x) \\ \end{array}
```

Pré condição:

true

Pós:

Dado encontrarPrimeiroZero(array) = r temos

$$\begin{split} r &= -1 \longrightarrow (\forall i \in \mathbb{N}. \, (i < |array| \longrightarrow array[i] \neq 0)) \, \wedge \\ r &\geq 0 \longrightarrow (r < |array| \wedge array[r] = 0 \, \wedge \, (\forall i \in \mathbb{N}. \, (i < r \longrightarrow array[i] \neq 0))) \end{split}$$
