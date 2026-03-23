## MÉTODOS FORMAIS

Prof. Júlio Machado

# CONJUNTOS E FUNÇÕES

Revisão

- Um conjunto é uma coleção de elementos
- A={0,1}
- B=∅={} é o conjunto vazio

- Os elementos também são chamados de membros desse conjunto
- A={0,1}
- 0∈A, 0 é um elemento do conjunto A, 0 pertence a A
- 2∉A, 2 não é um elemento do conjunto A, 2 não pertence a A

- Conjuntos podem também ser descritos através de uma especificação das propriedades dos seus elementos
- A={x∈N/x<5}, onde N é o conjunto dos números naturais</li>
- $B=\{x \in N/x \mod 2 = 0\}$

- Um conjunto A é subconjunto de um conjunto B, A⊆B, se cada elemento de A também é elemento de B
- A={0,1,2}
- N={0,1,2,3,...}
- A⊆N
- A<u></u>
- ∅⊆A, o vazio está contido em qualquer conjunto

- União  $A \cup B = \{x \mid x \in A \text{ ou } x \in B\}$ 
  - A={0,1,2}
  - B={0,2,4,6}
  - A∪B={0,1,2,4,6}
- Intersecção A∩B = {x / x∈A e x∈B}
  - A={0,1,2}
  - B={0,2,4,6}
  - A∩B={0,2}
- Diferença A-B ou A/B = {x / x∈A e x∉B}
  - $A=\{0,1,2\}$
  - B={0,2,4,6}
  - A-B={1}

- Conjunto das partes, ou conjunto potência, de um conjunto A, escrito P(A), é o conjunto de todos os subconjuntos do conjunto A
- A={0,1}
- $P(A) = {\emptyset, {0}, {1}, {0,1}}$

- O produto cartesiano entre dois conjuntos A e B, escrito AxB, é o conjunto de todos os pares ordenados (a,b) tal que a∈A e b∈B
- $A = \{0,1\}$
- B={x,y}
- $AxB=\{(0,x),(0,y),(1,x),(1,y)\}$

- O produto cartesiano generalizado A<sup>n</sup>, com n≥0 é definido como
  - $A^0 = \{()\}$
  - $A^{n+1} = AxA^n$
- $A = \{0,1\}$
- $A^3 = AxA^2 = AxAxA^1 = AxAxAxA^0$

#### Relações

- Uma relação binária R entre dois conjuntos A e B, escrita R:A↔B, é um subconjunto do produto cartesiano AxB
  - Conjunto A é chamado de domínio
  - Conjunto B é chamado de codomínio
- A={0,1,2}
- B={x,y}
- R1= $\{(0,x),(1,x),(2,y)\}$
- $R2=\{(0,x),(0,y),(1,y),(2,y)\}$
- R3={(1,x)}

#### Relações

- Seja uma relação binária R:A↔B
  - Domínio de definição de R é  $\{x \in A \mid \exists y \in B \ e \ (x,y) \in R\}$
  - Imagem de R é  $\{y \in B \mid \exists x \in A \text{ e } (x,y) \in R\}$
- A={0,1,2}
- B={x,y}
- $R3=\{(1,x)\}$ 
  - $dd(R3)=\{1\}$
  - $img(R3)=\{x\}$

#### Relações de Equivalência

- Seja uma relação binária R:A↔A, diz-se que ela é uma relação de equivalência caso seja:
  - Reflexiva: ∀x∈A.(x,x)∈R
  - Simétrica:  $\forall x \in A, y \in A. (x,y) \in R \Rightarrow (y,x) \in R$
  - Transitiva:  $\forall x \in A, y \in A, z \in A, (x,y) \in R \land (y,z) \in R \Rightarrow (x,z) \in R$

#### Relações de Ordem Parcial

- Seja uma relação binária R:A↔A, diz-se que ela é uma relação de ordem parcial caso seja:
  - Reflexiva: ∀x∈A.(x,x)∈R
  - Antissimétrica:  $\forall x \in A, y \in A. (x,y) \in R \land (y,x) \in R \Rightarrow x=y$
  - Transitiva:  $\forall x \in A, y \in A, z \in A, (x,y) \in R \land (y,z) \in R \Rightarrow (x,z) \in R$

#### Relações de Ordem Total

- Seja uma relação de ordem parcial R:A↔A, diz-se que ela é uma relação de ordem total caso :
  - Qualquer elemento possa ser comparado, ou seja, ∀x∈A, y∈A.
    (x,y)∈R ∨ (y,x)∈R

#### Funções Parciais

- Uma função parcial f entre dois conjuntos A e B, escrito f:A→B, é uma relação entre os conjuntos A e B tal que existe somente um par ordenado com a primeira componente em A
  - Ou seja, se (x,y)∈f e (x,z)∈f então y=z
- A={0,1,2}
- B={x,y}
- R1={(0,x),(1,x),(2,y)} é função
  - Escreve-se R1(0)=x ou  $\{0 \mapsto x\} \in R1$
- R2={(0,x),(0,y),(1,y),(2,y)} não é função
- R3={(1,x)} é função

#### Funções Totais

 Uma função total F:A→B é uma função parcial que é definida para todo elemento do conjunto de partida, ou seja, para todo elemento x∈A existem um elemento y∈B tal que F(x)=y

### LINGUAGENS FORMAIS

Revisão

#### Alfabeto e palavra

- Um alfabeto é um conjunto finito, não vazio, de elementos (símbolos)
- Toda linguagem tem um alfabeto associado
- Uma *palavra* (cadeia de caracteres ou *string*) sobre um alfabeto  $\Sigma$  é uma sequência finita de símbolos justapostos
- O tamanho de uma palavra w, representado por |w|, é o número de símbolos da palavra
- A palavra vazia (ε), é uma palavra sem símbolo, ou seja,
  |ε| = 0

#### Linguagem sobre um alfabeto

- Uma linguagem sobre um alfabeto  $\Sigma$  é um conjunto de palavras sobre  $\Sigma$
- Denotanto o conjunto de todas as palavras sobre  $\Sigma$  como  $\Sigma^*$ , dizemos que uma linguagem sobre  $\Sigma$  é qualquer subconjunto de  $\Sigma^*$

#### Linguagens artificiais

## Uma linguagem artificial pode ser vista de duas formas:

- como uma entidade livre, ou seja, sem qualquer significado associado (SINTAXE);
- como uma entidade juntamente com uma interpretação do seu significado (SEMÂNTICA).
- Métodos Formais lida com ambos aspectos das linguagens

#### Hierarquia de Chomsky

![](content/images/images-revisao-_page_21_Picture_1.jpeg)
