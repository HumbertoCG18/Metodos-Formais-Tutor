{0}------------------------------------------------

# Exercícios

## Programação e Verificação com Dafny (Sequences)

1) Acesse o tutorial do Dafny. Execute as atividades indicadas em nas seguintes seções:

- Collection Types / Sequences <https://dafny-lang.github.io/dafny/OnlineTutorial/ValueTypes>
- Sequences <https://dafny-lang.github.io/dafny/OnlineTutorial/Sequences>

2) O seguinte predicado em Dafny pode ser utilizado para indicar se uma sequência possui os elementos em ordem crescente.

```
ghost predicate ordenado(s: seq<int>)
{
  forall i,j :: 0 <= i < j < |s| ==> s[i] <= s[j]
}
```

Construa uma versão recursiva para o mesmo predicado.

3) O seguinte predicado em Dafny pode ser utilizado para indicar se um elemento não pertence a um array.

```
ghost predicate naopertence(x:int, a:array<int>)
reads a
{
  forall i :: 0 <= i < a.Length ==> x != a[i]
}
```

Construa uma versão que não utiliza o quantificador universal para o mesmo predicado. Dica: use sequências como um tipo auxiliar.

4) O uso de sequências é muito útil para simplificar especificações sobre outros tipos de coleções, tal como arrays. Estamos interessados em calcular o somatório de todos os elementos de um array de inteiros. Implemente e prove correta sua especificação, utilizando obrigatoriamente *seq* para facilitar a construção das especificações necessárias. Primeiro, especifique uma função recursiva adequada para representar o somatório de elementos de uma sequência. Somente depois, implemente um método para calcular o somatório dos elementos de um array.