---
entry_id: "ex5"
title: "hoare\\ex5.dfy"
language: "dafny"
category: "codigo-professor"
unit: ""
source: "raw/code/professor/ex5.dfy"
---
# hoare\ex5.dfy

> **Linguagem:** dafny
> Extraído de: Hoare

```dafny
method Exemplo(x:int) returns (i:int)
  ensures i <= 0
{
  i := x;
  while i > 0
    //invariant true
    //decreases i
  {
    i := i-1;
  }
  assert i <= 0;
}

```
