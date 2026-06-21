<!-- EXEC_SUMMARY_START -->
## Sumário
> *Leia antes de varrer o arquivo. Vá direto à seção relevante para a pergunta do aluno.*

- **Introdução**
- **Introdução**
- **Introdução**
- **Introdução**
- **Introdução**
- **Introdução**
- **SISTEMAS ---**
  - Sistemas
  - Sistemas Concorrentes
- **Propriedades**
  - Propriedades
  - Propriedades
  - Justiça
  - Justiça
  - Justiça
  - Justiça
- **MODELOS ---**
  - Modelo
- **Modelo**
- **LÓGICA TEMPORAL ---**
  - Lógica Temporal
  - Lógica Temporal
  - Lógica Temporal
  - Lógica Temporal
  - CTL
- **CTL - Sintaxe**
- **CTL - Semântica**
- **CTL - Semântica**
- **CTL- Semântica**
- **CTL - Semântica**
- **CTL - Semântica**
- **CTL - Semântica**
- **CTL**
- **CTL - Exemplo**
- **CTL - Exemplo**
- **LTL versus CTL**
- **LTL versus CTL**
- **LTL versus CTL**
- **LTL versus CTL**
- **LTL versus CTL**
- **LTL versus CTL**

<!-- EXEC_SUMMARY_END -->
<!-- DATALAB_CHUNK 1: pages 1-20 -->

{0}------------------------------------------------

# MÉTODOS FORMAIS ---

Prof. Júlio Machado

{1}------------------------------------------------

# VERIFICAÇÃO DE MODELOS

---

Conceitos Básicos

{2}------------------------------------------------
## Introdução

```
graph TD; SS([system specification]) --> DP[Design Process]; DP --> PP([product or prototype]); PP --> V[Verification]; SS --> P([properties]); P --> V; V --> BF([bug(s) found]); V --> NBF([no bugs found]);
```

The diagram illustrates the process of a posteriori system verification. It starts with a 'system specification' (oval) which leads to a 'Design Process' (rectangle). The 'Design Process' produces a 'product or prototype' (oval). This product is then used in 'Verification' (rectangle). Additionally, the 'system specification' is used to define 'properties' (oval), which are also used in 'Verification'. The 'Verification' process results in either 'bug(s) found' (oval) or 'no bugs found' (oval).

Schematic view of an a posteriori system verification process.

Figure 1.2: Schematic view of an a posteriori system verification.

{3}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-1b7d539e02a202c2cf2d97698b911447_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Schematic view of an a posteriori system verification process.
<!-- /IMAGE_DESCRIPTION -->
## Introdução

```
graph TD; requirements([requirements]) --> Formalizing[Formalizing]; Formalizing --> property_spec([property specification]); system([system]) --> Modeling[Modeling]; Modeling --> system_model([system model]); property_spec --> Model_Checking[Model Checking]; system_model --> Model_Checking; system_model --> Simulation[Simulation]; Model_Checking --> satisfied([satisfied]); Model_Checking --> violated([violated + counterexample]); Simulation --> location_error([location error]);
```

The diagram illustrates the model-checking approach through two parallel vertical flows that converge. The left flow starts with an oval labeled *requirements*, which points to a rectangular box labeled **Formalizing**. This box points to an oval labeled *property specification*. The right flow starts with an oval labeled *system*, which points to a rectangular box labeled **Modeling**. This box points to an oval labeled *system model*. Both the *property specification* and *system model* ovals have arrows pointing to a central rectangular box labeled **Model Checking**. From **Model Checking**, two arrows point down to ovals labeled *satisfied* and *violated + counterexample*. Additionally, an arrow from the *system model* oval points down to a rectangular box labeled **Simulation**. Finally, an arrow from **Simulation** points to an oval labeled *location error*.

Schematic view of the model-checking approach flowchart

Figure 1.4: Schematic view of the model-checking approach.

{4}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-2fa4a1bf91d0f34e87c689fbc1211fe3_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Schematic view of the model-checking approach flowchart
<!-- /IMAGE_DESCRIPTION -->
## Introdução

- Verificação de modelos (*Model Checking*) refere-se ao problema de verificar automaticamente se um MODELO que representa um SISTEMA atende a uma dada ESPECIFICAÇÃO
- Formalmente:
  - Dada uma propriedade desejada do sistema, expressa em uma lógica temporal  $p$
  - Um estrutura  $M$  que representa o modelo do sistema
  - Um estado inicial  $s$  do modelo

$$M, s \models p$$

{5}------------------------------------------------
## Introdução

- Exemplos de sistemas:
  - Hardware
  - Software
    - De tempo real
    - De missão crítica
      - Aqueles em que qualquer falha pode resultar em grandes perdas (humanas, econômicas, etc)
  - Protocolos de comunicação
  - Algoritmos e protocolos de criptografia
  - Algoritmos concorrentes
  - Algoritmos paralelos
  - Algoritmos distribuídos

{6}------------------------------------------------
## Introdução

- Exemplos de propriedades:
  - O sistema nunca atinge um estado de erro
  - O sistema não pode reiniciar sem que antes o botão de *reset* seja pressionado
  - Sempre que o botão de *reset* for pressionado, o sistema será reiniciado

{7}------------------------------------------------
## Introdução

- O processo de verificação consiste em começar com um modelo e descobrir se as hipóteses feitas pelo usuários são válidas no modelo
- Caso as hipóteses não sejam válidas o verificador produz contra-exemplos que consistem em trechos de execução, mostrando valores para os quais as propriedades se tornam falsas

