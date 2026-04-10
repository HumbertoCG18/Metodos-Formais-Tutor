# MÉTODOS FORMAIS

Prof. Júlio Machado

## LÓGICA DE PREDICADOS

Sintaxe

Baseado nos materiais do Prof. Alfio Martini

#### Sintaxe

- Devido ao poder da lógica de predicados, sua linguagem é mais complexa do que a lógica proposicional
- Conceitos:
  - Assinaturas
  - Termos (denotam objetos)
  - Fórmulas (denotam valores lógicos)

#### Assinatura

- Assinaturas são declarações dos símbolos utilizados para a construção da linguagem específica
- Dividida em duas partes:
  - Assinatura para os termos
  - Assinatura para as fórmulas

#### Assinatura

- Uma assinatura de primeira ordem para a lógica de predicados é uma tupla =(OP, R) onde
  - OP = (C, F, ArF) tal que
    - C é um conjunto de símbolos de constantes
    - F é um conjunto de símbolos de funções
    - ArF:F→N é uma função de aridade que indica o número de argumentos de cada símbolo de função fF
  - R = (P, ArP) tal que
    - P é um conjunto de símbolos de predicados
    - ArP:P→N é uma função de aridade que indica o número de argumentos de cada símbolo de predicado pP
- Para cada assinatura assumimos um conjunto contável de identificadores para variáveis X={x, y, z, ...}

### Exemplo

- Assinatura para aritmética:
  - OP=(C,F,ArF)
    - C={0}
    - F={add, mult, succ}
    - ArF={add 2, mult 2, succ 1}
  - R=(P,ArP)
    - P={menor, meneq, maieq}
    - ArP={menor 2, meneq 2, maieq 2}

### Exemplo

- Assinatura para família:
  - OP=(C,F,ArF)
    - C={andre, beto, ana}
    - F={}
    - ArF={}
  - R=(P,ArP)
    - P={pai, mae, irmao}
    - ArP={pai 2, mae 2, irmao 2}

#### Termos

- Termos são objetos sintáticos que servem para representar elementos do domínio de uma determinada aplicação
- Um termo ou é uma constante, uma variável, ou então um símbolo de função aplicado a argumentos que são termos

#### Termos

- Seja OP=(C,F,ArF) uma assinatura para termos. O conjunto de termos sobre OP com variáveis X, denotado T (X), é definido pelas seguintes regras de construção (definição por indução):
  - Toda variável $\in$ é um termo
  - Toda constante $\in$ é um termo
  - Se $\in$ é uma função de aridade e 1, $\ldots$ , são termos, então (1, $\ldots$ ,) é um termo

$$\frac{1}{v:T_{\Sigma}(X)} v \in X_{\Sigma} \text{ [VAR]} \qquad \frac{1}{c:T_{\Sigma}(X)} c \in C \text{ [CON]}$$

$$\frac{t_1:T_{\Sigma}(X),\ldots,t_n:T_{\Sigma}(X)}{f(t_1,\ldots,t_n):T_{\Sigma}(X)} f \in F, Ar_F(f) = n \text{ [FUN]}$$

#### Exemplo

- Assinatura para aritmética:
  - OP=(C,F,ArF)
    - C={0}
    - F={add, mult, succ}
    - ArF={add 2, mult 2, succ 1}
  - R=(P,ArP)
    - P={menor, meneq, maieq}
    - ArP={menor 2, meneq 2, maieq 2}
- Termos sobre a assinatura:
  - 0
  - succ(0)
  - succ(succ(0))
  - add(x,succ(0))

- Fórmulas são objetos sintáticos que denotam valores lógicos que determinados elementos do domínio possam ou não possuir
  - Fórmulas atômicas são construídas com símbolos de predicados aplicados a termos, com um predicado especial de igualdade (=), além dos símbolos para verdade ($\top$) e falsidade ($\bot$)
  - Fórmulas compostas são construídas através das fórmulas atômicas, dos conectivos proposicionais e dos quantificadores universal () e existencial ()

