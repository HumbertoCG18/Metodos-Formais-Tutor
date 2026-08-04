{0}------------------------------------------------

# Lógica de Hoare – Exercícios

$\{x < 5\} \quad x := x + 1 \quad \{x < 7\}$

$\{x < 5\}$

$\{x + 1 < 7\}$

$x := x + 1$

$\{x < 7\}$

condição de premissa:

$x < 5 \rightarrow x + 1 < 7$

---

$\{a > 0 \wedge b > 0\} \quad x := a; y := b \quad \{x + y > 0\}$

$\{a > 0 \wedge b > 0\}$

$\{a + b > 0\}$

$x := a$

$\{x + b > 0\}$

$y := b$

$\{x + y > 0\}$

condição de premissa:

$a > 0 \wedge b > 0 \rightarrow a + b > 0$

{1}------------------------------------------------

$(a > b) \quad x := -a; y := -b \quad (x < y)$

$(a > b)$

$(-a < -b)$

$x := -a$

$(x < -b)$

$y := -b$

$(x < y)$

condição de prova:

$a > b \rightarrow -a < -b$

---

$(x < y) \quad \text{temp} := x; x := y; y := \text{temp} \quad (y < x)$

~~condição de prova~~

$(x < y)$

$\text{temp} := x$

$(\text{temp} < y)$

$x := y$

$(\text{temp} < x)$

$y := \text{temp}$

$(y < x)$

{2}------------------------------------------------

$\{x < y\} \quad y := y + x; \quad x := y - x; \quad y := y - x \quad \{y < x\}$

$\{x < y + x - x\} \equiv \{x < y\}$

$y := y + x$

$\{y - (y - x) < y - x\} \equiv \{x < y - x\}$

$x := y - x$

$\{y - x < x\}$

$y := y - x$

$\{y < x\}$

//

$\{x < 10\} \quad \text{if } (x > 5) \{x := 4\} \quad \{x < 5\}$

$\{x < 10\}$

$\{x > 5 \rightarrow 4 < 5 \wedge \neg(x > 5) \rightarrow x < 5\}$

$\text{if } (x > 5) \{$

$\{4 < 5\}$

$x := 4$

$\{x < 5\}$

$\}$

$\{x < 5\}$

Condição de prova:

$x < 10 \rightarrow (x > 5 \rightarrow 4 < 5 \wedge \neg(x > 5) \rightarrow x < 5)$

{3}------------------------------------------------

$\{T\} \text{ if } (x < y) \{ x = y \} \{ x > y \}$

$\{T\}$

$\{x < y \rightarrow y > y \wedge \neg(x < y) \rightarrow x > y\}$

$\text{if } (x < y) \{$

$\{y > y\}$

$x = y$

$\{x > y\}$

$\}$

$\{x > y\}$

condição de parâmetros:

$T \rightarrow (x < y \rightarrow y > y \wedge \neg(x < y) \rightarrow x > y)$

$\{T\} \text{ if } (x > y) \{ x = y + 1; y = x + 1 \} \{ x \leq y \}$

$\{T\}$

$\{x > y \rightarrow y + 1 \leq y + 2 \wedge \neg(x > y) \rightarrow x \leq y\}$

$\text{if } (x > y) \{$

$\{y + 1 \leq y + 2\}$

$x = y + 1$

$\{x \leq x + 1\}$

$y = x + 1$

$\{x \leq y\}$

$\}$

$\{x \leq y\}$

condição de parâmetros:

$T \rightarrow (x > y \rightarrow y + 1 \leq y + 2 \wedge \neg(x > y) \rightarrow x \leq y)$

{4}------------------------------------------------

$\{\{T\}\}$

$\{\{x < y \rightarrow y \geq x \wedge y \geq y\} \wedge \neg(x < y) \rightarrow x \geq x \wedge x \geq y\}\}$

if  $(x < y)$  {

$\{\{y \geq x \wedge y \geq y\}\}$

$max := y$

$\{\{max \geq x \wedge max \geq y\}\}$

} else {

$\{\{x \geq x \wedge x \geq y\}\}$

$max := x$

$\{\{max \geq x \wedge max \geq y\}\}$

}

$\{\{max \geq x \wedge max \geq y\}\}$

condição de prova:

$T \rightarrow (\{x < y \rightarrow y \geq x \wedge y \geq y\} \wedge (\neg(x < y) \rightarrow x \geq x \wedge x \geq y))$

{5}------------------------------------------------

$\{T\}$

$\{x < y \rightarrow x \leq y-1 \wedge \neg(x < y) \rightarrow -x \leq -y\}$

$\{x < y\}$

$y := y-1$

$\{x \leq y\}$

$\}$  else  $\{$

$\{-x \leq -y\}$

$x := -x$

$\{x \leq -y\}$

$y := -y$

$\{x \leq y\}$

$\}$

$\{x \leq y\}$

Condição de parada:

$T \rightarrow (x < y \rightarrow x \leq y-1) \wedge (\neg(x < y) \rightarrow -x \leq -y)$