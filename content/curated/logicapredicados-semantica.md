# MÉTODOS FORMAIS

Prof. Júlio Machado

# LÓGICA DE PREDICADOS

Semântica

Baseado nos materiais do Prof. Alfio Martini

# Motivação

- Definir a noção de interpretação para uma assinatura da Lógica de Predicados
- Aprender a calcular o valor semântico de termos e fórmulas
- Revisando...
  - Termos são elementos sintáticos que servem para representar elementos do domínio de uma determinada aplicação
    - Símbolos de variáveis, constantes e funções
  - Fórmulas são elementos sintáticos que denotam certas propriedades booleanas que determinados elementos do domínio possam ter
    - Símbolos de predicados, conectivos proposicionais, quantificador universal, quantificador existencial

# Interpretação

- Os elementos básicos de uma interpretação para uma assinatura da lógica de predicados são:
  - Um domínio, o qual é uma coleção não vazia de elementos, no qual as fórmulas serão avaliadas.
  - Um elemento do domínio, para cada constante da assinatura.
  - Um conjunto de funções sobre o domínio, uma para cada símbolo de função presente na assinatura.
  - Um conjunto de relações sobre o domínio, uma para cada símbolo de predicado na assinatura.

# Interpretação

- Seja =(OP, R) uma assinatura para a lógica de predicados
- Uma interpretação I para consiste de:
  - Um conjunto não-vazio D de valores chamado de domínio
  - Para cada símbolo constante c C, um valor c<sup>I</sup> D
  - Para cada símbolo de função f F, uma função f I :D<sup>n</sup>→D tal que ArF(f) = n
  - Para cada símbolo de predicado p P, uma relação p<sup>I</sup> D<sup>n</sup> , tal que ArP(p) = n

- Assinatura para aritmética:
  - OP=(C,F,ArF) • C={0, 1, 2, ...}
    - F={add, mult, ...}
    - ArF={add2, mult2, ...}
  - R=(P,ArP)
    - P={menor, meneq, maieq, ...}
    - ArP={menor2, meneq2, maieq2, ...}

- Interpretação para assinatura aritmética:
  - D = Naturais = {0,1,2,...}
  - Constantes
    - 0 0 <sup>I</sup>=0
    - 1 1 <sup>I</sup>=1
    - ...
  - Funções
    - add add<sup>I</sup> :NxN→N, tal que add(x,y)=x+y
    - ...
  - Predicados
    - menor menor<sup>I</sup>N<sup>2</sup>={(0,1),(0,2),(0,3),...}=x<y
    - ...

# Ambiente

- Uma interpretação permite atribuir o significado dos símbolos de constantes, funções e predicados
- Para definir o valor de variáveis se utiliza o conceito de ambiente
- Essencialmente, ambientes funcionam como uma tabela de consulta para os valores das variáveis
- IMPORTANTE: ambiente define o valor das variáveis chamadas livres, ou seja, aquelas que não estão no contexto de um quantificador; uma variável que está no contexto de um quantificador é chamada de variável ligada

# Ambiente

- Seja =(OP, R) uma assinatura para a lógica de predicados e X um conjunto de variáveis para a assinatura
- Um ambiente é uma função a: X →D que atribui valores do domínio às variáveis

# Ambiente

- Exemplo ambiente para assinatura aritmética:
  - X ={x,y}
  - a={x0,y1}

### Avaliação de Termos

- Seja  $\Sigma$  uma assinatura, I uma interpretação para a assinatura, e a um ambiente
- A função de avaliação de termos [.]<sub>a</sub>:T<sub>$\Sigma$</sub>(X)→D é definida indutivamente por:
  - Se o termo t é uma variável x, então [x]<sub>a</sub>=a(x)
  - Se o termo t é uma constante c, então [c]<sub>a</sub>=c<sup>l</sup>
  - Se o termo t é da forma f(t1,...,tn), então [f(t1,...,tn)]<sub>a</sub>=f<sup>l</sup>([t1]<sub>a</sub>,..., [tn]<sub>a</sub>)

- Avaliação de termo na assinatura aritmética:
  - [add(0,1)]<sub>a</sub>

- Seja uma assinatura, I uma interpretação para a assinatura, a um ambiente e A uma fórmula
- Defini-se a relação de satisfação $\models$ por indução estrutural sobre A
  - A expressão $\models$ diz que a fórmula A é V na interpretação I e ambiente a
  - A expressão ⊭ diz que a fórmula A é F na interpretação I e ambiente a

- Fórmulas atômicas:
  - $\models$ $\top$
  - ⊭ $\bot$
  - $\models$ (1, $\ldots$ ,) se e somente se ([t1]<sup>a</sup> ,...,[tn]<sup>a</sup> )p I
  - ⊭ (1, $\ldots$ ,) se e somente se ([t1]<sup>a</sup> ,...,[tn]<sup>a</sup> )p I
  - $\models$ <sup>1</sup> = <sup>2</sup> se e somente se [t1]<sup>a</sup> =[t2]<sup>a</sup>
  - ⊭ <sup>1</sup> = 2se e somente se [t1]a[t2]<sup>a</sup>

#### • Quantificadores:

- $\models$ $\forall$. se e somente se $\models$[$\mapsto$] para todo dD
- ⊭ $\forall$. se e somente se ⊭[$\mapsto$] para algum dD
- $\models$ $\exists$. se e somente se $\models$[$\mapsto$] para algum dD
- ⊭ $\exists$. se e somente se ⊭[$\mapsto$] para todo dD

- Conectivos proposicionais:
  - $\models$ $\neg$ se e somente se ⊭
  - ⊭ $\neg$ se e somente se $\models$
  - $\models$ <sup>1</sup> $\lor$ <sup>2</sup> se e somente se $\models$ <sup>1</sup> ou $\models$ <sup>2</sup>
  - ⊭ <sup>1</sup> $\lor$ <sup>2</sup> se e somente se ⊭ <sup>1</sup> e ⊭ <sup>2</sup>
  - $\models$ <sup>1</sup> $\land$ <sup>2</sup> se e somente se $\models$ <sup>1</sup> e $\models$ <sup>2</sup>
  - ⊭ <sup>1</sup> $\land$ <sup>2</sup> se e somente se ⊭ <sup>1</sup> ou ⊭ <sup>2</sup>

- Operadores proposicionais:
  - $\models$ <sup>1</sup> → <sup>2</sup> se e somente se ⊭ <sup>1</sup> ou $\models$ <sup>2</sup>
  - ⊭ <sup>1</sup> → <sup>2</sup> se e somente se $\models$ <sup>1</sup> e ⊭ <sup>2</sup>
  - $\models$ <sup>1</sup> $\leftrightarrow$ <sup>2</sup> se e somente se ( $\models$ <sup>1</sup> e $\models$ 2) ou ( ⊭ <sup>1</sup> e ⊭ 2)
  - ⊭ <sup>1</sup> $\leftrightarrow$ <sup>2</sup> se e somente se ( $\models$ <sup>1</sup> e ⊭ 2) ou ( ⊭ <sup>1</sup> e $\models$ 2)

- Avaliação de fórmula na assinatura aritmética:
  - [menor(1,add(1,1))]<sup>a</sup>
  - [x.menor(add(x,1),x)]<sup>a</sup>
