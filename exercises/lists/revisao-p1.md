# Exercícios Revisão para P1

1) Encontre uma definição indutiva para o conjunto  $S = \{3, 4, 5, 8, 9, 12, 16, 17, 20, 24, 33, \dots\}$ .  
Dica: pense em como quebrar o conjunto  $S$  em conjuntos menores antes.

2) Assuma as árvores binárias definidas indutivamente como trabalhado em sala de aula.

$$\frac{}{\langle \rangle \in ArvBin(\tau)} \text{vazia}$$

$$\frac{L \in ArvBin(\tau) \quad R \in ArvBin(\tau), x \in \tau}{\langle L, x, R \rangle \in ArvBin(\tau)} \text{cons}$$

Encontre uma definição indutiva para um conjunto de árvores binárias “Natalinas” cujos primeiros elementos são apresentados a seguir:

3) Apresente uma definição equacional recursiva para a função  $max: List(\mathbb{N}) \rightarrow \mathbb{N}$ , que recebe uma lista de números Naturais e retorna o maior elemento dessa lista. Especifique formalmente as pré e pós-condições através de fórmulas da lógica de predicado. Se for necessário, apenas apresente a declaração de funções auxiliares e qual o propósito, sem a necessidade de implementá-las. Utilize obrigatoriamente a definição indutiva de listas trabalhadas em sala de aula.

$$\frac{}{[] \in List(\tau)} \text{empty}$$

$$\frac{L \in List(\tau), h \in \tau}{h:L \in List(\tau)} \text{cons}$$

4) Considere a seguinte definição de uma função por equações recursivas:

$f: \mathbb{N} \rightarrow \mathbb{N}$

*requer: True*

*garante:  $f(n) = (n + 1)^2$*

$$f(0) = 1 \qquad (f1)$$

$$f(n) = f(n - 1) + 2 \times n + 1 \quad \text{se } n > 0 \quad (f2)$$

Deseja-se provar por indução matemática que  $\forall n \in \mathbb{N}. f(n) = (n + 1)^2$ .

- Defina a propriedade geral a ser provada.
- Defina a propriedade para o caso base e apresente sua prova.
- Defina a propriedade para o passo da indução, a hipótese da indução e apresente sua prova.

5) Seja a seguinte definição equacional recursiva para a soma de dois números naturais:

$soma: \mathbb{N} \times \mathbb{N} \rightarrow \mathbb{N}$

*requer: True*

*garante:  $soma(m, n) = m + n$*

$$soma(0, n) = n \qquad (s1)$$

$$soma(m + 1, n) = soma(m, n) + 1 \quad (s2)$$

- Apresente uma definição equacional recursiva para a seguinte função:

$dobro: \mathbb{N} \rightarrow \mathbb{N}$

- Prove que  $\forall m \in \mathbb{N}. dobro(m) = soma(m, m)$ .

<!-- IMAGE_DESCRIPTION_ORPHANS -->
## Imagens Curadas

Descrições preservadas para imagens detectadas no documento, mas sem referência markdown compatível no corpo principal.

<!-- IMAGE_DESCRIPTION: revisao-p1-revisao-p1.pdf-0001-07.png -->
<!-- Tipo: diagrama -->
> **[Descrição de imagem]** A imagem apresenta uma sequência de quatro árvores binárias {T₀, T₁, T₂, T₃}, organizadas em ordem crescente de profundidade.
<!-- /IMAGE_DESCRIPTION -->
<!-- /IMAGE_DESCRIPTION_ORPHANS -->
