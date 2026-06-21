{0}------------------------------------------------

# Exercícios Revisão para P1

1) Encontre uma definição indutiva para o conjunto  $S=\{3,4,5,8,9,12,16,17,20,24,33,\dots\}$ .  
Dica: pense em como quebrar o conjunto  $S$  em conjuntos menores antes.

2) Assuma as árvores binárias definidas indutivamente como trabalhado em sala de aula.

$$\frac{}{\langle \rangle \in ArvBin(\tau)} \text{vazia}$$

$$\frac{L \in ArvBin(\tau) \quad R \in ArvBin(\tau), x \in \tau}{\langle L, x, R \rangle \in ArvBin(\tau)} \text{cons}$$

Encontre uma definição indutiva para um conjunto de árvores binárias “Natalinas” cujos primeiros elementos são apresentados a seguir:

```

graph TD
    T1((a))
    T2((a)) --- T2L((a))
    T2 --- T2R((a))
    T3((a)) --- T3L((a))
    T3 --- T3R((a))
    T3L --- T3LL((a))
    T3R --- T3RR((a))
    T4((a)) --- T4L((a))
    T4 --- T4R((a))
    T4L --- T4LL((a))
    T4R --- T4RR((a))
    
```

Diagram showing four binary trees with nodes labeled 'a'. The first tree has one node. The second tree has a root with two children. The third tree has a root with two children, and the left child has two children. The fourth tree has a root with two children, and both the left and right children have two children each.

3) Apresente uma definição equacional recursiva para a função  $max: List(\mathbb{N}) \rightarrow \mathbb{N}$ , que recebe uma lista de número Naturais e retorna o maior elemento dessa lista. Especifique formalmente as pré e pós-condições através de fórmulas da lógica de predicado. Se for necessário, apenas apresente a declaração de funções auxiliares e qual o propósito, sem a necessidade de implementá-las. Utilize obrigatoriamente a definição indutiva de listas trabalhadas em sala de aula.

$$\frac{}{[] \in List(\tau)} \text{empty}$$

$$\frac{L \in List(\tau), h \in \tau}{h: L \in List(\tau)} \text{cons}$$

{1}------------------------------------------------

4) Considere a seguinte definição de uma função por equações recursivas:

$$f: \mathbb{N} \rightarrow \mathbb{N}$$

*requer: True*

$$\text{garante: } f(n) = (n + 1)^2$$

$$f(0) = 1 \qquad (f1)$$

$$f(n) = f(n - 1) + 2 \times n + 1 \quad \text{se } n > 0 \quad (f2)$$

Deseja-se provar por indução matemática que  $\forall n \in \mathbb{N}. f(n) = (n + 1)^2$ .

- a) Defina a propriedade geral a ser provada.
- b) Defina a propriedade para o caso base e apresente sua prova.
- c) Defina a propriedade para o passo da indução, a hipótese da indução e apresente sua prova.

5) Seja a seguinte definição equacional recursiva para a soma de dois números naturais:

$$\text{soma: } \mathbb{N} \times \mathbb{N} \rightarrow \mathbb{N}$$

*requer: True*

$$\text{garante: } \text{soma}(m, n) = m + n$$

$$\text{soma}(0, n) = n \qquad (s1)$$

$$\text{soma}(m + 1, n) = \text{soma}(m, n) + 1 \quad (s2)$$

- a) Apresente uma definição equacional recursiva para a seguinte função:

$$\text{dobro: } \mathbb{N} \rightarrow \mathbb{N}$$

- b) Prove que  $\forall m \in \mathbb{N}. \text{dobro}(m) = \text{soma}(m, m)$ .

{2}------------------------------------------------

Gabarito:

1)

$$S = \{3, 5, 9, 17, 33, \dots\} \cup \{4, 8, 12, 16, 20, \dots\}$$

Base:

$$\overline{3 \in S}$$

$$\overline{4 \in S}$$

Indução:

$$\frac{x \in S, x \text{ é ímpar}}{2x - 1 \in S}$$

$$\frac{x \in S, x \text{ é par}}{x + 4 \in S}$$

2)

**Basis:**  $\langle \langle \rangle, a, \langle \rangle \rangle \in S$   
**Induction:**  $\langle L, a, R \rangle \in S$  implies  $\langle \langle L, a, \langle \rangle \rangle, a, \langle \langle \rangle, a, R \rangle \rangle \in S$

Diagram illustrating the construction of binary trees from a single node 'a'. The first tree is a single node 'a'. The second tree has root 'a' with two children 'a'. The third tree has root 'a' with left child 'a' (red) and right child 'a' (blue); the red child has a red child 'a', and the blue child has a blue child 'a'. The fourth tree has root 'a' with left child 'a' (black) and right child 'a' (black); the left child has a red child 'a', and the right child has a blue child 'a'. Dashed green lines indicate the recursive construction of the trees.

