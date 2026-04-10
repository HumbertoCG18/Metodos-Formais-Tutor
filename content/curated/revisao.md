# MÉTODOS FORMAIS

Prof. Júlio Machado

## CONJUNTOS E FUNÇÕES

Revisão

- Um conjunto é uma coleção de elementos
- A={0,1}
- B=={} é o conjunto vazio

- Os elementos também são chamados de membros desse conjunto
- A={0,1}
- 0A, 0 é um elemento do conjunto A, 0 pertence a A
- 2A, 2 não é um elemento do conjunto A, 2 não pertence a A

- Conjuntos podem também ser descritos através de uma especificação das propriedades dos seus elementos
- A={xN/x<5}, onde N é o conjunto dos números naturais
- B={xN/x mod 2 = 0}

- Um conjunto A é subconjunto de um conjunto B, AB, se cada elemento de A também é elemento de B
- A={0,1,2}
- N={0,1,2,3,...}
- AN
- AA
- A, o vazio está contido em qualquer conjunto

- União AB = {x / xA ou xB}
  - A={0,1,2}
  - B={0,2,4,6}
  - AB={0,1,2,4,6}
- Intersecção AB = {x / xA e xB}
  - A={0,1,2}
  - B={0,2,4,6}
  - AB={0,2}
- Diferença A-B ou A/B = {x / xA e xB}
  - A={0,1,2}
  - B={0,2,4,6}
  - A-B={1}

- Conjunto das partes, ou conjunto potência, de um conjunto A, escrito (A), é o conjunto de todos os subconjuntos do conjunto A
- A={0,1}
- (A)={,{0},{1},{0,1}}

- O produto cartesiano entre dois conjuntos A e B, escrito AxB, é o conjunto de todos os pares ordenados (a,b) tal que aA e bB
- A={0,1}
- B={x,y}
- AxB={(0,x),(0,y),(1,x),(1,y)}

- O produto cartesiano generalizado A<sup>n</sup> , com n$\geq$0 é definido como
  - A<sup>0</sup> = {()}
  - An+1 = AxA<sup>n</sup>
- A={0,1}
- A<sup>3</sup>=AxA<sup>2</sup>=AxAxA<sup>1</sup>=AxAxAxA<sup>0</sup>

#### Relações

- Uma relação binária R entre dois conjuntos A e B, escrita R:A$\leftrightarrow$B, é um subconjunto do produto cartesiano AxB
  - Conjunto A é chamado de domínio
  - Conjunto B é chamado de codomínio
- A={0,1,2}
- B={x,y}
- R1={(0,x),(1,x),(2,y)}
- R2={(0,x),(0,y),(1,y),(2,y)}
- R3={(1,x)}

#### Relações

- Seja uma relação binária R:A$\leftrightarrow$B
  - Domínio de definição de R é {xA | yB e (x,y)R}
  - Imagem de R é {yB | xA e (x,y)R}
- A={0,1,2}
- B={x,y}
- R3={(1,x)}
  - dd(R3)={1}
  - img(R3)={x}

#### Relações de Equivalência

- Seja uma relação binária R:A$\leftrightarrow$A, diz-se que ela é uma relação de equivalência caso seja:
  - Reflexiva: xA.(x,x)R
  - Simétrica: xA, yA. (x,y)R (y,x)R
  - Transitiva: xA, yA, zA,. (x,y)R (y,z)R (x,z)R

#### Relações de Ordem Parcial

- Seja uma relação binária R:A$\leftrightarrow$A, diz-se que ela é uma relação de ordem parcial caso seja:
  - Reflexiva: xA.(x,x)R
  - Antissimétrica: xA, yA. (x,y)R (y,x)R x=y
  - Transitiva: xA, yA, zA,. (x,y)R (y,z)R (x,z)R

#### Relações de Ordem Total

- Seja uma relação de ordem parcial R:A$\leftrightarrow$A, diz-se que ela é uma relação de ordem total caso :
  - Qualquer elemento possa ser comparado, ou seja, xA, yA. (x,y)R (y,x)R

#### Funções Parciais

- Uma função parcial f entre dois conjuntos A e B, escrito f:A⇀B, é uma relação entre os conjuntos A e B tal que existe somente um par ordenado com a primeira componente em A
  - Ou seja, se (x,y)f e (x,z)f então y=z
- A={0,1,2}
- B={x,y}
- R1={(0,x),(1,x),(2,y)} é função
  - Escreve-se R1(0)=x ou {0⟼x}R1
- R2={(0,x),(0,y),(1,y),(2,y)} não é função
- R3={(1,x)} é função

#### Funções Totais

• Uma função total F:A→B é uma função parcial que é definida para todo elemento do conjunto de partida, ou seja, para todo elemento xA existem um elemento yB tal que F(x)=y

#### LINGUAGENS FORMAIS

Revisão

#### Alfabeto e palavra

- Um *alfabeto* é um conjunto finito, não vazio, de elementos (símbolos)
- Toda linguagem tem um alfabeto associado
- Uma *palavra* (cadeia de caracteres ou *string*) sobre um alfabeto é uma sequência finita de símbolos justapostos
- O **tamanho de uma palavra** *w*, representado por |*w*|, é o número de símbolos da palavra
- A **palavra vazia** (), é uma palavra sem símbolo, ou seja, || = 0

#### Linguagem sobre um alfabeto

- Uma linguagem sobre um alfabeto é um conjunto de palavras sobre
- Denotanto o conjunto de todas as palavras sobre como \*, dizemos que uma linguagem sobre é qualquer subconjunto de \*

#### Linguagens artificiais

#### Uma linguagem artificial pode ser vista de duas formas:

- como uma *entidade livre*, ou seja, sem qualquer significado associado (SINTAXE);
- como uma *entidade* juntamente *com uma interpretação do seu significado* (SEMÂNTICA).
- Métodos Formais lida com ambos aspectos das linguagens

#### Hierarquia de Chomsky

![](content/images/revisao-_page_21_Picture_1.png)
