---
entry_id: "exercicio6"
title: "exercicios_arrays\\exercicio6.dfy"
language: "dafny"
category: "codigo-professor"
unit: ""
source: "raw/code/professor/exercicio6.dfy"
---
# exercicios_arrays\exercicio6.dfy

> **Linguagem:** dafny
> Extraído de: exercicios_arrays

```dafny
method IncrementaArray(a: array<int>)
  modifies a
  ensures forall i :: 0 <= i < a.Length ==> a[i] == old(a[i]) + 1
{
  var n := 0;
  while n != a.Length
    invariant 0 <= n <= a.Length
    invariant forall i :: 0 <= i < n ==> a[i] == old(a[i])+1
    invariant forall i :: n <= i < a.Length ==> a[i] == old(a[i])
  {
    a[n] := a[n] + 1;
    n := n + 1;
  }
}

```
