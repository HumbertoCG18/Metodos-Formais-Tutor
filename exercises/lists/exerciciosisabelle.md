---
entry_id: "exerciciosisabelle"
title: "Exerciciosisabelle"
backend: "pymupdf4llm"
source_pdf: "raw/pdfs/listas/exerciciosisabelle.pdf"
page_range: "1-2"
---
## **Métodos Formais** 

## **Prof. Júlio Machado** 

## **Exercícios** 

## **Formalização e prova de algoritmos como equações recursivas no Isabelle** 

- 1) Nos exercícios a seguir, descreva no Isabelle as equações recursivas referentes a cada função sobre os números Naturais. Lembre-se que a recursão deve ser feita sobre a estrutura indutiva do conjunto _nat_ do Isabelle, ou seja, sobre _0_ e o construtor _Suc_ . 

a) Especifique uma função para calcular a função potência de dois ( 2[𝑛] ). Utilize a função 𝑝𝑜𝑡2: $\mathbb{N}$→ $\mathbb{N}$ . A utilização de operações de multiplicação (*) é permitida. 

b) Especifique uma função para calcular o fatorial de um número. Utilize a função 𝑓𝑎𝑡: $\mathbb{N}$→$\mathbb{N}$ . A utilização de operações de multiplicação (*) é permitida. 

c) Especifique uma função para calcular o n-ésimo termo da série de Fibonacci. Utilize a função 𝑓𝑖𝑏: $\mathbb{N}$→$\mathbb{N}$ . A utilização de operações de soma (+) é permitida. 

- 2) Para cada função indicada a seguir, prove os teoremas apresentados utilizando a linguagem Isar de forma detalhada, justificando cada passo de prova: 

- a) Para a função do exercício “1a”. 

Prove $\forall$𝑎$\in$$\mathbb{N}$. (𝑝𝑜𝑡2(𝑎) = 2[𝑎] ) . Utilize a função potência no Isabelle como “2^a”. 

b) Seja a seguinte especificação equacional recursiva para a função que realiza a soma de dois números Naturais no Isabelle: 

`primrec soma::"nat` $\Rightarrow$ `nat` $\Rightarrow$ `nat" where soma01: "soma x 0 = x"| soma02: "soma x (Suc y) = Suc (soma x y)"` 

Prove $\forall$𝑎, 𝑏$\in$$\mathbb{N}$. (𝑠𝑜𝑚𝑎(𝑎, 𝑏) = 𝑎+ 𝑏) 

Prove $\forall$𝑎, 𝑏$\in$$\mathbb{N}$. (𝑠𝑜𝑚𝑎(𝑎, 𝑏) = 𝑠𝑜𝑚𝑎(𝑏, 𝑎)) 

c) Seja a seguinte especificação equacional recursiva para a função que realiza a multiplicação de dois números Naturais no Isabelle. 

`primrec mult::"nat` $\Rightarrow$ `nat` $\Rightarrow$ `nat" where mult01: "mult x 0 = 0"|` 

--- end of page.page_number=1 ---

```
  mult02: "mult x (Suc y) = soma x (mult x y)"
```

Prove $\forall$𝑎$\in$$\mathbb{N}$. (𝑚𝑢𝑙𝑡(𝑎, 0) = 0) 

Prove $\forall$𝑎, 𝑏$\in$$\mathbb{N}$. (𝑚𝑢𝑙𝑡(𝑎, 𝑏) = 𝑎∗𝑏) 

Prove $\forall$𝑎, 𝑏$\in$$\mathbb{N}$. (𝑚𝑢𝑙𝑡(𝑎, 𝑏) = 𝑚𝑢𝑙𝑡(𝑏, 𝑎)) 

d) Para a função do exercício “1c”. 

Prove $\forall$𝑎$\in$$\mathbb{N}$. (𝑓𝑖𝑏(𝑎+ 2) ∗𝑓𝑖𝑏(𝑎) −(𝑓𝑖𝑏(𝑎+ 1))[2] = (−1)[𝑎] ) 

Utilize a função potência no Isabelle como “a^b”. Esse teorema é conhecido como “Identidade de Cassini” e foi apresentado pelo astrônomo francês Jean-Dominique Cassini em 1680.
