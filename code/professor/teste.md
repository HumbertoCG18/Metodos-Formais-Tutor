---
entry_id: "teste"
title: "classes_parte1\\teste.dfy"
language: "dafny"
category: "codigo-professor"
unit: ""
source: "raw/code/professor/teste.dfy"
---
# classes_parte1\teste.dfy

> **Linguagem:** dafny
> Extraído de: Classes Parte1

```dafny
class Contador
{
  ghost var valor: int

  //Invariante de classe
  ghost predicate Valid()
    reads this

  constructor ()
    ensures Valid()
    ensures valor == 0

  method incrementa()
    requires Valid()
    modifies this
    ensures Valid()
    ensures valor == old(valor) + 1

  method decrementa()
    requires Valid()
    modifies this
    ensures Valid()
    ensures valor == old(valor) - 1

  function getValor():int
    requires Valid()
    reads this
    ensures getValor() == valor
}

method Main()
{
  var c := new Contador();
  var v := c.getValor();
  assert v == 0;
  c.incrementa();
  var v2 := c.getValor();
  assert v2 == 1;
}
```
