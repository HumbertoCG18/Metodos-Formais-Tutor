## Prof. Júlio Machado

## Indução Estrutural sobre Listas

Podemos provar propriedades sobre especificações recursivas para estruturas de dados indutivas utilizando a técnica de prova chamada de Indução Estrutural. A indução estrutural pode ser vista como uma generalização do processo de indução sobre os naturais para outras estruturas indutivas. Assim, uma prova por indução estrutural de uma propriedade P consiste em duas partes:

- a) Mostrar que P vale para todos os elementos especificados nos casos base da definição indutiva da estrutura;
- b) Mostrar que, se P vale para elementos usado para construir novos elementos nos casos de passo de indução da definição indutiva da estrutura, então P vale para os novos elementos.

Seja a seguinte definição indutiva para listas:

$$\frac{L \in List(\tau), h \in \tau}{h: L \in List(\tau)} cons$$

Seja a seguinte definição equacional recursiva para a concatenação de duas listas:

$$cat: List(\tau) \times List(\tau) \rightarrow List(\tau)$$

$$cat([ ],l) = l \qquad (cat1)$$

$$cat(h:T,l) = h: cat(T,l) \qquad (cat2)$$

Deseja-se provar que cat é associativa, isto é:

$$\forall L_1, L_2, L_3 \in List(\tau). \, cat\big(L_1, cat(L_2, L_3)\big) = cat(cat(L_1, L_2), L_3)$$

Observe atentamente a propriedade P que queremos provar por indução em  $L_1$ , já que esse é o parâmetro que sofre o processo de recursão na definição da função cat:

$$P(L) \triangleq \forall L_2, L_3 \in List(\tau). \, cat\big(L, cat(L_2, L_3)\big) = cat(cat(L, L_2), L_3)$$

Caso Base: P([ ])

Provar que  $\forall L_2, L_3 \in List(\tau)$ .  $cat([ ], cat(L_2, L_3)) = cat(cat([ ], L_2), L_3)$ .

Sejam  $L_2, L_3 \in List(\tau)$  arbitrárias.

$$cat\big([\quad], cat(L_2, L_3)\big)$$

$$= cat(L_2, L_3) \qquad \text{(por } cat1)$$

$$= cat(cat([\quad], L_2), L_3) \quad \text{(por } cat1)$$
q.e.d

```
\begin{aligned} & \underline{\text{Caso Indutivo:}}\ P(L) \to P(h;L) \\ & \text{Sejam}\ L_1 \in \textit{List}(\tau)\ \text{e}\ h \in \tau\ \text{arbitrários}. \\ & \text{Assumir por hipótese de indução}\ & \text{(HI)}\ & \text{que}\ & \forall L_2, L_3 \in \textit{List}(\tau).\ cat\big(L_1, cat(L_2, L_3)\big) = \\ & cat(cat(L_1, L_2), L_3). \\ & \text{Provar que}\ & \forall L_2, L_3 \in \textit{List}(\tau).\ cat\big(h:L_1, cat(L_2, L_3)\big) = cat(cat(h:L_1, L_2), L_3). \\ & \text{Sejam}\ L_2, L_3 \in \textit{List}(\tau)\ \text{arbitrárias}. \\ & cat\big(h:L_1, cat(L_2, L_3)\big) \\ & = h: cat\big(L_1, cat(L_2, L_3)\big)\ & \text{(por cat2)} \\ & = h: cat(cat(L_1, L_2), L_3)\ & \text{(por cat2)} \end{aligned}
```

 $= cat(cat(h:L_1,L_2),L_3)$  (por cat2)

q.e.d.
