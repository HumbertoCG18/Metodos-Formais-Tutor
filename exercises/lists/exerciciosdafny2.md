<!-- EXEC_SUMMARY_START -->
## Sumário
> *Leia antes de varrer o arquivo. Vá direto à seção relevante para a pergunta do aluno.*

- **Exercícios**
- **Programação e Verificação com Dafny (Arrays)**

<!-- EXEC_SUMMARY_END -->
{0}------------------------------------------------

# Métodos Formais

Prof. Júlio Machado

## Exercícios

## Programação e Verificação com Dafny (Arrays)

1) Acesse o tutorial do Dafny. Execute as atividades indicadas em nas seguintes seções:

- Arrays
- Quantifiers
- Predicates
- Framing
- Binary Search

2) Complete as seguintes definições para encontrar o maior elemento de um array. Observe atentamente a diferença entre os dois métodos. Anote a implementação de modo que possa ser verificada a correção total.

```
method FindMaxIndex(a: array<int>) returns (i: int)
// Anote este metodo com pre e pos condicoes
{
    // Retorna o indice do maior elemento.
}
```

```
method FindMaxValue(a: array<int>) returns (m: int)
// Anote este metodo com pre e pos condicoes
{
    // Retorna o maior elemento.
}
```

3) Dado o seguinte predicado em Dafny, complete sua definição para indicar quando um array possua somente elementos distintos e em ordem crescente. Observe atentamente a necessidade de um frame de leitura. Depois crie um método Main para verificar o funcionamento.

```
ghost predicate Sorted(a: array<int>)
    reads a
{
}
```

4) A seguinte função em Dafny especifica o cálculo do produto dos números em um array. Ela é definida em termos de uma função recursiva auxiliar que retorna o produto dos números em um array entre as posições *from* e *to* (inclusive). Antes de prosseguir, procure descrever em termos do símbolo  $\prod$  (produtório) o que está sendo calculado.

```
ghost function Product(a: array<int>): int
    reads a
```

{1}------------------------------------------------

```

{
    ProductAux(a, 0, a.Length-1)
}

ghost function ProductAux(a: array<int>, from:nat, to:int): int
requires to < a.Length
reads a
{
    if from > to
    then 1
    else if from == to
        then a[to]
        else a[to] * ProductAux(a, from, to-1)
}

```

Implemente o seguinte método que calcula o produto dos números em um array. Anote corretamente as asserções necessárias para verificar a correção total do seu código no Dafny.

```

method ProductImpl(a: array<int>) returns (p: int)
{
}

```

5) Retome o exemplo de análise das invariantes de laço do problema de Busca Binária em um array. Compare o material do estudo de caso com a apresentação da seção “Binary Search” do tutorial do Dafny. Existe alguma diferença fundamental? Qual ou quais diferenças você consegue apontar?

```

ghost predicate sorted(a: array<int>)
reads a
{
    forall j, k :: 0 <= j < k < a.Length ==> a[j] <= a[k]
}

method BinarySearch(a: array<int>, value: int) returns (index: int)
requires sorted(a)
ensures 0 <= index ==> index < a.Length && a[index] == value
ensures index < 0 ==> forall k :: 0 <= k < a.Length ==> a[k] != value
{
    var low, high := 0, a.Length;
    while low < high
        invariant 0 <= low <= high <= a.Length
        invariant forall i :: 0 <= i < a.Length && !(low <= i < high) ==>
a[i] != value
    {
        var mid := (low + high) / 2;
        if a[mid] < value
        {
            low := mid + 1;
        }
    }
}

```

{2}------------------------------------------------

```
    else if value < a[mid]
    {
        high := mid;
    }
    else
    {
        return mid;
    }
}
return -1;
}
```

6) Escreva um método em Dafny que receba um array de inteiros e modifique o array incrementando de uma unidade cada elemento. Adicione todas as cláusulas de especificação necessárias e prove a correção do método. Utilize a seguinte assinatura para o método:

```
method IncrementaArray(a: array<int>)
    modifies a
    ensures forall i :: 0 <= i < a.Length ==> a[i] == old(a[i]) + 1
```