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

$=T(\frac{n}{13}) = 13(13T(\frac{n}{13^{2}}) + 5) + 5$

$=13^{2}T(\frac{n}{13^{2}}) + 70$

$...$

$=13^{i}T(\frac{n}{13^{i}})+ 5*\sum\limits _{j=0}^{i}13^j$

Now to reach base case I believe $i$ needs to be  $log_{13}(n)$ again here leaving:

$=13^{log_{13}(n)}T(\frac{n}{13^{log_{13}(n)}})+ 5*\sum\limits _{j=0}^{\log{ _{13}}{(n)}} 13^j$

$=nT(1) + 5*\sum\limits _{j=0}^{\log{ _{13}}{(n)}} 13^j$

$= (1*n) + 5 * (13^{\log{ _{13}}{n}} + \sum\limits _{j=0}^{\log{ _{13}}{(n-1)}} 13^j)$

$= n + 5 * (n + \sum\limits _{j=0}^{\log{ _{13}}{(n-1)}} 13^j)$

I believe that based off the final part $ n + 5 * (n + \sum\limits _{j=0}^{\log{ _{13}}{(n-1)}} 13^j)$ the bound would be $\Theta(n)$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

$T(n) = 13T(\frac{n}{13}) + 2n$

$=13(13T(\frac{n}{13^{2}}) + 2(\frac{n}{13})) + 2n$

$=13^{2}T(\frac{n}{13^{2}}) + 4n$

$...$

$=13^iT(\frac{n}{13^{i}}) + (2n)i$

Again we need $i$ to be $log_{13}(n)$ giving us:

$=13^{log_{13}(n)}T(\frac{n}{13^{log_{13}(n)}}) + (2n)(log_{13}(n))$

$=nT(1) + (2n)(log_{13}(n))$
