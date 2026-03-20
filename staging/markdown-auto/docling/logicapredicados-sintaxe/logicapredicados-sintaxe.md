## MÉTODOS FORMAIS

Prof. Júlio Machado

## LÓGICA DE PREDICADOS

## Sintaxe

Baseado nos materiais do Prof. Alfio Martini

## Sintaxe

- Devido ao poder da lógica de predicados, sua linguagem é mais complexa do que a lógica proposicional
- Conceitos:
- Assinaturas
- Termos (denotam objetos)
- Fórmulas (denotam valores lógicos)

## Assinatura

- Assinaturas são declarações dos símbolos utilizados para a construção da linguagem específica
- Dividida em duas partes:
- Assinatura para os termos
- Assinatura para as fórmulas

## Assinatura

- Uma assinatura de primeira ordem para a lógica de predicados é uma tupla  =(OP, R) onde
- OP = (C, F, ArF) tal que
- C é um conjunto de símbolos de constantes
- F é um conjunto de símbolos de funções
- ArF:F → N é uma função de aridade que indica o número de argumentos de cada símbolo de função f  F
- R = (P, ArP) tal que
- P é um conjunto de símbolos de predicados
- ArP:P → N é uma função de aridade que indica o número de argumentos de cada símbolo de predicado p  P
- Para cada assinatura assumimos um conjunto contável de identificadores para variáveis X={x, y, z, ...}

## Exemplo

## · Assinatura para aritmética:

```
· OP=(C,F,ArF) · C={0} · F={add, mult, succ} · ArF={add  2, mult  2, succ  1} · R=(P,ArP) · P={menor, meneq, maieq} · ArP={menor  2, meneq  2, maieq 
```

- 2}

## Exemplo

## · Assinatura para família:

```
· OP=(C,F,ArF) · C={andre, beto, ana} · F={} · ArF={} · R=(P,ArP) · P={pai, mae, irmao} · ArP={pai  2, mae  2, irmao 
```

- 2}

## Termos

- Termos são objetos sintáticos que servem para representar elementos do domínio de uma determinada aplicação
- Um termo ou é uma constante, uma variável, ou então um símbolo de função aplicado a argumentos que são termos

## Termos

- Seja OP=(C,F,ArF) uma assinatura para termos. O conjunto de termos sobre OP com variáveis X, denotado T  (X), é definido pelas seguintes regras de construção (definição por indução):
- Toda variável 𝑣 ∈ 𝑋 é um termo
- Toda constante 𝑐 ∈ 𝐶 é um termo
- Se 𝑓 ∈ 𝐹 é uma função de aridade 𝑛 e 𝑡 1 , … , 𝑡𝑛 são termos, então 𝑓(𝑡1 , … , 𝑡𝑛) é um termo

$$\frac { \overline { v \colon T _ { \Sigma } ( X ) } ^ { v \in X _ { \Sigma } \ [ \text {VAR} ] } } { v \colon T _ { \Sigma } ( X ) } & & \overline { c \colon T _ { \Sigma } ( X ) } ^ { \ } c \in C \ [ \text {CON} ] \\ \frac { t _ { 1 } \colon T _ { \Sigma } ( X ) , \dots , t _ { n } \colon T _ { \Sigma } ( X ) } { f ( t _ { 1 } , \dots , t _ { n } ) \colon T _ { \Sigma } ( X ) } & f \in F , A r _ { F } ( f ) = n \ [ \text {FUN} ]$$

## Exemplo

## · Assinatura para aritmética:

```
· OP=(C,F,ArF) · C={0} · F={add, mult, succ} · ArF={add  2, mult  2, succ  1} · R=(P,ArP) · P={menor, meneq, maieq} · ArP={menor  2, meneq  2, maieq  2}
```

- Termos sobre a assinatura:
- 0
- succ(0)
- succ(succ(0))
- add(x,succ(0))

## Fórmulas

- Fórmulas são objetos sintáticos que denotam valores lógicos que determinados elementos do domínio possam ou não possuir
- Fórmulas atômicas são construídas com símbolos de predicados aplicados a termos, com um predicado especial de igualdade (=), além dos símbolos para verdade ( ⊤ ) e falsidade ( ⊥ )
- Fórmulas compostas são construídas através das fórmulas atômicas, dos conectivos proposicionais e dos quantificadores universal (  ) e existencial (  )

## Fórmulas

- Seja R=(P, ArP) uma assinatura para fórmulas. O conjunto de fórmulas sobre R com variáveis X, denotado por Form  (X) é definido pelas seguintes regras de construção (definição por indução):
- Fórmulas atômicas:
- ⊥ e ⊤ são fórmulas
- Se 𝑡 1 e 𝑡 2 são termos, então 𝑡 1 = 𝑡2 é uma fórmula
- Se 𝑝 ∈ 𝑃 é um predicado de aridade 𝑛 e 𝑡 1 , … , 𝑡𝑛 são termos, então 𝑝(𝑡1 , … , 𝑡𝑛) é uma fórmula

