## **Exercícios**

## Formalização e prova de algoritmos como equações recursivas no Isabelle (parte 2)

1) Podemos provar propriedades sobre especificações recursivas para estruturas de dados indutivas utilizando a técnica de prova por indução estrutural. Dada a especificação indutiva de listas e as seguintes especificações recursivas, prove as propriedades indicadas no Isabelle utilizando a linguagem Isar de forma detalhada, justificando cada passo de prova. Utilize o tipo de dados "'a list" do Isabelle. Observe que a operação ":" para construção de listas é representada pelo símbolo "#" no Isabelle.

$$\frac{L \in List(\tau), h \in \tau}{h: L \in List(\tau)} cons$$

$$cat: List(\tau) \times List(\tau) \to List(\tau)$$

$$cat([\quad], l) = l \qquad (cat1)$$

$$cat(h: T, l) = h: cat(T, l) \qquad (cat2)$$

$$tamanho: List(\tau) \to \mathbb{N}$$

$$tamanho([\quad]) = 0 \qquad (tamanho1)$$

$$tamanho(h: T) = 1 + tamanho(T) \qquad (tamanho2)$$

a) 
$$\forall L_1, L_2, L_3 \in List(\tau). \left( cat(L_1, cat(L_2, L_3)) = cat(cat(L_1, L_2), L_3) \right)$$
  
b)  $\forall L_1, L_2 \in List(\tau). \left( tamanho(cat(L_1, L_2)) = tamanho(L_1) + tamanho(L_2) \right)$ 

2) Podemos provar propriedades sobre especificações recursivas para estruturas de dados indutivas utilizando a técnica de prova por indução estrutural. Dada a especificação indutiva de árvores e as seguintes especificações recursivas, prove as propriedades indicadas no Isabelle utilizando a linguagem Isar de forma detalhada, justificando cada passo de prova.

$$\frac{L \in ArvBin(\tau) \quad R \in ArvBin(\tau), x \in \tau}{\langle L, x, R \rangle \in ArvBin(\tau)} cons$$

 $numnodos: ArvBin(\tau) \rightarrow \mathbb{N}$ 

$$numnodos(\langle \ \ \rangle) = 0 \tag{1}$$

```
numnodos(\langle L,x,R\rangle) = 1 + numnodos(L) + numnodos(R) \tag{2} espelho: ArvBin(\tau) \rightarrow ArvBin(\tau) espelho(\langle \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \
```

a) 
$$\forall A \in ArvBin(\tau)$$
.  $(espelho(espelho(A)) = A)$ 

b)  $\forall A \in ArvBin(\tau). \left(numnodos(A) = tamanho(conteudo(A))\right)$
