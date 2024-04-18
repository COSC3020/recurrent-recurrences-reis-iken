[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

**MY ANSWER:**

1. We can substitute in T(n) for a few iterations:

T(n) = (n/13) + 5

= (n/13^2) + 10

= (n/13^3) + 15

Thus, we can make the generalization:

= (n/13^i) + 5i

For i = $\log_{13} n$:

= T(1) + 5$\log_{13} n$

Since T(1) = 1, we get:

T(n) = 1 + 5$\log_{13} n$

By this, we know that the big $\Theta$ time complexity is $\Theta(logn)$

2. We shall substitute in T(n) for a few iterations:

T(n) = 13T(n/13) + 5

= 13^2T(n/13^2) + 13*5 + 5

Thus, we can make our generalization:

T(n) = 13^iT(n/13^i) + 5(1 + 13 + 13^2 + 13^3 + ... + 13^(i-1))

We have a geometric series in there! Let's simplify:

T(n) = 13^iT(n/13^i) + 5((13^i - 1)/12)

For i = $\log_{13} n$:

T(n) = n * T(1) + 5((n - 1)/12)

Since T(1) = 1, we get:

T(n) = n + 5((n - 1)/12)

= n + (5/12)n - 5/12

By this, we can conclude that the big $\Theta$ time complexity is $\Theta(n)$