## Fórmulas

## · Fórmulas atômicas:

$$[ B O T ]$$

$$\overline { \perp \colon F o r m _ { \Sigma } ( X ) } \ \left [ B O T \right ] & & \overline { \top \colon F o r m _ { \Sigma } ( X ) } \ \left [ T O P \right ] \\ \frac { t _ { 1 } \colon T _ { \Sigma } ( X ) , \dots , t _ { n } \colon T _ { \Sigma } ( X ) } { p ( t _ { 1 } , \dots , t _ { n } ) \colon F o r m _ { \Sigma } ( X ) } \ p \in P , A r _ { P } ( p ) = n \ \left [ A T O M \right ]$$

$$[ T O P ]$$

$$\frac { ( \lambda ) } { X ) } \ p \in P , A r _ { P } ( p ) = n \ \left [ A T O M \right ]$$

$$\frac { t _ { 1 } \colon T _ { \Sigma } ( X ) \ t _ { 2 } \colon T _ { \Sigma } ( X ) } { t _ { 1 } = t _ { 2 } \colon F o r m _ { \Sigma } ( X ) } \left [ A T O M , E Q \right ]$$

## Fórmulas

- Seja R=(P, ArP) uma assinatura para fórmulas. O conjunto de fórmulas sobre R com variáveis X, denotado por Form  (X) é definido pelas seguintes regras de construção (definição por indução):
- Fórmulas compostas:
- Se 𝐴 é uma fórmula, então (¬𝐴) é uma fórmula
- Se 𝐴 e 𝐵 são fórmulas, então (𝐴 ∧ 𝐵) , (𝐴 ∨ 𝐵) , (𝐴 → 𝐵) e (𝐴 ↔ 𝐵) também são fórmulas
- Se 𝐴 é uma fórmula e v ∈ 𝑋 , então (∀𝑣. 𝐴) e (∃𝑣. 𝐴) são fórmulas

## Fórmulas

## · Fórmulas compostas:

$$\frac { A \colon F o r m _ { \Sigma } ( X ) \ B \colon F o r m _ { \Sigma } ( X ) } { ( A \ b o p \ B ) \colon F o r m _ { \Sigma } ( X ) } \left [ B O P \right ] & \quad \frac { A \colon F o r m _ { \Sigma } ( X ) } { ( \neg A ) \colon F o r m _ { \Sigma } ( X ) } \left [ \text {NEG} \\ \\ \frac { A \colon F o r m _ { \Sigma } ( X ) } { ( \forall v . A ) } \ v \in X _ { \Sigma } \ \left [ \text {UNI} \right ] & \quad \frac { A \colon F o r m _ { \Sigma } ( X ) } { ( \exists v . A ) } \ v \in X _ { \Sigma } \ \left [ \text {EXI} \\ \\ \right ]$$

𝑏𝑜𝑝 ∈ {→, ↔,∧,∨}

## Exemplo

- Assinatura para aritmética:
- Fórmulas sobre a assinatura:
- menor(0,0) · x=0 · maieq(x,add(x,succ(x))) · ∀𝑥. (∃𝑦. 𝑚𝑎𝑖𝑜𝑟(𝑦, 𝑥))
- 2}

```
· OP=(C,F,ArF) · C={0} · F={add, mult, succ} · ArF={add  2, mult  2, succ  1} · R=(P,ArP) · P={menor, meneq, maieq} · ArP={menor  2, meneq  2, maieq 
```

## LÓGICA DE PREDICADOS

Formalização

## Formalização

- Usaremos os quantificadores e também variáveis, que representam indivíduos no mundo que estamos representando
- Os predicados e funções serão grafados com letras maiúsculas, enquanto que as variáveis deverão ser grafadas em letras minúsculas
- Usaremos as letras do fim do alfabeto para designar as variáveis, por exemplo: x, y, z, etc
- Usaremos as letras do início do alfabeto para designar indivíduos (constantes), por exemplo: a, b, c, etc

## Formalização

- Exemplo: Jones é um ladrão
- Primeiro devemos criar um predicado para designar que algo é (ou possui a propriedade de ser) ladrão:
- L(x) = 'x é um ladrão'
- Agora vamos usar uma letra do início do alfabeto para designar o indivíduo:
- j = 'Jones'
- Formalizando:
- L(j)

## Formalização

- Exemplo: Jones é um ladrão
- Domínio = conjunto de todas as pessoas · OP=(C,F,ArF) · C={j} · F={} · ArF={} · R=(P,ArP) · P={L} · ArP={L  1}

## Formalização

- Exemplo: Bob ama Cathy