{8}------------------------------------------------
## SISTEMAS ---

Concorrência

{9}------------------------------------------------
### Sistemas

- O tipo de sistema de interesse são os chamados sistemas reativos concorrentes
- Um sistema reativo é um que reage ao ambiente e não se espera que termine
  - Ex.: sistemas operacionais, sistemas embarcados, etc
- Um sistema concorrente é aquele que possui mais de uma linha de execução simultânea e potencialmente interagindo umas com as outras

{10}------------------------------------------------
### Sistemas Concorrentes

- Fenômenos da concorrência:
  - bloqueio ou “deadlock” – situação em que processos estão em bloqueio mútuo
  - “livelock” – situação em que processos esperam de forma ocupada (computam mas não fazem progresso)
  - postergação infinita ou “starvation” – situação em que um processo pode ser indefinidamente preterido em uma decisão de escalonamento de processos
  - exclusão mútua – situação no qual no máximo um processo está na chamada região crítica (região de acesso a recursos compartilhados entre vários processos que deve ser executada de maneira exclusiva)

{11}------------------------------------------------
## Propriedades

- Existem vários tipos de propriedades desejáveis em um sistema concorrente:
  - Segurança (“safety”) – “nada de mau poderá acontecer”
  - Vivacidade (“liveness”) – “eventualmente algo de bom irá acontecer”

{12}------------------------------------------------
### Propriedades

- Nos sistemas sequenciais já estudados, várias propriedades já foram observadas:
  - Invariantes
  - Correção parcial é uma propriedade de segurança
    - Se um programa termina, o estado é correto
  - Terminação é uma propriedade de vivacidade
    - Um programa termina
  - Correção total é uma combinação de ambas

{13}------------------------------------------------
### Propriedades

- Em sistemas concorrentes:
  - Ausência de “deadlock” é uma propriedade de segurança
  - Observação da exclusão mútua é uma propriedade de segurança
  - Ausência de “starvation” é uma propriedade de vivacidade
  - Ausência de “livelock” é uma propriedade de vivacidade

{14}------------------------------------------------
### Justiça

- A discussão das propriedades de vivacidade depende diretamente da justiça (“fairness”) do sistema
- Condições de “fairness” especificam garantias de um processo ter condições de executar independentemente do que outros processos estão realizando
- Quando muitos processos estão aptos a realizar uma ação, uma política de escalonamento determina qual irá executar a seguir

{15}------------------------------------------------
### Justiça

- Uma política de escalonamento é incondicionalmente justa (“unconditional fairness”) se toda ação não condicional possível acontece eventualmente

{16}------------------------------------------------
### Justiça

- Uma política de escalonamento é fracamente justa (“weak fairness”) se
  - Ela é incondicionalmente justa e
  - Toda ação condicional possível é executada eventualmente, assumindo que sua condição (guarda) permaneça válida

{17}------------------------------------------------
### Justiça

- Uma política de escalonamento é fortemente justa (“strong fairness”) se
  - Ela é incondicionalmente justa e
  - Toda ação condicional possível é executada eventualmente se sua condição (guarda) se tornar verdadeira com frequência infinita (“infinitely often”)

{18}------------------------------------------------
## MODELOS ---

Semântica

{19}------------------------------------------------
### Modelo

- Um modelo é um sistema de transição de estados
- Modelo de Kripke
  - Máquina de transição de estados finita com estados etiquetados por proposições atômicas

Diagrama de um Modelo de Kripke com três estados:  $s_0$ ,  $s_1$  e  $s_2$ . Os estados são representados por círculos contendo proposições atômicas:

- $s_0$  contém  $p, q$
- $s_1$  contém  $q, r$
- $s_2$  contém  $r$

As transições entre os estados são:

- Uma seta curva de  $s_1$  para  $s_0$ .
- Uma seta curva de  $s_0$  para  $s_1$ .
- Uma seta curva de  $s_0$  para  $s_2$ .
- Uma seta curva de  $s_1$  para  $s_2$ .
- Uma seta curva de  $s_2$  para  $s_2$  (auto-loop).

Diagrama de um Modelo de Kripke com três estados s0, s1 e s2.

Diagrama de um Modelo de Kripke com três estados:  $x=0$ ,  $x=1$  e  $x=2$ . Os estados são representados por círculos contendo proposições atômicas:

- $x=0$  contém  $x=0$  e  $y=2$
- $x=1$  contém  $x=1$  e  $y=1$
- $x=2$  contém  $x=2$  e  $y=0$

As transições entre os estados são:

- Uma seta curva de  $x=0$  para  $x=1$ .
- Uma seta curva de  $x=1$  para  $x=0$ .
- Uma seta curva de  $x=1$  para  $x=2$ .
- Uma seta curva de  $x=2$  para  $x=1$ .

Diagrama de um Modelo de Kripke com três estados x=0, x=1 e x=2.

<!-- DATALAB_CHUNK 2: pages 21-40 -->

{20}------------------------------------------------

# Modelo

- Definição:  $M = \langle S, I, T, P, L \rangle$ 
  - $S$  é um conjunto finito de estados
  - $I \subseteq S$  é um conjunto de estados iniciais
  - $T \subseteq S \times S$  é uma relação de transição tal que
$$\forall s \in S. \exists s' \in S. (s, s') \in T$$
  - $P$  é um conjunto de proposições atômicas
  - $L: S \rightarrow 2^P$  é uma função que etiqueta cada estado com um conjunto de proposições atômicas válidas naquele estado

