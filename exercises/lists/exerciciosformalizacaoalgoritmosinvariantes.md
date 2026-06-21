{0}------------------------------------------------

# Exercícios

# Formalização de algoritmos com invariantes de laço

1) Dado os seguintes passos de um algoritmo (definido em uma linguagem como Java), defina a noção de estado da computação e mostre os passos de computação a partir do estado inicial para o valor de entrada  $c = 4$ . Defina também uma relação de transição entre os estados.

```
x=c;  
y=0;  
while (x>0){  
    x=x-1;  
    y=y+1;  
}
```

2) Para o algoritmo do exercício anterior, qual a relação entre os valores das variáveis  $c$ ,  $x$  e  $y$  a cada passo da iteração? Defina uma asserção que seja uma invariante.

3) Defina um algoritmo iterativo (não recursivo) para o cálculo do fatorial de um número Natural qualquer.

4) Para o algoritmo do exercício 3 (fatorial), defina uma noção de estado de computação e mostre os passos necessários para computar o valor do fatorial do número 4. Defina também uma relação de transição entre os estados.

5) Para o algoritmo do exercício 3 (fatorial), defina uma asserção que mostre uma propriedade invariante adequada para o laço de repetição.

6) Reescreva o algoritmo de busca binária de modo que os valores  $lo$  e  $hi$  que definem o subintervalo do array sejam ambos inclusos, isto é  $[lo..hi]$ . Modifique corretamente todas as asserções da invariante de laço. Qual o comportamento observado no resultado do algoritmo?

7) Observe e se convença que o algoritmo apresentado no material de estudo não garante que o índice retornado seja a da primeira ocorrência de um elemento caso o array contenha elementos repetidos.

a) O que ele garante sobre o índice?

b) Modifique a pós-condição para garantir que o valor retornado seja o índice da primeira ocorrência caso o elemento esteja no array. Reescreva o algoritmo e adeque as asserções da invariante de laço.

c) Repita o mesmo processo do exercício anterior para o caso em que se deseja obter o índice da última ocorrência do elemento caso ele esteja no array.

{1}------------------------------------------------

8) Pesquise a definição e o código-fonte do método *Collections.binarySearch* em Java e verifique quais são suas pré e pós condições.