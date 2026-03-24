# MÉTODOS FORMAIS

Prof. Júlio Machado

# LÓGICA PROPOCIONAL

Introdução

Baseado nos materiais do Prof. Daniel Callegari

## Proposição

- Costuma-se usar a palavra "proposição" para designar o significado de uma sentença ou oração declarativa.
- Exemplo: "João ama Maria" é o mesmo que "Maria é amada por João".

## Proposição

- Toda proposição é uma frase (mas nem toda frase é uma proposição); uma frase é uma proposição apenas quando admite um dos dois valores lógicos: Falso (F) ou Verdadeiro (V).
- Frases que não são proposições
  - Pare!
  - Quer uma xícara de café?
  - Eu não estou bem certo se esta cor me agrada.
- Frases que são proposições
  - A lua é o único satélite do planeta terra (V)
  - A cidade de Salvador é a capital do estado do Amazonas (F)
  - O numero 712 é ímpar (F)
  - Raiz quadrada de dois é um número irracional (V)

### Composição de Proposições

- É possível construir proposições a partir de proposições já existentes. Este processo é conhecido por Composição de Proposições. Suponha que tenhamos duas proposições,
- A = "Maria tem 23 anos"
- B = "Maria é menor"

## Composição de Proposições

```
"Maria não tem 23 anos"                     (não(A))
"Maria não é menor"                         (não(B))
"Maria tem 23 anos" e "Maria é menor"       (A e B)
"Maria tem 23 anos" ou "Maria é menor"      (A ou B)
"Maria não tem 23 anos" e "Maria é menor"   (não(A) e B)
"Maria não tem 23 anos" ou "Maria é menor"  (não(A) ou B)
"Maria tem 23 anos" ou "Maria não é menor"  (A ou não(B))
"Maria tem 23 anos" e "Maria não é menor"   (A e não(B))
"Se "Maria tem 23 anos" então "Maria é menor" (se A então B)
"Se "Maria não tem 23 anos" então "Maria é menor" (se não(A) então B)
"Maria não tem 23 anos" e "Maria é menor" (não(A) e B)
```

## Composição de Proposições

![](content/images/logicaproposicional-sintaxe-_page_6_Figure_1.png)

# LÓGICA PROPOCIONAL

Sintaxe

Baseado nos materiais do Prof. Alfio Martini

 Ao apresentarmos uma linguagem formal, precisamos fornecer os componentes básicos da linguagem, chamados de alfabeto, para em seguida fornecer as regras de formação da linguagem, também chamada de gramática.

- Na Lógica Proposicional, o alfabeto é constituído dos seguintes elementos:
  - Um conjunto enumerável de símbolos atômicos para variáveis proposicionais, que representam as sentenças declarativas
    - {p,q,r,...}
  - Símbolos para os conectivos lógicos e para os valores lógicos (verdadeiro e falso)

| operador              | significado                      |
|-----------------------|----------------------------------|
|                       | (bottom), constante para falso   |
| T                     | (top), constante para verdadeiro |
|                       | negação, não                     |
| $\wedge$              | conjunção, e                     |
| V                     | disjunção, ou                    |
| $\rightarrow$         | implicação, seentão              |
| $\longleftrightarrow$ | equivalência, se e somente se    |

Símbolos para agrupamentos via parênteses ( e )

- Os elementos da linguagem da Lógica Proposicional são chamados de fórmulas
- O conjunto de fórmulas da Lógica Proposicional (chamado de fórmulas bem-formadas, representado pelo símbolo  $P_{\Sigma}$ ) será definido por *indução* 
  - Base da indução: o conjunto já possui alguns elemento conhecidos
  - Passo da indução: adiciona-se elementos ao conjunto de acordo com algumas regras

• Toda proposição atômica no conjunto  $\Sigma = \{p, q, r, ...\}$  é uma fórmula bem-formada, ou seja,  $\{p, q, r, ...\} \subset P_{\Sigma}$ 

$$\frac{v \in \Sigma}{v \in P_{\Sigma}} (ATM)$$

• As constantes  $\bot$  e  $\top$  estão em  $P_{\Sigma}$ 

$$\frac{}{\perp \in P_{\Sigma}}(CONST1)$$

$$\frac{}{\top \in P_{\Sigma}}(CONST2)$$

• Se  $\phi$  é uma fórmula bem-formada, então  $(\neg \phi)$  é uma fórmula bem-formada

$$\frac{\phi \in P_{\Sigma}}{(\neg \phi) \in P_{\Sigma}}(NEG)$$

• Se  $\phi$  e  $\psi$  são fórmulas bem-formadas, então  $(\phi \land \psi)$  é uma fórmula bem-formada

$$\frac{\phi \in P_{\Sigma}, \psi \in P_{\Sigma}}{(\phi \land \psi) \in P_{\Sigma}}(E)$$

• Se  $\phi$  e  $\psi$  são fórmulas bem-formadas, então  $(\phi \lor \psi)$  é uma fórmula bem-formada

$$\frac{\phi \in P_{\Sigma}, \psi \in P_{\Sigma}}{(\phi \vee \psi) \in P_{\Sigma}}(OU)$$

• Se  $\phi$  e  $\psi$  são fórmulas bem-formadas, então  $(\phi \rightarrow \psi)$  é uma fórmula bem-formada

$$\frac{\phi \in P_{\Sigma}, \psi \in P_{\Sigma}}{(\phi \to \psi) \in P_{\Sigma}} (IMP)$$

• Se  $\phi$  e  $\psi$  são fórmulas bem-formadas, então ( $\phi \leftrightarrow \psi$ ) é uma fórmula bem-formada

$$\frac{\phi \in P_{\Sigma}, \psi \in P_{\Sigma}}{(\phi \leftrightarrow \psi) \in P_{\Sigma}} (EQUI)$$

#### Fórmulas bem-formadas

$$(p \land q)$$

$$((\bot \lor q) \to r)$$

$$(((\neg q) \lor (\neg r)) \leftrightarrow (p \land s))$$

$$(p \to (q \to r))$$

#### Fórmulas mal-formadas

$$p \to q$$

$$(p \land q \neg)$$

$$(\lor p \lor q)$$

$$((p \land q) \lor \neg r)$$

$$p \land q$$
