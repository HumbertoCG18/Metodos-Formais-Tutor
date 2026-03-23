# MÉTODOS FORMAIS

Prof. Júlio Machado

## LÓGICA DE PREDICADOS

Sintaxe

Baseado nos materiais do Prof. Alfio Martini

#### **Sintaxe**

- Devido ao poder da lógica de predicados, sua linguagem é mais complexa do que a lógica proposicional
- Conceitos:
  - Assinaturas
  - Termos (denotam objetos)
  - Fórmulas (denotam valores lógicos)

#### **Assinatura**

- Assinaturas são declarações dos símbolos utilizados para a construção da linguagem específica
- Dividida em duas partes:
  - Assinatura para os termos
  - Assinatura para as fórmulas

### **Assinatura**

- Uma <u>assinatura de primeira ordem</u> para a lógica de predicados é uma tupla Σ=(OP, R) onde
  - OP = (C, F, ArF) tal que
    - C é um conjunto de símbolos de constantes
    - F é um conjunto de símbolos de funções
    - ArF:F→N é uma função de aridade que indica o número de argumentos de cada símbolo de função f∈F
  - R = (P, ArP) tal que
    - P é um conjunto de símbolos de predicados
    - ArP:P→N é uma função de aridade que indica o número de argumentos de cada símbolo de predicado p∈P
- Para cada assinatura assumimos um conjunto contável de identificadores para variáveis X={x, y, z, ...}

### Exemplo

- Assinatura para aritmética:
  - OP=(C,F,ArF)
    - C={0}
    - F={add, mult, succ}
    - ArF={add  $\mapsto$  2, mult  $\mapsto$  2, succ  $\mapsto$  1}
  - R=(P,ArP)
    - P={menor, meneq, maieq}
    - ArP={menor  $\mapsto$  2, meneq  $\mapsto$  2, maieq  $\mapsto$  2}

### Exemplo

- Assinatura para família:
  - OP=(C,F,ArF)
    - C={andre, beto, ana}
    - F={}
    - ArF={}
  - R=(P,ArP)
    - P={pai, mae, irmao}
    - ArP={pai  $\mapsto$  2, mae  $\mapsto$  2, irmao  $\mapsto$  2}

#### **Termos**

- Termos são objetos sintáticos que servem para representar elementos do domínio de uma determinada aplicação
- Um termo ou é uma constante, uma variável, ou então um símbolo de função aplicado a argumentos que são termos

#### **Termos**

- Seja OP=(C,F,ArF) uma assinatura para termos. O <u>conjunto de termos</u> sobre OP com variáveis X, denotado Τ<sub>Σ</sub>(X), é definido pelas seguintes regras de construção (definição por indução):
  - Toda variável  $v \in X$  é um termo
  - Toda constante  $c \in C$  é um termo
  - Se  $f \in F$  é uma função de aridade n e  $t_1, ..., t_n$  são termos, então  $f(t_1, ..., t_n)$  é um termo

$$\frac{1}{v:T_{\Sigma}(X)} v \in X_{\Sigma} \text{ [VAR]} \qquad \frac{1}{c:T_{\Sigma}(X)} c \in C \text{ [CON]}$$

$$\frac{t_1:T_{\Sigma}(X),\ldots,t_n:T_{\Sigma}(X)}{f(t_1,\ldots,t_n):T_{\Sigma}(X)} f \in F, Ar_F(f) = n \text{ [FUN]}$$

### Exemplo

- Assinatura para aritmética:
  - OP=(C,F,ArF)
    - C={0}
    - F={add, mult, succ}
    - ArF={add  $\mapsto$  2, mult  $\mapsto$  2, succ  $\mapsto$  1}
  - R=(P,ArP)
    - P={menor, meneq, maieq}
    - ArP={menor  $\mapsto$  2, meneq  $\mapsto$  2, maieq  $\mapsto$  2}
- Termos sobre a assinatura:
  - 0
  - succ(0)
  - succ(succ(0))
  - add(x,succ(0))