{21}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-5445597cceefaca1ac89e710fe339325_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagrama de um Modelo de Kripke com três estados s0, s1 e s2.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-81a4cbf0b3c4cbc065efdf8f800dadde_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagrama de um Modelo de Kripke com três estados x=0, x=1 e x=2.
<!-- /IMAGE_DESCRIPTION -->
## Modelo

- Dada uma estrutura de Kripke  $M$ , um caminho de  $M$  iniciado no estado  $s_0$  é uma sequência infinita de estados  $\pi = s_0, s_1, s_2, \dots$  onde  $\forall i \geq 0. s_i \rightarrow s_{i+1}$  é uma transição de estado no modelo
- Dado um caminho  $\pi$ , o seu primeiro estado será denotado por  $\pi_0$  e assim por diante
- O sufixo do caminho  $\pi = s_0, s_1, s_2, \dots$  que começa na posição  $i$  será denotado por  $\pi^i = s_i, s_{i+1}, s_{i+2}, \dots$

{22}------------------------------------------------
## LÓGICA TEMPORAL ---

LTL e CTL

{23}------------------------------------------------
### Lógica Temporal

- A ideia da lógica temporal é que uma fórmula não é estaticamente verdadeira ou falsa em um modelo
- Um modelo é composto por diversos estados e a fórmula pode ser verdadeira em alguns e falsa em outros
- Fórmulas possuem uma avaliação dinâmica, pois seu valor lógico pode mudar a medida que o sistema evolui de um estado para outro
  - Exs:
    - Uma proposição é sempre válida
    - Uma proposição é eventualmente válida

{24}------------------------------------------------
### Lógica Temporal

- Os instantes temporais discretos são representados por estados
- Tempo Linear (*linear-time*)
  - O tempo é um conjunto de caminhos, onde um caminho é uma sequência de estados

Diagrama de Tempo Linear (linear-time): Uma sequência linear de estados  $s_0, s_1, s_2, s_3, s_4$  conectados por linhas horizontais.

Diagrama de Tempo Linear (linear-time)

- Tempo Ramificado (*branching-time*)
  - O tempo é representado em árvore cuja raiz é o momento presente

Diagrama de Tempo Ramificado (branching-time): Uma árvore de estados onde  $s_0$  é a raiz.  $s_0$  ramifica para  $s_1$  e  $s_2$ .  $s_1$  ramifica para  $s_3$  e  $s_4$ .  $s_2$  ramifica para  $s_5$ .

Diagrama de Tempo Ramificado (branching-time)

{25}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-552265bdbcf6d43d341fd018a9076269_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagrama de Tempo Linear (linear-time)
<!-- /IMAGE_DESCRIPTION -->
### Lógica Temporal

- Para verificar a validade de uma fórmula em uma lógica temporal é necessário saber quais as sequências de estados (caminhos ou traços) possíveis num determinado sistema

{26}------------------------------------------------
#### Tempo Linear

```
graph LR; In(( )) --> s0u0((s0  
u0)); s1u1((s1  
u1)) --> s0u0; s0u0 --> s1u1; s0u0 --> s1u2((s1  
u2)); s1u2 --> s1u2;
```

A state transition diagram with three states: (s1, u1), (s0, u0), and (s1, u2). An arrow points to (s0, u0) from above. Transitions: (s1, u1) to (s0, u0), (s0, u0) to (s1, u1), (s0, u0) to (s1, u2), and a self-loop on (s1, u2).

```
graph LR; s0u0((s0  
u0)) --> s1u2_1((s1  
u2)); s1u2_1 --> s1u2_2((s1  
u2)); s1u2_2 --> s1u2_3((s1  
u2)); s1u2_3 --> s1u2_4((s1  
u2)); s1u2_4 --> s1u2_5((s1  
u2)); s1u2_5 -.-> Dashed1[...];
```

A linear sequence of states: (s0, u0) -> (s1, u2) -> (s1, u2) -> (s1, u2) -> (s1, u2) -> (s1, u2) with a dashed arrow indicating continuation.

```
graph LR; s0u0((s0  
u0)) --> s1u1((s1  
u1)); s1u1 --> s0u0_2((s0  
u0)); s0u0_2 --> s1u2_1((s1  
u2)); s1u2_1 --> s1u2_2((s1  
u2)); s1u2_2 --> s1u2_3((s1  
u2)); s1u2_3 -.-> Dashed2[...];
```

A linear sequence of states: (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u2) -> (s1, u2) -> (s1, u2) with a dashed arrow indicating continuation.

```
graph LR; s0u0((s0  
u0)) --> s1u1_1((s1  
u1)); s1u1_1 --> s0u0_2((s0  
u0)); s0u0_2 --> s1u1_2((s1  
u1)); s1u1_2 --> s0u0_3((s0  
u0)); s0u0_3 --> s1u2_1((s1  
u2)); s1u2_1 -.-> Dashed3[...];
```

A linear sequence of states: (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u2) with a dashed arrow indicating continuation.

```
graph LR; s0u0((s0  
u0)) --> s1u1_1((s1  
u1)); s1u1_1 --> s0u0_2((s0  
u0)); s0u0_2 --> s1u1_2((s1  
u1)); s1u1_2 --> s0u0_3((s0  
u0)); s0u0_3 --> s1u1_3((s1  
u1)); s1u1_3 -.-> Dashed4[...];
```

