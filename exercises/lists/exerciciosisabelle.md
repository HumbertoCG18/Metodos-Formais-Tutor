## **Prof. Júlio Machado**

## **Exercícios**

## **Formalização e prova de algoritmos como equações recursivas no Isabelle**

- 1) Nos exercícios a seguir, descreva no Isabelle as equações recursivas referentes a cada função sobre os números Naturais. Lembre-se que a recursão deve ser feita sobre a estrutura indutiva do conjunto *nat* do Isabelle, ou seja, sobre *0* e o construtor *Suc*.
- a) Especifique uma função para calcular a função potência de dois (2 ). Utilize a função 2: $\mathbb{N}$ → $\mathbb{N}$. A utilização de operações de multiplicação (\*) é permitida.
- b) Especifique uma função para calcular o fatorial de um número. Utilize a função : $\mathbb{N}$ → $\mathbb{N}$. A utilização de operações de multiplicação (\*) é permitida.
- c) Especifique uma função para calcular o n-ésimo termo da série de Fibonacci. Utilize a função : $\mathbb{N}$ → $\mathbb{N}$. A utilização de operações de soma (+) é permitida.
- 2) Para cada função indicada a seguir, prove os teoremas apresentados utilizando a linguagem Isar de forma detalhada, justificando cada passo de prova:
- a) Para a função do exercício "1a".

```
Prove $\forall$ $\in$ $\mathbb{N}$. (2() = 2
                          ). Utilize a função potência no Isabelle como "2^a".
```

b) Seja a seguinte especificação equacional recursiva para a função que realiza a soma de dois números Naturais no Isabelle:

```
primrec soma::"nat $\Rightarrow$ nat $\Rightarrow$ nat" where
 soma01: "soma x 0 = x"|
 soma02: "soma x (Suc y) = Suc (soma x y)"
```

```
Prove $\forall$,  $\in$ $\mathbb{N}$. ((, ) =  + )
Prove $\forall$,  $\in$ $\mathbb{N}$. ((, ) = (, ))
```

c) Seja a seguinte especificação equacional recursiva para a função que realiza a multiplicação de dois números Naturais no Isabelle.

```
primrec mult::"nat $\Rightarrow$ nat $\Rightarrow$ nat" where
 mult01: "mult x 0 = 0"|
```

## mult02: "mult x (Suc y) = soma x (mult x y)"

Prove $\forall$ $\in$ $\mathbb{N}$. ((, 0) = 0)

Prove $\forall$, $\in$ $\mathbb{N}$. ((, ) = ∗ )

Prove $\forall$, $\in$ $\mathbb{N}$. ((, ) = (, ))

d) Para a função do exercício "1c".

Prove 
$$\forall a \in \mathbb{N}. (fib(a+2) * fib(a) - (fib(a+1))^2 = (-1)^a)$$

Utilize a função potência no Isabelle como "a^b". Esse teorema é conhecido como "Identidade de Cassini" e foi apresentado pelo astrônomo francês Jean-Dominique Cassini em 1680.
