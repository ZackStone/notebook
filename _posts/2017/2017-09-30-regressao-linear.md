---
layout: post
title:  "Regressão Linear"
date:   2017-09-30 23:52:00 -0300
categories: machine-learning
tags: machine-learning regressão-linear
language: br
summary: Breve descrição sobre o post de regressão linear
---

* Do not remove this line (it will not be displayed)
{:toc}

# Análise de Regressão

Uma análise de regressão gera uma equação para descrever a relação estatística entre uma ou mais preditoras e a variável de resposta.


## Regressão Linear

Tem esse nome porque a realação entre as variáveis é descrita por uma função linear

Exemplo: `y = a + bx`

Nesse tipo de regressão existe apenas uma variável de saída (y) e uma de entrada (x).

Exemplo: `y = f(x)`

## Regressão Não Linear


## Regressão Linear Simples

Existe uma única variável de saída y (Variável dependente)

Existe uma única varíável de entrada x (Variável independente)


## Regressão Linear Múltipla

A intuição nos diz que, geralmente, se pode melhorar uma predição se incluirmos novas variáveis independentes ao modelo (equação) de regressão.

Basicamente, ela leva em consideração diversas variáveis de entrada xi, i=1,...p, influenciando ao mesmo tempo uma única variável de saída, y.

Nesse tipo de regressão existe apenas uma variável de saída (y) e várias de entrada (xi
, i=1,...p).

Exemplo: `y = f(x1, x2, ..., xp)`


Antes de tudo devemos buscar o "equilíbrio" entre o número de parâmetros e a "capacidade preditiva" do modelo.

- Número excessivo de parâmetros
	- Overfitting (sobreajustamento): modelo é muito específico
- Número reduzido de parâmetros
	- Underfitting (subajustamento): modelo pode ser pouco preditivo


### Forward Elimination

Which involves starting with no variables in the model, testing the addition of each variable using a chosen model fit criterion, adding the variable (if any) whose inclusion gives the most statistically significant improvement of the fit, and repeating this process until none improves the model to a statistically significant extent.

### Backward Elimination

Backward elimination, which involves starting with all candidate variables, testing the deletion of each variable using a chosen model fit criterion, deleting the variable (if any) whose loss gives the most statistically insignificant deterioration of the model fit, and repeating this process until no further variables can be deleted without a statistically significant loss of fit.

### Bidirectional Elimination

a combination of the above, testing at each step for variables to be included or excluded.

### Todos os modelos possíveis



# Referências

- [PDF Aula de Regressão (FACOM - UFU)](http://www.facom.ufu.br/~backes/pgc204/Aula06-Regressao.pdf)
- [Udemy - Machine Learning A-Z™: Hands-On Python & R In Data Science](https://www.udemy.com/machinelearning)
- [support.minitab.com](https://support.minitab.com/pt-br/minitab/18/help-and-how-to/modeling-statistics/regression/supporting-topics/basics/types-of-regression-analyses/)
- [en.wikipedia.org](https://en.wikipedia.org/wiki/Stepwise_regression)