A linear sequence of states: (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u1) with a dashed arrow indicating continuation.

...

{27}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-043e64d41a3368d138ace3816fd26469_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** A state transition diagram with three states: (s1, u1), (s0, u0), and (s1, u2).
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-a149b400127a3e3e50b3c98d27c5935c_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** A linear sequence of states: (s0, u0) -> (s1, u2) -> (s1, u2) -> (s1, u2) -> (s1, u2) -> (s1, u2) with a dashed arrow indicating continuation.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-2ae3eae1bd80a90f192f568ae246a9a6_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** A linear sequence of states: (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u2) -> (s1, u2) -> (s1, u2) with a dashed arrow indicating continuation.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-e90987faabad6a6665cd8ed1151dc474_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** A linear sequence of states: (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u2) with a dashed arrow indicating continuation.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-4cde160bcc69b7b6c81b648dd0e4252e_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** A linear sequence of states: (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u1) -> (s0, u0) -> (s1, u1) with a dashed arrow indicating continuation.
<!-- /IMAGE_DESCRIPTION -->
#### Tempo Ramificado

The diagram illustrates branching time (Tempo Ramificado) using a state transition graph. The graph consists of nodes and directed edges representing transitions between states.

**Top Graph (Initial State):**

- Node  $s_0 u_0$  is the initial state, indicated by an incoming arrow from above.
- Node  $s_0 u_0$  has two outgoing transitions to  $s_1 u_1$  and  $s_1 u_2$ .
- Node  $s_1 u_1$  has a self-loop transition back to  $s_0 u_0$ .
- Node  $s_1 u_2$  has a self-loop transition back to  $s_0 u_0$ .

**Bottom Graph (Branching Structure):**

- Node  $s_0 u_0$  branches into two paths.
- The upper path consists of a sequence of  $s_1 u_2$  nodes, with the last node having a dashed arrow indicating continuation.
- The lower path starts with  $s_1 u_1$ , which transitions to  $s_0 u_0$ .
- From this  $s_0 u_0$ , the path branches again into two sub-paths:
  - The upper sub-path consists of a sequence of  $s_1 u_2$  nodes, with the last node having a dashed arrow.
  - The lower sub-path starts with  $s_1 u_1$ , which transitions to another  $s_0 u_0$ .
- From this final  $s_0 u_0$ , the path branches into two more sub-paths:
  - The upper sub-path consists of a single  $s_1 u_2$  node with a dashed arrow.
  - The lower sub-path consists of a single  $s_1 u_1$  node with a dashed arrow.

Diagram illustrating branching time (Tempo Ramificado) with a state transition graph.

{28}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-e354b57563dae469c00b412b2abdf765_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagrama de Tempo Ramificado (branching-time)
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-d17aa1fcc3b86503ad1dd0717a6c34c2_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating branching time (Tempo Ramificado) with a state transition graph.
<!-- /IMAGE_DESCRIPTION -->
### Lógica Temporal

- LTL – *Linear Temporal Logic*
  - Lógica do tipo temporal linear
  - Ex.:  $F p$ 
    - No futuro (F) a fórmula (p) será verdadeira
- CTL – *Computation Tree Logic*
  - Lógica do tipo temporal ramificada
  - Ex.:  $AF p$ 
    - Para todos os caminhos possíveis (A), eventualmente no futuro (F) a fórmula (p) será verdadeira
- Observação:
  - As duas lógicas possuem poder de expressão diferentes
  - Porém possuem elementos em comum que são utilizados na prática

{29}------------------------------------------------
#### LTL - Sintaxe

- Toda proposição atômica é uma fórmula
- Combinação de operadores booleanos sobre fórmulas é uma fórmula
- Se  $\varphi$  e  $\psi$  são fórmulas, então
  - $X\varphi$  é uma fórmula (“next”)
  - $F\varphi$  é uma fórmula (“future”, “finally”, “eventually”)
  - $G\varphi$  é uma fórmula (“globally”, “always”)
  - $\varphi U\psi$  é uma fórmula (“until”)
- Observação:  $X$ ,  $F$  e  $G$  são por vezes representados por símbolos  $\circ$ ,  $\diamond$  e  $\square$

{30}------------------------------------------------
#### LTL - Semântica

- Fórmulas são interpretadas sobre caminhos/traços infinitos sobre um Modelo de Kripke
- O fato de uma fórmula LTL  $f$  se verificar num caminho  $\pi$  do modelo  $M$  será denotado  $M, \pi \models f$
- Uma fórmula LTL  $f$  é válida num estado  $s$  do modelo  $M$ , denotado  $M, s \models f$  se e somente se para todos os caminhos  $\pi$  do modelo  $M$ , onde  $\pi_0 = s$  se verifica  $M, \pi \models f$

{31}------------------------------------------------
#### LTL - Semântica

- $M, \pi \models \varphi$  é uma fórmula válida no primeiro estado  $\pi_0$
- $M, \pi \models X\varphi$  é uma fórmula (“next”) válida no próximo estado

$$M, \pi \models X f \Leftrightarrow M, \pi^1 \models f$$

The diagram shows a sequence of six circular states connected by arrows. The first state is empty. The second state contains the letter 'f'. The third, fourth, and fifth states are empty. The sixth state is empty, and a dashed arrow points from it to the right, indicating the sequence continues. This illustrates that if a formula 'f' is true in the next state (state 2), then the formula 'Xf' is true in the current state (state 1).

