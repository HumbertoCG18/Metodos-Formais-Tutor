<!-- EXEC_SUMMARY_START -->
## Sumário
> *Leia antes de varrer o arquivo. Vá direto à seção relevante para a pergunta do aluno.*

- **Verificação de Modelos e Lógica Temporal**
- **Imagens Curadas**

<!-- EXEC_SUMMARY_END -->
{0}------------------------------------------------

# Exercícios
## Verificação de Modelos e Lógica Temporal

1) Apresente um Modelo de Kripke para a representação de uma lâmpada que pode ser ligada/desligada e que também pode queimar. Qual seriam as proposições adequadas para a modelagem?

2) Apresente um Modelo de Kripke para um buffer de duas posições. Sabe-se que cada posição do buffer pode estar cheia ou vazia. O buffer é criado inicialmente vazio e utiliza uma política de fila. Utilize o seguinte diagrama para facilitar a modelagem.

Diagrama de um buffer de duas posições. O diagrama mostra quatro estados representados por retângulos divididos em duas células. O primeiro retângulo (estado inicial) tem ambas as células vazias. Uma seta aponta para o segundo retângulo, onde a célula da esquerda contém uma bola preta. Uma seta aponta do segundo para o terceiro, onde a célula da direita contém uma bola preta. Uma seta aponta do terceiro para o quarto, onde ambas as células contêm bolas pretas. Há também setas de retroalimentação: uma do quarto para o primeiro, uma do terceiro para o segundo, e uma do segundo para o primeiro.

3) Seja o seguinte Modelo de Kripke. Para cada fórmula a seguir em LTL

- Encontre um caminho a partir do estado  $q3$  que satisfaça a fórmula;
- Determine se  $M, q3 \models \text{fórmula}$ .

Diagrama de um Modelo de Kripke com quatro estados: q1, q2, q3 e q4. q1 é um círculo contendo 'a'. q2 é um círculo contendo 'b' e possui uma seta de retroalimentação para si mesmo. q3 é um círculo contendo 'a'. q4 é um círculo contendo 'a,b'. As transições são: q1 para q2, q2 para q1, q2 para q3, q3 para q4, q4 para q3 e q4 para q1.

a)  $G a$

b)  $a U b$

c)  $a U (X(a \wedge \neg b))$

d)  $X(\neg b) \wedge G(\neg a \vee \neg b)$

{1}------------------------------------------------

4) Apresente fórmulas LTL para as seguintes propriedades:

a) Safety: a temperatura do reator não ultrapassará 1000.

b) Liveness: um programa que iniciou irá terminar.

c) Fairness: um processo que esteja pronto para ser executado será executado.

d) Safety: não é possível embarcar em um avião sem o passaporte ou sem a passagem.

5) Para cada árvore a seguir, indique qual das seguintes fórmulas CTL tem sua semântica representada:

| EF preto | EG preto | AF preto | AG preto | cinza EU preto | cinza AU preto |
|----------|----------|----------|----------|----------------|----------------|
|----------|----------|----------|----------|----------------|----------------|

|  |  |
|--|--|
|  |  |
|  |  |
|  |  |

Tree diagram 1: Root is gray. Left child is gray, right child is black. The left child has two black children, and the right child has one black child. All children have dashed lines below them. Tree diagram 2: Root is white. Left child is white, right child is white. The left child has two white children, and the right child has one white child. All children have dashed lines below them. Tree diagram 3: Root is black. Left child is black, right child is white. The left child has two black children, and the right child has one white child. All children have dashed lines below them. Tree diagram 4: Root is gray. Left child is gray, right child is black. The left child has two black children, and the right child has one gray child. All children have dashed lines below them. Tree diagram 5: Root is black. Left child is black, right child is black. The left child has two black children, and the right child has one black child. All children have dashed lines below them. Tree diagram 6: Root is white. Left child is white, right child is black. The left child has two white children, and the right child has one white child. All children have dashed lines below them.

<!-- IMAGE_DESCRIPTION: datalab-8642df2e3828b25d27362bec6d5a0eae_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagrama de um buffer de duas posições. O diagrama mostra quatro estados representados por retângulos divididos em duas células. O primeiro retângulo (estado inicial) tem ambas as células vazias. Uma seta aponta para o...
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-868ef3e0abb37916a7af1e923995f329_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagrama de um Modelo de Kripke com quatro estados: q1, q2, q3 e q4.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION_ORPHANS -->
## Imagens Curadas

Descrições preservadas para imagens detectadas no documento, mas sem referência markdown compatível no corpo principal.

<!-- IMAGE_DESCRIPTION: datalab-715219db84ec2a5622d09f9d822b4550_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Tree diagram 1: Root is gray. Left child is gray, right child is black. The left child has two black children, and the right child has one black child. All children have dashed lines below them. Tree diagram 2: Root is...
<!-- /IMAGE_DESCRIPTION -->
<!-- /IMAGE_DESCRIPTION_ORPHANS -->
