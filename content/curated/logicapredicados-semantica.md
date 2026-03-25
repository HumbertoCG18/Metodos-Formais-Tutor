# MÉTODOS FORMAIS

Prof. Júlio Machado

## LÓGICA DE PREDICADOS

Semântica

Baseado nos materiais do Prof. Alfio Martini

#### Motivação

- Definir a noção de interpretação para uma assinatura da Lógica de Predicados
- Aprender a calcular o valor semântico de termos e fórmulas
- Revisando...
  - Termos são elementos sintáticos que servem para representar elementos do domínio de uma determinada aplicação
    - Símbolos de variáveis, constantes e funções
  - Fórmulas são elementos sintáticos que denotam certas propriedades booleanas que determinados elementos do domínio possam ter
    - Símbolos de predicados, conectivos proposicionais, quantificador universal, quantificador existencial

### Interpretação

- Os elementos básicos de uma interpretação para uma assinatura da lógica de predicados são:
  - Um domínio, o qual é uma coleção não vazia de elementos, no qual as fórmulas serão avaliadas.
  - Um elemento do domínio, para cada constante da assinatura.
  - Um conjunto de funções sobre o domínio, uma para cada símbolo de função presente na assinatura.
  - Um conjunto de relações sobre o domínio, uma para cada símbolo de predicado na assinatura.

### Interpretação

- Seja $\Sigma$=(OP, R) uma assinatura para a lógica de predicados
- Uma interpretação I para  $\Sigma$  consiste de:
  - Um conjunto não-vazio D de valores chamado de domínio
  - Para cada símbolo constante c $\in$ C, um valor c<sup>l</sup> $\in$ D
  - Para cada símbolo de função f $\in$ F, uma função f¹:D<sup>n</sup>→D tal que ArF(f) = n
  - Para cada símbolo de predicado  $p \in P$ , uma relação  $p^l \subseteq D^n$ , tal que ArP(p) = n

- Assinatura para aritmética:
  - OP=(C,F,ArF)C={0, 1, 2, ...}
    - F={add, mult, ...}
    - ArF={add→2, mult→2, ...}
  - R=(P,ArP)
    - P={menor, meneq, maieq, ...}
    - ArP={menor→2, meneq→2, maieq→2, ...}

- Interpretação para assinatura aritmética:
  - D = Naturais =  $\{0,1,2,...\}$
  - Constantes
    - $0 \mapsto 0 = 0$
    - $1 \mapsto 1^{l}=1$
    - •
  - Funções
    - add  $\mapsto$  add<sup>1</sup>:NxN $\rightarrow$ N, tal que add(x,y)=x+y
    - ...
  - Predicados
    - menor  $\mapsto$  menor  $|\subseteq N^2 = \{(0,1),(0,2),(0,3),...\} = x < y$
    - ...

#### **Ambiente**

- Uma interpretação permite atribuir o significado dos símbolos de constantes, funções e predicados
- Para definir o valor de variáveis se utiliza o conceito de ambiente
- Essencialmente, ambientes funcionam como uma tabela de consulta para os valores das variáveis
- IMPORTANTE: ambiente define o valor das variáveis chamadas livres, ou seja, aquelas que não estão no contexto de um quantificador; uma variável que está no contexto de um quantificador é chamada de variável ligada

#### **Ambiente**

- Seja  $\Sigma$ =(OP, R) uma assinatura para a lógica de predicados e  $X_{\Sigma}$  um conjunto de variáveis para a assinatura
- Um <u>ambiente</u> é uma função a: X<sub>$\Sigma$</sub> →D que atribui valores do domínio às variáveis

#### **Ambiente**

- Exemplo ambiente para assinatura aritmética:
  - $X_{\Sigma} = \{x,y\}$
  - $a=\{x\mapsto 0, y\mapsto 1\}$

#### Avaliação de Termos

