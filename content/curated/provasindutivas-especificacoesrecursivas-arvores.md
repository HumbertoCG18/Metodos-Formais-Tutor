## Indução Estrutural sobre Árvores

Podemos provar propriedades sobre especificações recursivas para estruturas de dados indutivas utilizando a técnica de prova chamada de Indução Estrutural. A indução estrutural pode ser vista como uma generalização do processo de indução sobre os naturais para outras estruturas indutivas. Assim, uma prova por indução estrutural de uma propriedade P consiste em duas partes:

- a) Mostrar que P vale para todos os elementos especificados nos casos base da definição indutiva da estrutura;
- b) Mostrar que, se P vale para elementos usado para construir novos elementos nos casos de passo de indução da definição indutiva da estrutura, então P vale para os novos elementos.

Seja a seguinte definição indutiva para árvores:

$$\frac{L \in ArvBin(\tau) \quad R \in ArvBin(\tau), x \in \tau}{\langle L, x, R \rangle \in ArvBin(\tau)} cons$$

Seja a seguinte definição equacional recursiva para a função capaz de "espelhar" uma árvore binária:

$$espelho: ArvBin(\tau) \rightarrow ArvBin(\tau)$$

$$espelho(\langle \ \rangle) = \langle \ \rangle \qquad (espelho1)$$

$$espelho(\langle L, x, R \rangle) = \langle espelho(R), x, espelho(L) \rangle \qquad (espelho2)$$

Deseja-se provar

$$\forall A \in ArvBin(\tau). espelho(espelho(A)) = A$$

isto é, que espelho é função inversa de si mesmo.

Observe atentamente a propriedade P que queremos provar por indução em A:

$$P(A) \triangleq espelho(espelho(A)) = A$$

Caso Base:  $P(\langle \rangle)$ 

Provar que  $espelho(espelho(\langle \rangle)) = \langle \rangle$ .

 $espelho(espelho(\langle \rangle))$ 

 $= espelho(\langle \rangle)$  (por espelho1)

 $=\langle \rangle$  (por espelho1)

q.e.d

```
Caso Indutivo: P(L) \wedge P(R) \rightarrow P(\langle L, x, R \rangle)
```

Sejam  $L, R \in ArvBin(\tau)$  e  $x \in \tau$  arbitrários.

Assumir por hipótese de indução (HI1) que espelho(espelho(L)) = L.

Assumir por hipótese de indução (HI2) que espelho(espelho(R)) = R.

Provar que  $espelho(espelho(\langle L, x, R \rangle)) = \langle L, x, R \rangle$ .

 $espelho(espelho(\langle L, x, R \rangle))$ 

$$= espelho(\langle espelho(R), x, espelho(L) \rangle)$$
 (por espelho2)

$$= \langle espelho(espelho(L)), x, espelho(espelho(R)) \rangle$$
 (por espelho2)

$$= \langle L, x, espelho(espelho(R)) \rangle$$
 (por HI1)

$$= \langle L, x, R \rangle$$
 (por HI2)

q.e.d.
