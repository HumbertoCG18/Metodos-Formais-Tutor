---
entry_id: "ex1"
title: "tiposindutivos\\ex1.dfy"
language: "dafny"
category: "codigo-professor"
unit: ""
source: "raw/code/professor/ex1.dfy"
---
# tiposindutivos\ex1.dfy

> **Linguagem:** dafny
> Extraído de: Tiposindutivos

```dafny
//tipos indutivos via datatype
//tipo de dados imutável

datatype Cor = Azul | Amarelo | Vermelho | Verde

predicate Gremista(c:Cor)
{
  c.Azul?
}

method Main()
{
  var c1 := Azul;
  var c2 := Cor.Vermelho;
  assert Gremista(c1);
  assert !Gremista(c2);
}

```