- Seja R=(P, ArP) uma assinatura para fórmulas. O conjunto de fórmulas sobre R com variáveis X, denotado por Form (X) é definido pelas seguintes regras de construção (definição por indução):
- Fórmulas atômicas:
  - $\bot$ e $\top$ são fórmulas
  - Se 1e <sup>2</sup> são termos, então <sup>1</sup> = <sup>2</sup> é uma fórmula
  - Se $\in$ é um predicado de aridade e 1, $\ldots$ , são termos, então (1, $\ldots$ ,) é uma fórmula

#### • Fórmulas atômicas:

$$\frac{1}{\bot : Form_{\Sigma}(X)} [BOT] \qquad \overline{\top : Form_{\Sigma}(X)} [TOP]$$

$$\frac{t_1 : T_{\Sigma}(X), \dots, t_n : T_{\Sigma}(X)}{p(t_1, \dots, t_n) : Form_{\Sigma}(X)} p \in P, Ar_P(p) = n [ATOM]$$

$$\frac{t_1: T_{\Sigma}(X) \ t_2: T_{\Sigma}(X)}{t_1 = t_2: Form_{\Sigma}(X)} \ [\text{ATOM,EQ}]$$

- Seja R=(P, ArP) uma assinatura para fórmulas. O conjunto de fórmulas sobre R com variáveis X, denotado por Form (X) é definido pelas seguintes regras de construção (definição por indução):
- Fórmulas compostas:
  - Se é uma fórmula, então ($\neg$) é uma fórmula
  - Se e são fórmulas, então ( $\land$ ), ( $\lor$ ), ( → ) e ( $\leftrightarrow$ ) também são fórmulas
  - Se é uma fórmula e v $\in$ , então ($\forall$. ) e ($\exists$. ) são fórmulas

• Fórmulas compostas:

$$\frac{A : Form_{\Sigma}(X) \ B : Form_{\Sigma}(X)}{(A \ bop \ B) : Form_{\Sigma}(X)} \text{ [BOP]} \qquad \frac{A : Form_{\Sigma}(X)}{(\neg A) : Form_{\Sigma}(X)} \text{ [NEG]}$$

$$\frac{A : Form_{\Sigma}(X)}{(\forall v.A)} \ v \in X_{\Sigma} \text{ [UNI]} \qquad \frac{A : Form_{\Sigma}(X)}{(\exists v.A)} \ v \in X_{\Sigma} \text{ [EXI]}$$

$\in$ {→, $\leftrightarrow$,$\land$,$\lor$}

#### Exemplo

- Assinatura para aritmética:
  - OP=(C,F,ArF)
    - C={0}
    - F={add, mult, succ}
    - ArF={add 2, mult 2, succ 1}
  - R=(P,ArP)
    - P={menor, meneq, maieq}
    - ArP={menor 2, meneq 2, maieq 2}
- Fórmulas sobre a assinatura:
  - menor(0,0)
  - x=0
  - maieq(x,add(x,succ(x)))
  - $\forall$. ($\exists$. (, ))

## LÓGICA DE PREDICADOS

- Usaremos os quantificadores e também variáveis, que representam indivíduos no mundo que estamos representando
- Os predicados e funções serão grafados com letras maiúsculas, enquanto que as variáveis deverão ser grafadas em letras minúsculas
- Usaremos as letras do fim do alfabeto para designar as variáveis, por exemplo: x, y, z, etc
- Usaremos as letras do início do alfabeto para designar indivíduos (constantes), por exemplo: a, b, c, etc

- Exemplo: Jones é um ladrão
  - Primeiro devemos criar um predicado para designar que algo é (ou possui a propriedade de ser) ladrão:
    - L(x) = "x é um ladrão"
  - Agora vamos usar uma letra do início do alfabeto para designar o indivíduo:
    - j = "Jones"
  - Formalizando:
    - L(j)

- Exemplo: Jones é um ladrão
  - Domínio = conjunto de todas as pessoas
  - OP=(C,F,ArF)
    - C={j}
    - F={}
    - ArF={}
  - R=(P,ArP)
    - P={L}
    - ArP={L 1}

• Exemplo: Bob ama Cathy
