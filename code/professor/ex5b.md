---
entry_id: "ex5b"
title: "colecoes_arrays\\ex5b.dfy"
language: "dafny"
category: "codigo-professor"
unit: ""
source: "raw/code/professor/ex5b.dfy"
---
# colecoes_arrays\ex5b.dfy

> **Linguagem:** dafny
> Extraído de: Colecoes Arrays

```dafny
method Busca(a:array<int>, x:int) returns (r:int)
  ensures 0 <= r ==> r < a.Length && a[r] == x
  ensures r < 0 ==> forall i :: 0 <= i < a.Length ==> a[i] != x
{
  r :=0; 
  while r < a.Length
    invariant 0 <= r <= a.Length
    invariant forall i :: 0 <= i < r ==> a[i] != x
    {
      if a[r]==x
      {
        return;
      }
      r := r +  1;
    }
  r := -1;
}

```
