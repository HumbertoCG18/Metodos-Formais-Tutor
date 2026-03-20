## Funções Recursivas sobre Árvores

## 1. Árvores polimórficas (definição indutiva)

Uma aplicação chave da recursão é a manipulação de árvores, já que as mesmas possuem uma definição inerentemente recursiva.

Informalmente, uma definição recursiva para uma árvore binária pode ser:

- Uma árvore vazia ou
- Uma árvore composta por duas sub-árvores, sendo uma esquerda e outra direita.

Uma definição formal pode ser dada através da definição de um conjunto indutivo para todas as árvores sobre um determinado tipo 𝜏 :

$$5 v a z i a$$

$$\overline { \langle \ \rangle \in A r v B i n ( \tau ) } \ v a z i a \\ \frac { L \in A r v B i n ( \tau ) } { \langle L , x , R \rangle \in A r v B i n ( \tau ) } \, c o n s$$

São exemplos de árvores de números naturais (elementos do conjunto 𝐴𝑟𝑣𝐵𝑖𝑛(ℕ ): 〈 〉, 〈〈 〉, 0, 〈 〉〉, 〈〈〈 〉, 1, 〈 〉〉, 0, 〈〈 〉, 2, 〈 〉〉〉

## 2. Árvores polimórficas (equações recursivas)

Um exemplo de especificação recursiva é o seguinte algoritmo para o cálculo do número de nodos de uma árvore binária:

𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠:𝐴𝑟𝑣𝐵𝑖𝑛(𝜏) → ℕ

$$n u m n o d o s ( \langle \ \rangle ) = 0$$

$$n u m n o d o s ( ( L , x , R ) ) = 1 + n u m n o d o s ( L ) + n u m n o d o s ( R )$$

Um exemplo de computação para 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈〈〈 〉, 1, 〈 〉〉, 0, 〈〈 〉, 2, 〈 〉〉〉) :

```
𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈〈〈 〉, 1, 〈 〉〉, 0, 〈〈 〉, 2, 〈 〉〉〉) = 1 + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈〈 〉, 1, 〈 〉〉) + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈〈 〉, 2, 〈 〉〉) (pela regra 2) = 1 + (1 + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈 〉) + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠(〈 〉)) + (1 + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠( ) + 𝑛𝑢𝑚𝑛𝑜𝑑𝑜𝑠( )) (pela regra 2)
```

= 1 + (1 + 0 + 0) + (1 + 0 + 0) (pela regra 1) = 3 (por aritmética)