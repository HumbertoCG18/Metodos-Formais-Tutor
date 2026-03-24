## Funções Recursivas sobre Árvores

## 1. Árvores polimórficas (definição indutiva)

Uma aplicação chave da recursão é a manipulação de árvores, já que as mesmas possuem uma definição inerentemente recursiva.

Informalmente, uma definição recursiva para uma árvore binária pode ser:

- Uma árvore vazia ou
- Uma árvore composta por duas sub-árvores, sendo uma esquerda e outra direita.

Uma definição formal pode ser dada através da definição de um conjunto indutivo para todas as árvores sobre um determinado tipo  $\tau$ :

$$\frac{L \in ArvBin(\tau)}{\langle L, x, R \rangle \in ArvBin(\tau), x \in \tau} cons$$

São exemplos de árvores de números naturais (elementos do conjunto  $ArvBin(\mathbb{N})$ :  $\langle \ \rangle, \langle \langle \ \rangle, 0, \langle \ \rangle, \langle \langle \ \rangle, 1, \langle \ \rangle, 0, \langle \langle \ \rangle, 2, \langle \ \rangle \rangle \rangle$ 

## 2. Árvores polimórficas (equações recursivas)

Um exemplo de especificação recursiva é o seguinte algoritmo para o cálculo do número de nodos de uma árvore binária:

$$numnodos: ArvBin(\tau) \to \mathbb{N}$$

$$numnodos(\langle L, x, R \rangle) = 0$$
 (1)
$$numnodos(\langle L, x, R \rangle) = 1 + numnodos(L) + numnodos(R)$$
 (2)

 $\label{lem:lem:lem:lem:lem:lem:lem:lem:lem:lem:$ 

```
\begin{aligned} & numnodos(\langle\langle\langle\langle \rangle, 1, \langle \rangle\rangle, 0, \langle\langle \rangle, 2, \langle \rangle\rangle\rangle)) \\ &= 1 + numnodos(\langle\langle \rangle, 1, \langle \rangle\rangle) + numnodos(\langle\langle \rangle, 2, \langle \rangle\rangle) \text{ (pela regra 2)} \\ &= 1 + \left(1 + numnodos(\langle \rangle) + numnodos(\langle \rangle)\right) + \left(1 + numnodos(\langle \rangle) + numnodos(\langle \rangle)\right) \text{ (pela regra 2)} \end{aligned}
```

$$= 1 + (1 + 0 + 0) + (1 + 0 + 0)$$
 (pela regra 1)

= 3 (por aritmética)
