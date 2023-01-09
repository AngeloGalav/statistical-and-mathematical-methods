# Approximation 
During a problem solving process, there are various sources of approximation. 
- _Measure errors_, due to the measure instrument. 
- __Arithmetic errors__, due to the propagation ___of the rounding errors___ of each single operation in an algorithmic process. 
- __Truncation errors__, difference between true result (for actual input) and result produced by given algorithm using exact arithmetic.
	- can be due to the truncation of an infinite procedure to a finite procedure. 
- __Inherent errors__, due to the finite representation of the data of a problem.

### Errors and precisions: definitions 
- Let $x'$ be an approximation of a given number x, then the _absolute error_ of such approximation is the quantity:
$$
E_x = |x' - x|
$$
However, this quantity could be meaningless in some applications.

- The _relative error_ is defined by the absolute error divided by the value of x:
$$
R_x = | \dfrac{x' - x}{x}|, x \ne 0
$$
- The _precision_ is the is the number of digits with which a number is expressed.
- The _accuracy_ is the number of correct significant digits used for approximating some quantity. 

# Finite Numbers representation 
Given a base $β ∈ Z$, with $β > 1$, a number $x ∈ R$, with $x \ne 0$, can be expressed in a unique way as:
$$


\begin{equation}

\begin{split}
x &= sign(x)(d_1 \beta^{-1} + d_2 \beta^{-2} + ...)\beta^{p}
\\ 
&=sign(x)mβ
\end{split}
\end{equation}
$$
where:
- $p \in \mathbb{Z}$
- The digits $d_1, d_2, ...$ satisfy the following conditions:
	- $0 \le d_i \le \beta - 1$
	- $d_1 \ne 0$ and $d_i$ are not all euqal to $\beta -1$ from a certain index $i$ onward. 
	- $\dfrac{1}{\beta} \le m \lt 1$ is the _mantissa_.
	- $\beta^p$ is the _exponential part_. 

The _normalized scientific representation_ of any real number x is the following:
$$
x = sign(x)(0.d_1d_2 . . .)β
$$
Formally, a system of floating point numbers $F(β, t, L, U)$ is defined by the following parameters:
- The base $\beta$
- The precision $t$
- The exponential range $[L, U]$.

Any f.p. number $x ∈ F$ has the following form: 
$$x = sign(x)(d_1β^{−1} + · · · + d_tβ^{ −t})β^p , L ≤ p ≤ U$$
where $d_i \in \mathbb{Z}$ and $0 \le d_i \le \beta - 1$ with $i = 1...t$.

A floating point system is _normalized_ when $d_1 \ne 0$.

Normalization allows one to have a unique representation of each number and, assuming $β = 2$ (i.e. binary system), to not store the leading bit since it will always be 1.

#### Total of numbers in a FP system 
A floating-point number system is finite and discrete. In particular, the total number of normalized floating-point numbers is:
$$
2(β − 1)β^{t−1}(U − L + 1) + 1
$$
- largest floating number (OFL) = $\beta^{U+1}(1-\beta^{-t})$
- smallest positive normalized number (UFL) = $\beta^{U+1}(1-\beta^{-t})$.  

## Rounding 
- _chop_ rounding rule, which consists in truncating x after the t-th digit. 
- _round-to-nearest rounding rule_, which consists in rounding x to the nearest floating-point number.
- The accuracy of a floating-point system is characterized by the machine precision, $\epsilon_{mach}$:
	- With chop rounding: $\epsilon_{mach} = β^{1−t}$ . 
	- With round-to-nearest rounding:$\epsilon_{mach} = \dfrac{1}{2}β^{1−t}$.
- The maximum relative error in representing a real number x within the range of a certain floating-point system is given by:
$$
|\dfrac{fl(x)-x}{x}| \le \epsilon_{mach}
$$
This means that, during the execution of an algorithm, each calculation can produce an error which is at most equal to $\epsilon_{mach}$.

IEEE floating-point standard provides special values to indicate two exceptional situations: 
- _Inf_, which is the result of the division between a finite number and zero. 
- _NaN_, which is the result of undefined or indeterminate operations, such as 0/0, 0 · Inf, Inf/Inf.

### Arithmetic operations
- In __additions and subtractions__, the mantissa of one of the two operands is shifted in order to match the two exponents. _This may cause the loss of some digits of the smaller number, possibly all of them_. 
- In __multiplication__, the result of two t-digits mantissas contains up to 2t digits, so such result may not be representable. 
- In __divisions__, the quotient of two t-digits mantissas may contain more than t digits, such as the non-terminating binary expansion of 1/10. 
- The subtraction between two t-digit numbers having the same sign and similar magnitudes yields a result having less than t digits. The reason is that the leading digits of the two numbers cancel each other. This is called __cancellation__.
	- Example: 
![[simple_cancellation_example.png]]