Diagram of a state transition sequence illustrating the semantics of the 'next' operator X.

{32}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-e05b36c0d46549e681ce6581422c66b2_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram of a state transition sequence illustrating the semantics of the 'next' operator X.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-b5335262987c819d7f71ce40f99cb71b_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the semantics of the LTL formula Gf.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-05eb72d372e4bf78e3d6a64949d77bcc_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the semantics of the LTL formula Ff.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-6e15fc9ea763541c5913d26f85072ae1_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the semantics of the LTL formula f U g.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-6cc85a2b62fd8a2a3faab29730f20e81_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the semantics of the CTL formula AF P.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-4e85fe330de2c4f5eea6de4b2a53c77f_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the semantics of the CTL formula AG P.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-b44f89b176c971c7dd264c07bfef2c2a_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the semantics of the CTL formula AX P.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-9dc9f41d7d76c1add4b190d348cb1533_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the semantics of the CTL formula EF P.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-762a17cd79880dbca172bcbbe9375223_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the semantics of the CTL formula EG P.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-2beb95006f1933bed737cfe1e6598db8_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the semantics of the CTL formula EX P.
<!-- /IMAGE_DESCRIPTION -->
#### LTL - Semântica

- $M, \pi \models G\varphi$  é uma fórmula (“globally”, “always”) sempre válida

$$M, \pi \models G f \quad \Leftrightarrow \quad \forall i \geq 0 \cdot M, \pi^i \models f$$

The diagram illustrates the semantics of the LTL formula  $Gf$ . It shows a sequence of states, each represented by a circle containing the letter 'f'. The states are connected by arrows, indicating a path through the model. The sequence starts with a solid arrow and ends with a dashed arrow, indicating an infinite path. This visualizes the requirement that the formula  $f$  must hold in every state along the entire path.

Diagram illustrating the semantics of the LTL formula Gf. It shows a sequence of states, each containing the letter 'f', connected by arrows. The sequence starts with a solid arrow and ends with a dashed arrow, indicating an infinite path.

{33}------------------------------------------------
#### LTL - Semântica

- $M, \pi \models F\varphi$  é uma fórmula (“future”, “finally”, “eventually”) eventualmente válida

$$M, \pi \models F f \Leftrightarrow \exists i \geq 0 \cdot M, \pi^i \models f$$

The diagram illustrates the semantics of the LTL formula  $Ff$ . It shows two horizontal sequences of states represented by circles. The top sequence has six circles; the fourth circle contains the letter 'f'. The bottom sequence has six circles; the first circle contains the letter 'f'. Solid arrows connect the first five circles in each sequence, and dashed arrows indicate the sequence continues. This visualizes that in any path, the formula 'f' is satisfied at some point in the future.

Diagram illustrating the semantics of the LTL formula Ff. It shows two horizontal sequences of states represented by circles. The top sequence has six circles; the fourth circle contains the letter 'f'. The bottom sequence has six circles; the first circle contains the letter 'f'. Solid arrows connect the first five circles in each sequence, and dashed arrows indicate the sequence continues. This visualizes that in any path, the formula 'f' is satisfied at some point in the future.

{34}------------------------------------------------
#### LTL - Semântica

- $M, \pi \models \varphi U \psi$  é uma fórmula (“until”) para qual  $\varphi$  é válida até que  $\psi$  o seja (essa é a versão “forte”)

$$M, \pi \models f U g \quad \Leftrightarrow \quad \exists i \geq 0 \cdot M, \pi^i \models g \text{ e } \forall 0 \leq j < i \cdot M, \pi^j \models f$$

The diagram illustrates the semantics of the LTL formula  $f U g$ . It shows two parallel paths of states. The top path starts with three states labeled 'f', followed by a state labeled 'g', and then two empty states. The bottom path starts with a state labeled 'g', followed by four empty states. Arrows indicate the sequence of states, and dashed arrows at the end of each path indicate that the sequence continues.

Diagram illustrating the semantics of the LTL formula f U g. It shows two parallel paths of states. The top path starts with three states labeled 'f', followed by a state labeled 'g', and then two empty states. The bottom path starts with a state labeled 'g', followed by four empty states. Arrows indicate the sequence of states, and dashed arrows at the end of each path indicate that the sequence continues.

- Cuidado: Não se afirma nada sobre o ponto “depois” de  $i$  em relação a  $f$

{35}------------------------------------------------
#### LTL - Exemplo

The diagram illustrates the intuitive semantics of five LTL temporal modalities using a sequence of five states (circles) connected by arrows, with the sequence continuing to infinity (indicated by  $\dots$ ).

- atomic prop.  $a$** : The first state is labeled  $a$ , and the subsequent four states are labeled "arbitrary".
- next step  $\bigcirc a$** : The first state is labeled "arbitrary", and the second state is labeled  $a$ . The subsequent three states are labeled "arbitrary".
- until  $a \cup b$** : The first three states are labeled  $a \wedge \neg b$ , the fourth state is labeled  $b$ , and the fifth state is labeled "arbitrary".
- eventually  $\diamond a$** : The first three states are labeled  $\neg a$ , the fourth state is labeled  $a$ , and the fifth state is labeled "arbitrary".
- always  $\Box a$** : All five states are labeled  $a$ .

Diagram illustrating the intuitive semantics of five LTL temporal modalities: atomic proposition, next step, until, eventually, and always.

Figure 5.1: Intuitive semantics of temporal modalities.