Define function **left, right**:  $\text{Trees} \rightarrow \text{Trees}$  as

$$\mathbf{left} (\langle L, a, R \rangle) = L$$

and

$$\mathbf{right} (\langle L, a, R \rangle) = R$$

**Revised Inductive Step:**  $T \in S$  implies

$$\langle \langle \mathbf{left}(T), a, \langle \rangle \rangle, a, \langle \langle \rangle, a, \mathbf{right}(T) \rangle \rangle \in S$$

3)

$$\mathbf{max}: \text{List}(\mathbb{N}) \rightarrow \mathbb{N}$$

$$\text{Pré: } L.\text{tamanho} > 0$$

$$\text{Pós: } \mathbf{max}(L) = \max L$$

$$(\forall i \in \mathbb{N}. i < L.\text{tamanho} \Rightarrow L[i] \leq \max) \wedge$$

$$(\exists i \in \mathbb{N}. i < L.\text{tamanho} \wedge L[i] = \max)$$

$$\mathbf{max}(h: L) = \mathbf{maxaux}(L, h)$$

{3}------------------------------------------------

$maxaux: List(\mathbb{N}) \times \mathbb{N} \rightarrow \mathbb{N}$

Pré: *true*

Pós:  $maxaux(L, h) = maior(max, h)$

onde  $max$  é tal que

$((\forall i \in \mathbb{N}. i < L.tamanho \Rightarrow L[i] \leq max) \wedge$

$(\exists i \in \mathbb{N}. i < L.tamanho \wedge L[i] = max))$

$maxaux([], m) = m$

$maxaux(h: L, m) = maxaux(L, maior(h, m))$

4)

a)

$$P(n) \cong f(n) = (n + 1)^2$$

b)

Queremos mostrar que:  $P(0) \cong f(0) = (0 + 1)^2$

Prova:

$$f(0) = 1 \text{ (por } f1)$$

$$= 0 + 1 \text{ (por arit. alg.)}$$

$$= (0 + 1) * 1 \text{ (por arit. alg.)}$$

$$= (0 + 1) * (0 + 1) \text{ (por arit. alg.)}$$

$$= (0 + 1)^2$$

q.e.d.

c)

Seja  $x \in \mathbb{N}$  arbitrário.

Hipótese de Indução:  $P(x) \cong f(x) = (x + 1)^2$

Queremos mostrar que:  $P(x + 1) \cong f(x + 1) = (x + 2)^2$

Prova:

$$f(x + 1) = f(x) + 2 \times (x + 1) + 1$$

$$= f(x) + 2x + 3 \text{ (por arit. alg.)}$$

$$= (x + 1)^2 + 2x + 3 \text{ (por HI)}$$

$$= x^2 + 2x + 1 + 2x + 3 \text{ (por arit. alg.)}$$

{4}------------------------------------------------

$$= x^2 + 4x + 4 \text{ (por arit. alg.)}$$

$$= (x + 2)^2 \text{ (por arit. alg.)}$$

q.e.d.

5)

a)

$dobro: \mathbb{N} \rightarrow \mathbb{N}$

$$dobro(0) = 0$$

$$dobro(x + 1) = dobro(x) + 2$$

b)

$$P(m) \equiv dobro(m) = soma(m, m)$$

Base:

$$P(0) \equiv dobro(0) = soma(0, 0)$$

$$dobro(0)$$

$$= 0 \text{ (por d1)}$$

$$= 0 + 0 \text{ (por arit. alg.)}$$

$$= soma(0, 0) \text{ (por pós soma)}$$

q.e.d.

Passo de indução:

$$P(m) \Rightarrow P(m + 1)$$

Seja  $x \in \mathbb{N}$  arbitrário.

Assumir por HI que  $P(x) \equiv dobro(x) = soma(x, x)$ .

Provar  $P(x + 1) \equiv dobro(x + 1) = soma(x + 1, x + 1)$

$$dobro(x + 1)$$

$$= dobro(x) + 2 \text{ (por d2)}$$

$$= soma(x, x) + 2 \text{ (por HI)}$$

$$= x + x + 2 \text{ (por pós soma)}$$

$$= (x + 1) + (x + 1) \text{ (por arit. alg.)}$$

$$= soma(x + 1, x + 1) \text{ (por pós soma)}$$

q.e.d.

<!-- IMAGE_DESCRIPTION_ORPHANS -->
## Imagens Curadas

Descrições preservadas para imagens detectadas no documento, mas sem referência markdown compatível no corpo principal.

<!-- IMAGE_DESCRIPTION: datalab-8642df2e3828b25d27362bec6d5a0eae_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram showing four binary trees with nodes labeled 'a'.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-aec7150315249ac202a63cc0e32323b8_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the construction of binary trees from a single node 'a'.
<!-- /IMAGE_DESCRIPTION -->
<!-- /IMAGE_DESCRIPTION_ORPHANS -->