- Fórmulas são objetos sintáticos que denotam valores lógicos que determinados elementos do domínio possam ou não possuir
  - Fórmulas atômicas são construídas com símbolos de predicados aplicados a termos, com um predicado especial de igualdade (=), além dos símbolos para verdade (⊤) e falsidade (⊥)
  - Fórmulas compostas são construídas através das fórmulas atômicas, dos conectivos proposicionais e dos quantificadores universal (∀) e existencial (∃)

- Seja R=(P, ArP) uma assinatura para fórmulas. O <u>conjunto de fórmulas</u> sobre R com variáveis X, denotado por Form<sub>Σ</sub>(X) é definido pelas seguintes regras de construção (definição por indução):
- · Fórmulas atômicas:
  - ⊥ e ⊤ são fórmulas
  - Se  $t_1$ e  $t_2$  são termos, então  $t_1=t_2$  é uma fórmula
  - Se  $p \in P$  é um predicado de aridade n e  $t_1, ..., t_n$  são termos, então  $p(t_1, ..., t_n)$  é uma fórmula

#### Fórmulas atômicas:

$$\frac{1}{\bot : Form_{\Sigma}(X)} [BOT] \qquad \overline{\top : Form_{\Sigma}(X)} [TOP]$$

$$\frac{t_1 : T_{\Sigma}(X), \dots, t_n : T_{\Sigma}(X)}{p(t_1, \dots, t_n) : Form_{\Sigma}(X)} p \in P, Ar_P(p) = n [ATOM]$$

$$\frac{t_1: T_{\Sigma}(X) \ t_2: T_{\Sigma}(X)}{t_1 = t_2: Form_{\Sigma}(X)} \ [\text{ATOM,EQ}]$$

- Seja R=(P, ArP) uma assinatura para fórmulas. O <u>conjunto de fórmulas</u> sobre R com variáveis X, denotado por Form<sub>Σ</sub>(X) é definido pelas seguintes regras de construção (definição por indução):
- Fórmulas compostas:
  - Se A é uma fórmula, então  $(\neg A)$  é uma fórmula
  - Se A e B são fórmulas, então  $(A \land B)$ ,  $(A \lor B)$ ,  $(A \to B)$  e  $(A \leftrightarrow B)$  também são fórmulas
  - Se A é uma fórmula e  $v \in X$ , então  $(\forall v.A)$  e  $(\exists v.A)$  são fórmulas

Fórmulas compostas:

$$\frac{A : Form_{\Sigma}(X) \ B : Form_{\Sigma}(X)}{(A \ bop \ B) : Form_{\Sigma}(X)} \text{ [BOP]} \qquad \frac{A : Form_{\Sigma}(X)}{(\neg A) : Form_{\Sigma}(X)} \text{ [NEG]}$$

$$\frac{A : Form_{\Sigma}(X)}{(\forall v.A)} \ v \in X_{\Sigma} \text{ [UNI]} \qquad \frac{A : Form_{\Sigma}(X)}{(\exists v.A)} \ v \in X_{\Sigma} \text{ [EXI]}$$

 $bop \in \{\rightarrow, \leftrightarrow, \land, \lor\}$ 

### Exemplo

- Assinatura para aritmética:
  - OP=(C,F,ArF)
    - C={0}
    - F={add, mult, succ}
    - ArF={add  $\mapsto$  2, mult  $\mapsto$  2, succ  $\mapsto$  1}
  - R=(P,ArP)
    - P={menor, meneq, maieq}
    - ArP={menor  $\mapsto$  2, meneq  $\mapsto$  2, maieq  $\mapsto$  2}
- Fórmulas sobre a assinatura:
  - menor(0,0)
  - x=0
  - maieq(x,add(x,succ(x)))
  - $\forall x. (\exists y. maior(y, x))$

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
    - ArP= $\{L \mapsto 1\}$

Exemplo: Bob ama Cathy