- Seja  $\Sigma$  uma assinatura, I uma interpretação para a assinatura, e a um ambiente
- A função de avaliação de termos [.]<sub>a</sub>:T<sub>$\Sigma$</sub>(X)→D é definida indutivamente por:
  - Se o termo t é uma variável x, então [x]<sub>a</sub>=a(x)
  - Se o termo t é uma constante c, então [c]<sub>a</sub>=c<sup>l</sup>
  - Se o termo t é da forma f(t1,...,tn), então [f(t1,...,tn)]<sub>a</sub>=f<sup>l</sup>([t1]<sub>a</sub>,..., [tn]<sub>a</sub>)

- Avaliação de termo na assinatura aritmética:
  - [add(0,1)]<sub>a</sub>

- Seja  $\Sigma$  uma assinatura, I uma interpretação para a assinatura, a um ambiente e A uma fórmula
- Defini-se a relação de satisfação  $I \vDash_a A$  por indução estrutural sobre A
  - A expressão I $\models$<sub>a</sub> A diz que a fórmula A é V na interpretação I e ambiente a
  - A expressão I ⊭<sub>a</sub> A diz que a fórmula A é F na interpretação I e ambiente a

- Fórmulas atômicas:
  - $I \vDash_a T$
  - $I \nvDash_a \bot$
  - $I \vDash_a p(t_1, ..., t_n)$  se e somente se ([t1]<sub>a</sub>,...,[tn]<sub>a</sub>) $\in p^1$
  - $I \not\models_a p(t_1, ..., t_n)$  se e somente se ([t1]<sub>a</sub>,...,[tn]<sub>a</sub>) $\not\in$ p<sup>l</sup>
  - $I \vDash_a t_1 = t_2$  se e somente se  $[t1]_a = [t2]_a$
  - $I \not\models_a t_1 = t_2$ se e somente se  $[t1]_a \neq [t2]_a$

#### Quantificadores:

- $I \vDash_a \forall x. B$  se e somente se  $I \vDash_{a[x \mapsto d]} B$  para todo  $d \in D$
- $I \not\models \forall x.B$  se e somente se  $I \not\models_{a[x \mapsto d]} B$  para algum  $d \in D$
- $I \vDash_a \exists x. B$  se e somente se  $I \vDash_{a[x \mapsto d]} B$  para algum  $d \in D$
- $I \not\models_a \exists x.B$  se e somente se  $I \not\models_{a[x\mapsto d]} B$  para todo  $d \in D$

- Conectivos proposicionais:
  - $I \vDash_a \neg B$  se e somente se  $I \nvDash_a B$
  - $I \nvDash_a \neg B$  se e somente se  $I \vDash_a B$
  - $I \vDash_a B_1 \lor B_2$  se e somente se  $I \vDash_a B_1$  ou  $I \vDash_a B_2$
  - $I \not\models_a B_1 \lor B_2$  se e somente se  $I \not\models_a B_1$  e  $I \not\models_a B_2$
  - $I \vDash_a B_1 \land B_2$  se e somente se  $I \vDash_a B_1$  e  $I \vDash_a B_2$
  - $I \not\models_a B_1 \land B_2$  se e somente se  $I \not\models_a B_1$  ou  $I \not\models_a B_2$

- Operadores proposicionais:
  - $I \vDash_a B_1 \to B_2$  se e somente se  $I \nvDash_a B_1$  ou  $I \vDash_a B_2$
  - $I \nvDash_a B_1 \to B_2$  se e somente se  $I \vDash_a B_1$  e  $I \nvDash_a B_2$
  - $I \vDash_a B_1 \leftrightarrow B_2$  se e somente se  $(I \vDash_a B_1 \in I \vDash_a B_2)$  ou  $(I \not\vDash_a B_1 \in I \not\vDash_a B_2)$
  - $I \nvDash_a B_1 \leftrightarrow B_2$  se e somente se  $(I \vDash_a B_1 \in I \nvDash_a B_2)$  ou  $(I \nvDash_a B_1 \in I \bowtie_a B_2)$

- Avaliação de fórmula na assinatura aritmética:
  - [menor(1,add(1,1))]<sub>a</sub>
  - $[\exists x.menor(add(x,1),x)]_a$