{36}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-339be989b91d5b1e73e5ecdc8401ca75_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Diagram illustrating the intuitive semantics of five LTL temporal modalities: atomic proposition, next step, until, eventually, and always.
<!-- /IMAGE_DESCRIPTION -->
#### LTL - Semântica

- Equivalências:

$$F\varphi = trueU\varphi$$

$$F\varphi = \neg G(\neg\varphi)$$

$$G\varphi = \neg F(\neg\varphi)$$

$$\neg G\varphi = F\neg\varphi$$

$$G(\varphi \wedge \psi) = (G\varphi) \wedge (G\psi)$$

$$F(\varphi \vee \psi) = (F\varphi) \vee (F\psi)$$

{37}------------------------------------------------
#### LTL - Semântica

- Algumas fórmulas representam conceitos que encontramos em diferentes especificações:
  - “eventually forever”  $FG\varphi$
  - “infinitely often”  $GF\varphi$

{38}------------------------------------------------
#### LTL

- Padrões de especificação:  
<http://patterns.projects.cs.ksu.edu/>

{39}------------------------------------------------
### CTL

- Muitas propriedades interessantes de sistemas concorrentes não podem ser especificadas usando o modelo de tempo linear
- CTL acrescenta à LTL os quantificadores sobre caminhos:
  - A (universal)
  - E (existencial)

<!-- DATALAB_CHUNK 3: pages 41-56 -->

{40}------------------------------------------------
## CTL - Sintaxe

- Toda proposição atômica é uma fórmula
- Combinação de operadores booleanos sobre fórmulas é uma fórmula
- Se  $\varphi$  e  $\psi$  são fórmulas, então
  - $EX\varphi$  é uma fórmula
  - $EF\varphi$  é uma fórmula “holds potentially”
  - $EG\varphi$  é uma fórmula “potentially always”
  - $E[\varphi U\psi]$  é uma fórmula
  - $AX\varphi$  é uma fórmula
  - $AF\varphi$  é uma fórmula “is inevitable”
  - $AG\varphi$  é uma fórmula “invariantly”
  - $A[\varphi U\psi]$  é uma fórmula

{41}------------------------------------------------
## CTL - Semântica

- Sendo  $f$  uma fórmula
  - $A f$  será válida em um estado  $s$  se  $f$  for válida em todos os caminhos que começam com  $s$
  - $E f$  será válida em um estado  $s$  se  $f$  for válida em pelo menos um caminho que começa com  $s$

$$\begin{array}{ll} M, s \models A h & \Leftrightarrow \forall \pi \in M \cdot \text{se } \pi_0 = s \text{ então } M, \pi \models h \\ M, s \models E h & \Leftrightarrow \exists \pi \in M \cdot \text{se } \pi_0 = s \text{ então } M, \pi \models h \end{array}$$

{42}------------------------------------------------
## CTL - Semântica

$AG\ f$

```
graph TD; A((f)) --> B((f)); A --> C((f)); A --> D((f)); B --> E((f)); C --> F((f)); C --> G((f)); D --> H((f)); D --> I((f)); E --> J((f)); F --> K((f)); G --> L((f)); H --> M((f)); I --> N((f)); J -.-> J1[ ]; K -.-> K1[ ]; L -.-> L1[ ]; M -.-> M1[ ]; N -.-> N1[ ];
```

A tree diagram illustrating the semantics of the CTL formula AG f. The tree has a root node 'f' which branches into three children, all labeled 'f'. The leftmost child has a single child 'f', which in turn has a single child 'f'. The middle child has two children, both labeled 'f'. The rightmost child has two children, both labeled 'f'. All leaf nodes have a dashed arrow pointing downwards, indicating that the tree continues infinitely. This structure represents a model where the formula f is true in every state of every path starting from the root.

{43}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-834fb96b114b8fdc001625e1ae28e8b1_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** A tree diagram illustrating the semantics of the CTL formula AG f.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-f5a5f52bc25d95a7f616290c99e88ae6_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** A tree diagram illustrating the semantics of the CTL formula EG f.
<!-- /IMAGE_DESCRIPTION -->
## CTL- Semântica

*EG f*

```
graph TD; A((f)) --> B(( )); A --> C((f)); A --> D(( )); B --> E(( )); E --> F(( )); F -.-> G[ ]; C --> H((f)); C --> I(( )); H --> J((f)); H --> K(( )); J -.-> L[ ]; K -.-> M[ ]; I --> N(( )); N -.-> O[ ]; D --> P(( )); P --> Q(( )); Q -.-> R[ ]; D --> S(( )); S --> T(( )); T -.-> U[ ];
```

A tree diagram illustrating the semantics of the CTL formula EG f. The root node is labeled 'f'. It has three children: a left child, a middle child labeled 'f', and a right child. The left child has a single child, which in turn has a single child, leading to a dashed arrow. The middle child 'f' has two children: a left child labeled 'f' and a right child. The 'f' child has two children, both leading to dashed arrows. The right child of the middle 'f' has a single child leading to a dashed arrow. The right child of the root has two children, each of which has a single child leading to a dashed arrow.

{44}------------------------------------------------
## CTL - Semântica

*AF f*

