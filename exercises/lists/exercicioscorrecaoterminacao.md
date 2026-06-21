{0}------------------------------------------------

# Exercícios

## Correção e Terminação

1) Acesse o seguinte tutorial do Dafny que tratam sobre a verificação da terminação:

- <https://dafny-lang.github.io/dafny/OnlineTutorial/Termination>

2) Analise o seguinte laço de repetição sobre duas variáveis inteiras.

```
while (x$\neq$y) {  
    x = x-1;  
    y = y+1;  
}
```

- a) Qual a condição sobre os valores das variáveis  $x$  e  $y$  implica na terminação do laço?
- b) Defina o estado da computação e mostre exemplos onde ocorre e não ocorre a terminação.
- c) Qual a variante de laço a ser utilizada de modo a provar a terminação?
- d) Implemente o respectivo algoritmo em Dafny e observe se a variante está correta.

3) Observe o seguinte método e responda: Dafny é capaz de verificar sua correção? Caso a resposta seja negativa, apresente as correções necessárias (exercício do tutorial do Dafny).

```
method m()  
{  
    var i, n := 0, 20;  
    while i != n  
        decreases n - i  
    {  
        i := i + 1;  
    }  
}
```

4) Seja a seguinte especificação equacional recursiva para o cálculo do tamanho de uma lista via recursão na cauda, defina a variante a ser utilizada em uma prova de terminação.

$tail\_len :: List(\mathbb{N}) \times \mathbb{N} \rightarrow \mathbb{N}$   
 $requer: true$   
 $garante: tail\_len([], a) = a \vee tail\_len([x_1, \dots, x_n], a) = n + a$   
 $tail\_len([], a) = a$   
 $tail\_len(x:L, a) = tail\_len(L, a + 1)$

{1}------------------------------------------------

5) Defina uma equação recursiva para o cálculo do número de folhas de uma árvore binária. Defina uma variante para ser utilizada em uma prova de terminação.