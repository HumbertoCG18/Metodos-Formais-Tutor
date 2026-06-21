---
entry_id: "ex4"
title: "terminacao\\ex4.dfy"
language: "dafny"
category: "codigo-professor"
unit: ""
source: "raw/code/professor/ex4.dfy"
---
# terminacao\ex4.dfy

> **Linguagem:** dafny
> Extraído de: Terminacao

```dafny
method Collatz(x: nat)
  decreases * //desabilita a verificação da terminação
{
  var n := x;
  while 1 < n
    decreases * //desabilita a verificação da terminação
  {
    n := if n % 2 == 0 then n / 2 else n * 3 + 1;
  }
}

```
