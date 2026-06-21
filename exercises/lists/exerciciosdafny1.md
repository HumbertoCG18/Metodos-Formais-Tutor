{0}------------------------------------------------

# Exercícios

## Programação e Verificação com Dafny

1) Acesse o tutorial do Dafny e leia as seguintes seções:

- Introduction
- Methods
- Pre and Post Conditions
- Assertions
- Functions
- Loop Invariants
- Termination

2) Compute uma função Fibonacci. O primeiro código é a especificação recursiva da função. O segundo código é a implementação iterativa. Anote a implementação iterativa de modo que possa ser verificada pelo Dafny.

```
ghost function Fib(n: nat): nat
{
  if n < 2 then n else Fib(n-2) + Fib(n-1)
}

method Compute_Fib(n: nat) returns (x: nat)
ensures x == Fib(n)
{
  x := 0;
  var y := 1;
  var i := 0;
  while i < n
  {
    x, y := y, x + y;
    i := i + 1;
  }
}
```

3) Especifique uma função recursiva  $Sum: \mathbb{N} \rightarrow \mathbb{N}$ , que calcule a soma dos naturais no intervalo  $[0, n]$ . Depois, constrói um método que implementa essa função e verifique sua correção em Dafny.

```
ghost function Sum(n: nat): nat
{
}
```

{1}------------------------------------------------

```
method Compute_Sum(n: nat) returns (s: nat)
ensures s == Sum(n)
{
}
}
```

4) Sem alterar o código de implementação a seguir, usando apenas as anotações de especificação, faça com que o seguinte método seja verificado no Dafny. Dica: esse método está calculando certos somatórios.

```
method Cube(N: int) returns (c: int)
  requires 0 <= N
  ensures c == N*N*N
{
  c := 0;
  var n := 0;
  var k := 1;
  var m := 6;
  while n < N
  {
    c := c + k;
    k := k + m;
    m := m + 6;
    n := n + 1;
  }
}
```