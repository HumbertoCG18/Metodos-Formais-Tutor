# Exercícios

# Formalização e prova de algoritmos como equações recursivas no Isabelle (parte 2)

1) Podemos provar propriedades sobre especificações recursivas para estruturas de dados indutivas utilizando a técnica de prova por indução estrutural. Dada a especificação indutiva de listas e as seguintes especificações recursivas, prove as propriedades indicadas no Isabelle utilizando a linguagem Isar de forma detalhada, justificando cada passo de prova. Utilize o tipo de dados “a list” do Isabelle. Observe que a operação “:” para construção de listas é representada pelo símbolo “#” no Isabelle.

$$\frac{}{[] \in List(\tau)} \text{empty}$$

$$\frac{L \in List(\tau), h \in \tau}{h: L \in List(\tau)} \text{cons}$$

$$cat: List(\tau) \times List(\tau) \rightarrow List(\tau)$$

$$cat([], l) = l \quad (cat1)$$

$$cat(h: T, l) = h: cat(T, l) \quad (cat2)$$

$$tamanho: List(\tau) \rightarrow \mathbb{N}$$

$$tamanho([]) = 0 \quad (tamanho1)$$

$$tamanho(h: T) = 1 + tamanho(T) \quad (tamanho2)$$

a)  $\forall L_1, L_2, L_3 \in List(\tau). (cat(L_1, cat(L_2, L_3)) = cat(cat(L_1, L_2), L_3))$

b)  $\forall L_1, L_2 \in List(\tau). (tamanho(cat(L_1, L_2)) = tamanho(L_1) + tamanho(L_2))$

2) Podemos provar propriedades sobre especificações recursivas para estruturas de dados indutivas utilizando a técnica de prova por indução estrutural. Dada a especificação indutiva de árvores e as seguintes especificações recursivas, prove as propriedades indicadas no Isabelle utilizando a linguagem Isar de forma detalhada, justificando cada passo de prova.

$$\frac{}{\langle \rangle \in ArvBin(\tau)} \text{vazia}$$

$$\frac{L \in ArvBin(\tau) \quad R \in ArvBin(\tau), x \in \tau}{\langle L, x, R \rangle \in ArvBin(\tau)} \text{cons}$$

$$numnodos: ArvBin(\tau) \rightarrow \mathbb{N}$$

$$numnodos(\langle \rangle) = 0 \quad (1)$$

$$\text{numnodos}(\langle L, x, R \rangle) = 1 + \text{numnodos}(L) + \text{numnodos}(R) \quad (2)$$

*espelho: ArvBin( $\tau$ )  $\rightarrow$  ArvBin( $\tau$ )*

$$\text{espelho}(\langle \rangle) = \langle \rangle \quad (\text{espelho1})$$

$$\text{espelho}(\langle L, x, R \rangle) = \langle \text{espelho}(R), x, \text{espelho}(L) \rangle \quad (\text{espelho2})$$

*conteudo: ArvBin( $\tau$ )  $\rightarrow$  List( $\tau$ )*

$$\text{conteudo}(\langle \rangle) = [ ] \quad (\text{conteudo1})$$

$$\text{conteudo}(\langle L, x, R \rangle) = x: \text{cat}(\text{conteudo}(L), \text{conteudo}(R)) \quad (\text{conteudo2})$$

Utilize o seguinte tipo de dados no Isabelle para a codificação de árvores:

|                                                              |
|--------------------------------------------------------------|
| datatype 'a ArvBin = Vazia   Nodo "'a ArvBin" 'a "'a ArvBin" |
|--------------------------------------------------------------|

a)  $\forall A \in \text{ArvBin}(\tau). (\text{espelho}(\text{espelho}(A)) = A)$

b)  $\forall A \in \text{ArvBin}(\tau). (\text{numnodos}(A) = \text{tamanho}(\text{conteudo}(A)))$