```
graph TD; Root(( )) --> L1((f)); Root --> L2(( )); Root --> L3(( )); L1 --> L1_1(( )); L1_1 --> L1_2(( )); L2 --> L2_1((f)); L2 --> L2_2(( )); L2_1 --> L2_1_1(( )); L2_1 --> L2_1_2(( )); L2_2 --> L2_2_1(( )); L3 --> L3_1((f)); L3 --> L3_2(( )); L3_1 --> L3_1_1(( )); L3_2 --> L3_2_1((f)); L3_2 --> L3_2_2((f)); L1_2 -.-> D1[ ]; L2_1_1 -.-> D2[ ]; L2_1_2 -.-> D3[ ]; L2_2_1 -.-> D4[ ]; L3_1_1 -.-> D5[ ]; L3_2_1 -.-> D6[ ]; L3_2_2 -.-> D7[ ];
```

A state transition system diagram illustrating the semantics of the CTL formula AF f. The root node branches into three children. The left child is labeled 'f' and has a single child, which in turn has a single child, ending in a dashed arrow. The middle child is unlabeled and has two children: the left one is labeled 'f' and has two children, each ending in a dashed arrow; the right one is unlabeled and has a single child ending in a dashed arrow. The right child of the root is unlabeled and has two children: the left one is labeled 'f' and has a single child ending in a dashed arrow; the right one is unlabeled and has two children, each labeled 'f' and each ending in a dashed arrow.

{45}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-60ffbad6c0fb7371a57fe8f267d2d141_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** A state transition system diagram illustrating the semantics of the CTL formula AF f.
<!-- /IMAGE_DESCRIPTION -->
## CTL - Semântica

Diagram illustrating the semantics of the CTL formula AF P. A triangular lattice of nodes is shown. A path starting from the root node and following a sequence of nodes that eventually reach a node where P is true is highlighted in blue. The rest of the lattice is light blue.

$AF P$

Diagram illustrating the semantics of the CTL formula AG P. A triangular lattice of nodes is shown. All nodes in the lattice are shaded blue, indicating that P is true in all states reachable from the root.

$AG P$

Diagram illustrating the semantics of the CTL formula AX P. A triangular lattice of nodes is shown. The immediate children of the root node are shaded blue, indicating that P is true in all next states.

$AX P$

![Diagram illustrating the semantics of the CTL formula A[P U q]. A triangular lattice of nodes is shown. A path starting from the root node and following a sequence of nodes that eventually reach a node where q is true is highlighted in red. The rest of the lattice is light blue.](a93de4c3f80bd4a972ab65510b09b68d_img.jpg)

Diagram illustrating the semantics of the CTL formula A[P U q]. A triangular lattice of nodes is shown. A path starting from the root node and following a sequence of nodes that eventually reach a node where q is true is highlighted in red. The rest of the lattice is light blue.

$A[P U q]$

Diagram illustrating the semantics of the CTL formula EF P. A triangular lattice of nodes is shown. A single node in the lattice is shaded blue, indicating that P is true in some state reachable from the root.

$EF P$

Diagram illustrating the semantics of the CTL formula EG P. A triangular lattice of nodes is shown. A path starting from the root node and following a sequence of nodes that eventually reach a node where P is true is highlighted in blue. The rest of the lattice is light blue.

$EG P$

Diagram illustrating the semantics of the CTL formula EX P. A triangular lattice of nodes is shown. The immediate children of the root node are shaded blue, indicating that P is true in some next state.

$EX P$

![Diagram illustrating the semantics of the CTL formula E[P U q]. A triangular lattice of nodes is shown. A path starting from the root node and following a sequence of nodes that eventually reach a node where q is true is highlighted in red. The rest of the lattice is light blue.](5391e1303dec02a02e7e42b5a4ffe58a_img.jpg)

Diagram illustrating the semantics of the CTL formula E[P U q]. A triangular lattice of nodes is shown. A path starting from the root node and following a sequence of nodes that eventually reach a node where q is true is highlighted in red. The rest of the lattice is light blue.

$E[P U q]$

{46}------------------------------------------------
## CTL - Semântica

- Equivalências:

$$EG\varphi = \neg AF(\neg\varphi)$$

$$AG\varphi = \neg EF(\neg\varphi)$$

$$EF\varphi = E[\text{true}U\varphi]$$

$$AF\varphi = A[\text{true}U\varphi]$$

{47}------------------------------------------------
## CTL

- Padrões de especificação:  
<http://patterns.projects.cs.ksu.edu/>

{48}------------------------------------------------
## CTL - Exemplo

- Alarme de cofre

```
graph TD; start(( )) --> enter_code((enter code)); enter_code -- "code entered" --> check_code((check code)); check_code -- "valid code/count = 0" --> unlock_door((unlock door)); unlock_door --> delay((delay)); delay -- "timeout" --> enter_code; check_code -- "invalid code/count ++" --> count_attempts((count attempts)); count_attempts -- "count == 3 / count = 0" --> sound_alarm((sound alarm)); sound_alarm --> enter_code; count_attempts --> enter_code;
```

The diagram illustrates the state transitions for a safe alarm system. It consists of the following states and transitions:

- enter code** (yellow circle): The initial state where a code is entered.
- check code** (grey circle): Reached after a code is entered.
- unlock door** (grey circle): Reached if the code is valid.
- delay** (grey circle): A delay state after unlocking the door.
- count attempts** (grey circle): Reached if the code is invalid, incrementing the attempt count.
- sound alarm** (grey circle): Reached if the number of attempts reaches 3, triggering the alarm.

Transitions are labeled with events and actions:

