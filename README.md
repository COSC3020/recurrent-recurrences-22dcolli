[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

Note: I chose to use substitution on all three problems.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

$T(n) = T(\frac{n}{13}) + 5$

$=T(\frac{n}{13}) = (T(\frac{n}{13^{2}}) + 5) + 5$

$...$ (went on until pattern became evident)

$=T(\frac{n}{13^{i}}) + 5(i)$

$i$ will equal $log_{13}(n)$ to reach base case which gives us:

$T(\frac{n}{13^{log_{13}(n}}) + 5(log_{13}(n))$

$=T(1) + 5(log_{13}(n))$

$=1 + 5(log_{13}(n))$

Based on this we assume the bound is $\Theta(log(n))$ because we ignore the constants and focus on the most impactful growth rate


2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

$T(n) = 13T(\frac{n}{13}) + 5$

$=T(\frac{n}{13}) = (13T(\frac{n}{13^{2}}) + 5) + 5$

$...$ (went on until pattern became evident)

$=T(\frac{n}{13^{i}}) + 5(i)$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$
