---
entry_id: "contadorv3-inicio"
title: "classes_parte1\\contadorV3_inicio.dfy"
language: "dafny"
category: "codigo-professor"
unit: ""
source: "raw/code/professor/contadorv3-inicio.dfy"
---
# classes_parte1\contadorV3_inicio.dfy

> **Linguagem:** dafny
> Extraído de: Classes Parte1

```dafny
class Celula
{
  var dados: int
  constructor ()
    ensures dados == 0
  {
    dados := 0;
  }
}

class Contador
{
  //Contador é representado pelo número
  //de operações de incremento e decremento
  //armazenadas em um objeto Celula
  var incs: Celula
  var decs: Celula
  //valor é uma representação abstrata
  ghost var valor: int

  ghost predicate Valid()
    reads this
    //Como resolver a questão de quais objetos Celula temos acesso? Frames dinâmicos!
  {
    incs != decs
    && incs.dados >= 0
    && decs.dados >= 0
    && valor == incs.dados - decs.dados
  }

  constructor ()
    ensures Valid()
    ensures valor == 0

  method Incrementa()
    requires Valid()
    modifies this
    ensures Valid()
    ensures valor == old(valor) + 1

  method Decrementa()
    requires Valid()
    modifies this
    ensures Valid()
    ensures valor == old(valor) - 1

  function GetValor():int
    requires Valid()
    reads this, incs, decs
    ensures GetValor() == valor
}

method Main()
{
  var c := new Contador();
  c.Incrementa();
  c.Incrementa();
  c.Decrementa();
  c.Incrementa();
  assert c.valor == 2;
}

```
