# Indução Estrutural sobre Árvores

Podemos provar propriedades sobre especificações recursivas para estruturas de dados indutivas utilizando a técnica de prova chamada de Indução Estrutural. A indução estrutural pode ser vista como uma generalização do processo de indução sobre os naturais para outras estruturas indutivas. Assim, uma prova por indução estrutural de uma propriedade  $P$  consiste em duas partes:

- Mostrar que  $P$  vale para todos os elementos especificados nos casos base da definição indutiva da estrutura;
- Mostrar que, se  $P$  vale para elementos usado para construir novos elementos nos casos de passo de indução da definição indutiva da estrutura, então  $P$  vale para os novos elementos.

Seja a seguinte definição indutiva para árvores:

$$\frac{}{\langle \rangle \in ArvBin(\tau)} \text{ vazia} \qquad \frac{L \in ArvBin(\tau) \quad R \in ArvBin(\tau), x \in \tau}{\langle L, x, R \rangle \in ArvBin(\tau)} \text{ cons}$$

Seja a seguinte definição equacional recursiva para a função capaz de “espelhar” uma árvore binária:

$$\text{espelho}: ArvBin(\tau) \rightarrow ArvBin(\tau)$$

$$\text{espelho}(\langle \rangle) = \langle \rangle \qquad (\text{espelho1})$$

$$\text{espelho}(\langle L, x, R \rangle) = \langle \text{espelho}(R), x, \text{espelho}(L) \rangle \qquad (\text{espelho2})$$

Deseja-se provar

$$\forall A \in ArvBin(\tau). \text{espelho}(\text{espelho}(A)) = A$$

isto é, que *espelho* é função inversa de si mesmo.

Observe atentamente a propriedade  $P$  que queremos provar por indução em  $A$ :

$$P(A) \triangleq \text{espelho}(\text{espelho}(A)) = A$$

Caso Base:  $P(\langle \rangle)$

Provar que  $\text{espelho}(\text{espelho}(\langle \rangle)) = \langle \rangle$ .

$$\text{espelho}(\text{espelho}(\langle \rangle))$$

$$= \text{espelho}(\langle \rangle) \quad (\text{por espelho1})$$

$$= \langle \rangle \qquad \qquad \qquad (\text{por espelho1})$$

q.e.d

Caso Indutivo:  $P(L) \wedge P(R) \rightarrow P(\langle L, x, R \rangle)$

Sejam  $L, R \in \text{ArvBin}(\tau)$  e  $x \in \tau$  arbitrários.

Assumir por hipótese de indução (HI1) que  $\text{espelho}(\text{espelho}(L)) = L$ .

Assumir por hipótese de indução (HI2) que  $\text{espelho}(\text{espelho}(R)) = R$ .

Provar que  $\text{espelho}(\text{espelho}(\langle L, x, R \rangle)) = \langle L, x, R \rangle$ .

$$\begin{aligned} & \text{espelho}(\text{espelho}(\langle L, x, R \rangle)) \\ &= \text{espelho}(\langle \text{espelho}(R), x, \text{espelho}(L) \rangle) && \text{(por espelho2)} \\ &= \langle \text{espelho}(\text{espelho}(L)), x, \text{espelho}(\text{espelho}(R)) \rangle && \text{(por espelho2)} \\ &= \langle L, x, \text{espelho}(\text{espelho}(R)) \rangle && \text{(por HI1)} \\ &= \langle L, x, R \rangle && \text{(por HI2)} \end{aligned}$$

q.e.d.
