# Exercícios

## Provas por Indução de Especificações Equacionais Recursivas

1) Especificar via equações recursivas o cálculo de potenciação de acordo com as informações que seguem e provar sua correção parcial por indução:

$pot :: \mathbb{N} \times \mathbb{N} \rightarrow \mathbb{N}$   
 $requer: true$   
 $garante: pot(b, p) = b^p$

2) Especificar via equações recursivas o cálculo da subtração truncada de acordo com as informações que seguem e provar sua correção parcial por indução:

$minusNat :: \mathbb{N} \times \mathbb{N} \rightarrow \mathbb{N}$   
 $requer: true$   
 $garante: minusNat(m, n) = m - n, se m \geq n$   
 $garante: minusNat(m, n) = 0, se m \leq n$

3) Provar por indução a correção parcial da função  $som2kR$  que segue:

$som2kR :: \mathbb{N} \rightarrow \mathbb{N}$   
 $requer: true$   
 $garante: som2kR(x) = \sum_{0 \leq k \leq x} 2k$   
 $som2kR(x) = som2kAux(x, 0)$   
 $onde:$   
 $som2kAux :: \mathbb{N} \times \mathbb{N} \rightarrow \mathbb{N}$   
 $requer: true$   
 $garante: som2kAux(x, a) = \left( \sum_{0 \leq k \leq x} 2k \right) + a$   
 $som2kAux(x, a) = a, \quad se \ x = 0$   
 $som2kAux(x, a) = som2kAux(x - 1, a + 2x), \quad se \ x > 0$

4) Seja a seguinte especificação equacional recursiva para a concatenação de duas listas:

$cat: List(\tau) \times List(\tau) \rightarrow List(\tau)$   
 $cat([], l) = l \quad (1)$

$cat(h:T, l) = h: cat(T, l) \quad (2)$

Prove, via indução estrutural, a seguinte propriedade:

$$\forall l_1, l_2, l_3 \in List(\tau). cat(l_1, cat(l_2, l_3)) = cat(cat(l_1, l_2), l_3)$$

5) Seja a seguinte especificação equacional recursiva para o espelhamento de uma árvore binária:

$$espelho: ArvBin(\tau) \rightarrow ArvBin(\tau)$$

$$espelho(\langle \rangle) = \langle \rangle \quad (1)$$

$$espelho(\langle L, x, R \rangle) = \langle espelho(R), x, espelho(L) \rangle \quad (2)$$

Prove, via indução estrutural, a seguinte propriedade:

$$\forall a \in ArvBin(\tau). espelho(espelho(a)) = a$$
