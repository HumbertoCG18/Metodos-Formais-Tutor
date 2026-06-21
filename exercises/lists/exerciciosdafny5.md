{0}------------------------------------------------

# Exercícios

## Programação e Verificação com Dafny (Classes)

1) Quando utilizamos objetos, Dafny necessita da descrição clara dos objetos que podem ter seus campos lidos ou modificados através do conceito de *frames* de leitura/escrita. Considere a seguinte classe e explique o problema que o Dafny encontrou. O quê está faltando na especificação?

```
class WrapArray
{
  var intarray: array<int>
  constructor (i:int)
    requires i > 0
  {
    intarray := new int[i];
  }
  method init(i: int)
    modifies intarray
  {
    var index: int := 0;
    while (index < intarray.Length)
    {
      intarray[index] := i;
      index := index+1;
    }
  }
}

method Main()
{
  var sh:= new WrapArray(5);
  sh.init(4);
}
```

2) Implemente e verifique em Dafny a correção de uma classe que represente uma ContaCorrente com operações de depósito, saque e consulta de saldo. Sabe-se que os objetos ContaCorrente possuem um valor máximo de saldo negativo garantido pelo banco e que jamais poderão extrapolar esse limite.

{1}------------------------------------------------

3) Em sala de aula foi apresentada a especificação de uma estrutura de dados do tipo fila de tamanho limitado e sua implementação através de um array. Modifique a especificação para suportar uma fila de tamanho ilimitado (lembre-se que agora não existe mais o impedimento de inserção caso o array esteja cheio, necessitando a substituição por um array maior). Altere de maneira adequada a implementação com base em arrays. Verifique que seu código atingiu a correção total em Dafny.

4) Acesso os exemplos de implementação de estruturas de dados disponibilizado no Moodle e procure entender o funcionamento das especificações de propriedades sobre as estruturas de listas encadeadas de nodos.