## Prof. Júlio Machado

## **Exercícios**

## **Conjuntos Indutivos**

- 1) Definir um conjunto de regras para construir os conjuntos que seguem:
  - a. Conjunto Pares: conjunto dos números naturais pares tal que  $(0 \in Pares)$
  - b. Conjunto *Impares*: conjunto dos números naturais ímpares tal que (0 ∉ *Impares*)
  - c. Conjunto  $S_1 \triangleq \{a^nbc^n | n \in \mathbb{N}\}$
  - d. Conjunto  $S_2 \triangleq \{a^n b^m | n > 0 \land m > 0\}$
  - e. Conjunto  $S_3 \triangleq \{a^n b^m a^n | n > 0 \land m > 0\}$
  - f. Conjunto  $S_4 \triangleq \{a^n b^m a^i | n > 0 \land m > 0 \land i \ge 0\}$
  - g. Conjunto Pot2: conjunto das potências de dois {1,2,4,8,16,32,...}
  - h. Conjunto S = {0,1,3,7,15,31,...}
- 2) Através de árvores de prova, mostrar que:
  - a.  $8 \in Pares$
  - b. 9 ∉ Pares
  - c.  $11 \in Impares$
  - d.  $aaabccc \in S_1$
  - e.  $aaab \in S_2$
  - f.  $aba \in S_3$
  - g.  $aabbbaaa \notin S_3$
  - h.  $aaabaaa \in S_4$
  - i.  $aaa \in S_4$
  - j.  $aaabb \in S_4$
  - k.  $aaaba \in S_4$
  - I. baaa  $\notin S_4$
- 3) Considere o conjunto *Prop* das proposições válidas sobre ∑:

$$\begin{split} S &\triangleq \{\land, \lor, \rightarrow\} \\ X &\triangleq \{x_0\,, x_1\,, \ldots, x_n\} \\ \Sigma &\triangleq S \cup X \end{split}$$

$$\frac{1}{v \in Prop} (v \in X) Var \qquad \frac{p \in Prop \quad q \in Prop}{(p \ bop \ q) \in Prop} (bop \in S) Bop$$

| $p \in Prop$                    |  |
|---------------------------------|--|
| $\overline{(p) \in Prop}^{Par}$ |  |

Demonstre que:

a. 
$$((x_0 \land x_1) \rightarrow x_2) \in Prop$$

b. 
$$(((x_0 \land x_1) \lor (x_2 \land x_3)) \to (x_4 \land x_5)) \in Prop$$

4) Considere o exercício anterior e apresente uma regra para introduzir o operador unário de negação representado pelo símbolo ¬. Após, demonstre que:

a. 
$$(\neg(x_0 \land x_1) \rightarrow x_2) \in Prop$$

b. 
$$(((x_0 \land x_1) \lor (\neg x_2 \land x_3)) \rightarrow \neg (x_4 \land x_5)) \in Prop$$
