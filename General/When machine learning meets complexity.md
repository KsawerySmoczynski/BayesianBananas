# [01 - When machine learning meets complexity](https://towardsdatascience.com/when-machine-learning-meets-complexity-why-bayesian-deep-learning-is-unavoidable-55c97aa2a9cc)
tags: [[00_General]]

## Takeaways:
* Bearing in mind that mathematical descriptions of anything more or less complex are merely models and **not** fundamental truths ([Cohen & Stewart, 1995](https://www.goodreads.com/book/show/287896.Nature_s_Numbers)), we can directly deduce that Bayesian inference is in any complex instance more appropriate to use than frequentist inference. **In Bayesian inference, we see the model parameters $θ$ as random variables**, i.e. we want to learn them, whereas we see **in frequentist inference the model parameters $θ$ as fixed, but unknown descriptions of the truth**.

*   In essence, this means that proponents of frequentist inference claim that we are able to describe the truth with an infinite number of experiments and that these model parameters θ describing the truth will never change.
 
* This is precisely what we do in **Bayesian methods**: the intractable posterior probability distribution $p(θ|D)$ is approximated, either by a variational distribution $q(θ|D)$ how we like to do it in neural networks, or with Monte Carlo methods how we often do it in probabilistic graphical models. 
  
*  In **frequentist inference** instead, we take a somehow ignorant approach and just repeat the experiment more often with the hope to finally have an acceptable confidence interval which includes our true parameter. This “level of acceptance” is called confidence level and denoted as _α_, which you have probably seen before. Commonly agreed on, $α$ should be at least 95%.

## Questions:
* Parametry modelu stają się zmiennymi losowymi. Mamy założenie, że parametry modelu reprezentowane przez zmienne losowe pochodzą z jakiejś dystrybucji  (pierwszy prior) np. Gaussowskiej. 
* Ucząc probabilistyczny model zbiegamy do danych. Czy overfit Bayesowskiej sieci nie będzie miał danej mody i bardzo niskiej wariancji -> w nieskończoności będzie dążył do modelu deterministycznego/frequentistowego? ([[Should all Machine Learning be Bayesian? Should all Bayesian models be non-parametric?]] -> Asymptotic consensus)
*  Jeżeli nie to będzie musiał być zbieżny do wielu wartości czego nie jesteśmy w stanie zareprezentować jako rozkład normalny. 
*  Jeżeli nie, i jesteśmy w stanie reprezentować wagi jako coś bardziej elastycznego niż rozkład gaussowski, (coś będącego w stanie reprezentować np. rozkłady wielomodalne) to otrzymujemy w granicy klasę modeli będących w stanie aproksymować dane. Poza przybliżonymi danymi, każdy z tych modeli powinien mieć inne obszary o dużej wariancji wynikające z rozbieżności parametrów. 
*  **Mając wiecej parametrów niż zmiennych -> częsty case przy sieciach jesteśmy w stanie przybliżać te same wartości wieloma funkcjami** -> czy w casie bayesowskim w granicy nie przybliżamy po prostu tych funkcji.

