---
entry_id: "ex0"
title: "introducao\\ex0.dfy"
language: "dafny"
category: "codigo-professor"
unit: ""
source: "raw/code/professor/ex0.dfy"
---
# introducao\ex0.dfy

> **Linguagem:** dafny
> Extraído de: Introducao

```dafny
function Somar(m:nat, n:nat):nat
//A verificação depende da implementação concreta; diz-se que funções são transparentes
{
  if (m == 0)
  then n
  else Somar(m-1,n) + 1
}

predicate Par(x:nat)
//A verificação depende da implementação concreta; diz-se que predicados são transparentes
{
  x % 2 == 0
}

```
