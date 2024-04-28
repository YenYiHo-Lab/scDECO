<p align="center">
  <img src="./images/scdeco_logo.svg" alt="scDECO logo" width="400">
</p>

<p align="center">
  <align="center"><ins>s</ins>ingle-<ins>c</ins>ell <ins>d</ins>iff<ins>e</ins>rential <ins>co</ins>-expression
</p>

<div align="center">
  <a href="https://doi.org/10.1111/biom.13701">
    <img src="https://img.shields.io/badge/DOI-doi.org%2F10.1111%2Fbiom.13701-blue" alt="DOI">
  </a>
  <a href="https://doi.org/10.1111/biom.13457">
    <img src="https://img.shields.io/badge/DOI-doi.org%2F10.1111%2Fbiom.13457-blue" alt="DOI">
  </a>
</div>





## Description

scDECO is an R package for estimating differential co-expression in single-cell RNA-seq data. 

Differential co-expression refers to correlation between two random variables $X_1, X_2$ changing with respect to the value of some covariate(s). 

<img src="images/dynamic_corr_plot.svg" alt="differential coexpression" width="700">


The package contains implementations for two different Bayesian models:
1. `scDECO.cop`: fits a Gaussian copula model with flexible, covariate-dependent, optionally zero-inflated marginals
2. `scDECO.pg`: fits a zero-inflated Poisson-Gamma model with correlation imparted through a latent bivariate normal variable


## Installation

```{r, eval=FALSE, message=FALSE, warning=FALSE}
devtools::install_github("YenYiHo-Lab/scDECO")
library(scDECO)
```

## Usage

```{r}
n <- 2500

# simulate 
x.use = rnorm(n) # covariate(s) mu and rho are dependent on
w.use = runif(n,-1,1) # covariate(s) ZINF is dependent on

eta1.use = c(-2.2, 0.7) # ZINF parameters for marginal 1
eta2.use = c(-2, 0.8) # ZINF parameters for marginal2
beta1.use = c(1,0.5) # mean parameters for marginal 1
beta2.use = c(1,1) # mean parameters for marignal 2
alpha1.use = 7 # alpha parameter for margin 1
alpha2.use = 3 # alpha parameter for marign2
tau.use = c(-0.2, .3) # rho parameters
```