- code entered**: From **enter code** to **check code**.
- valid code/count = 0**: From **check code** to **unlock door**.
- invalid code/count ++**: From **check code** to **count attempts**.
- count == 3 / count = 0**: From **count attempts** to **sound alarm**.
- timeout**: From **delay** back to **enter code**.
- Alarm reset**: From **sound alarm** back to **enter code**.

State transition diagram for a safe alarm system.

{49}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-01e00200a536673d6cd0e6d8705047a0_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** State transition diagram for a safe alarm system.
<!-- /IMAGE_DESCRIPTION -->
## CTL - Exemplo

- $AG(\text{enter\_code} \ \& \ \text{valid\_code} \ \rightarrow \ AF(\text{unlock\_door}))$ 
  - Verdadeiro
- $AG(\text{enter\_code} \ \rightarrow \ AF(\text{unlock\_door}))$ 
  - Falso

The diagram illustrates a state transition system for a door unlocking process. It consists of two rows of states, each represented by a circle containing text. The top row contains four states: 'enter code', 'check code', 'count attempts', and 'sound alarm'. The bottom row contains three states: 'enter code', 'check code', and 'count attempts'. A solid arrow points from 'count attempts' in the top row to 'sound alarm'. A solid arrow points from 'sound alarm' to 'enter code' in the bottom row. A solid arrow points from 'enter code' in the bottom row to 'check code', and another solid arrow points from 'check code' to 'count attempts'. A bracket under the first three states of the top row is labeled '3 vezes'. A bracket under the first three states of the bottom row is also labeled '3 vezes'. A dashed arrow points to the right from the 'count attempts' state in the bottom row, indicating a continuation of the sequence.

State transition diagram for a door unlocking system showing a loop where the alarm sounds but the code is re-entered.

{50}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-8f7c0bf0c75a31fee6b0c7392ff57c39_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** State transition diagram for a door unlocking system showing a loop where the alarm sounds but the code is re-entered.
<!-- /IMAGE_DESCRIPTION -->
## LTL versus CTL

- A expressividade das duas é incomparável: cada uma das lógicas consegue exprimir propriedades que a outra não consegue

{51}------------------------------------------------
## LTL versus CTL

- Exemplo:
- Qualquer  $p$  é seguido, em algum instante, por um  $q$
- LTL
  - $G(p \rightarrow F q)$
- CTL
  - $AG(p \rightarrow AF q)$

{52}------------------------------------------------
## LTL versus CTL

- Exemplo:
- CTL
  - $AG\ EF\ p$  significa que onde quer que tenhamos que ir, sempre podemos chegar a um estado onde  $p$  é verdade (é uma propriedade útil para encontrar paradas em protocolos)
- LTL
  - Não é possível representar a propriedade

{53}------------------------------------------------
## LTL versus CTL

- Exemplo:
- LTL
  - $(G F p \rightarrow F q)$  significa que se existe uma infinidade de  $p$  ao longo do caminho, então existe alguma ocorrência de  $q$  (útil para indicar restrições de imparcialidade)
- CTL
  - Não é possível representar a propriedade

{54}------------------------------------------------
## LTL versus CTL

- Exemplo:
- LTL
  - $FX p$  é válido em ambos modelos
- CTL
  - $AF AX p$  distingue os dois modelos

```
graph TD; S(( )) --> L(( )); S --> R(( )); L --> P1((p)); R --> P1; L --> P2((p)); R --> P2; P1 --> F(( )); P2 --> F; F --> F;
```

Model 1: A state transition system with 6 states. The initial state (top) has two outgoing transitions to two intermediate states. These two intermediate states both have transitions to two states labeled 'p'. Both 'p' states have transitions to a final state (bottom), which has a self-loop.

```
graph TD; S(( )) --> L(( )); S --> R(( )); L --> P1((p)); P1 --> F(( )); R --> P2((p)); P2 --> F; F --> F;
```

Model 2: A state transition system with 6 states. The initial state (top) has two outgoing transitions to two intermediate states. The left intermediate state has a transition to a state labeled 'p', which then transitions to the final state (bottom). The right intermediate state has a transition to another state labeled 'p', which then transitions to the final state (bottom). The final state has a self-loop.

{55}------------------------------------------------

<!-- IMAGE_DESCRIPTION: datalab-a780a960b3f2de2493d5785bedae10ff_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Model 1: A state transition system with 6 states.
<!-- /IMAGE_DESCRIPTION -->

<!-- IMAGE_DESCRIPTION: datalab-9e8ebf03cae78f4f81b697548c2d7250_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** Model 2: A state transition system with 6 states.
<!-- /IMAGE_DESCRIPTION -->
## LTL versus CTL

- Exemplo:
- LTL
  - $FG\ p$  é válido no modelo
- CTL
  - $AF\ AG\ p$  não é válido no modelo
- Não é possível expressar a mesma semântica

```
graph LR; start(( )) --> s1((p)); s1 --> s1; s1 --> s2(( )); s2 --> s3((p)); s3 --> s3;
```

A state transition system diagram with three states: s1, s2, and s3. s1 and s3 are labeled with 'p' and have self-loops. s2 is an unlabeled state. Transitions: s1 to s2, s2 to s3, and self-loops on s1 and s3. An initial arrow points to s1.

<!-- IMAGE_DESCRIPTION: datalab-675af5bb2357ce5b510e613d04f66bdc_img.jpg -->
<!-- Tipo: generico -->
> **[Descrição de imagem]** A state transition system diagram with three states: s1, s2, and s3.
<!-- /IMAGE_DESCRIPTION -->
