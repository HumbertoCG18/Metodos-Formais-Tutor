{0}------------------------------------------------

# EQUAÇÕES RECURSIVAS III

1) ALTURA:  $ARV\ B\ I\ N(T) \rightarrow \mathbb{N}$

$$\{ ALTURA(\langle \rangle) = 0$$

$$\{ ALTURA(\langle L, \alpha, R \rangle) = 1 + \max(ALTURA(L), ALTURA(R))$$

2) NUMFOLHAS:  $ARV\ B\ I\ N(T) \rightarrow \mathbb{N}$

$$\{ NUMFOLHAS(\langle \rangle) = 0$$

$$\{ NUMFOLHAS(\langle \langle \rangle, \alpha, \langle \rangle \rangle) = 1$$

$$\{ NUMFOLHAS(\langle L, \alpha, R \rangle) = NUMFOLHAS(L) + NUMFOLHAS(R)$$

3) SOMA:  $ARV\ B\ I\ N(\mathbb{N}) \rightarrow \mathbb{N}$

$$\{ SOMA(\langle \rangle) = 0$$

$$\{ SOMA(\langle L, \alpha, R \rangle) = \alpha + SOMA(L) + SOMA(R)$$

4) ESPELHO:  $ARV\ B\ I\ N(T) \rightarrow ARV\ B\ I\ N(T)$

$$\{ ESPELHO(\langle \rangle) = \langle \rangle$$

$$\{ ESPELHO(\langle L, \alpha, R \rangle) = \langle ESPELHO(R), \alpha, ESPELHO(L) \rangle$$

5) PRÉ:  $ARV\ B\ I\ N(T) \rightarrow LIST(T)$

$$\{ PRÉ(\langle \rangle) = []$$

$$\{ PRÉ(\langle L, \alpha, R \rangle) = \alpha : CAT(PRÉ(L), PRÉ(R))$$