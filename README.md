
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Assessing the performance of real-time epidemic forecasts: A case study of Ebola in the Western Area region of Sierra Leone, 2014-15

This repository contains the data and code for our paper:

> Sebastian Funk, Anton Camacho, Adam J. Kucharski, Rachel Lowe,
> Rosalind M. Eggo and W. John Edmunds. Assessing the performance of
> real-time epidemic forecasts: A case study of Ebola in the Western
> Area region of Sierra Leone, 2014-15. PLoS Comput Biol 15(2):
> e1006785. <https://doi.org/10.1371/journal.pcbi.1006785>

### How to download or install

You can install the code and data as an R package,
`ebola.forecast.wa.sl`, from GitHub with:

``` r
devtools::install_github("sbfnk/ebola.forecast.wa.sl")
```

### Included data sets

The package includes five data sets. One of them contains the data of
Ebola cases from Western Area that was used for the analysis. It can be
loaded with

``` r
data(ebola_wa)
```

The other four data sets contain Monte-Carlo samples from the
semi-mechanistic model used for forecasts, as well as the three null
models. The data sets are called `samples_semi_mechanistic`,
`samples_bsts`, `samples_deterministic` and `samples_deterministic`, and
they can be loaded with

``` r
data(samples)
```

The data sets from the null models can be re-created using

``` r
samples_bsts <- null_model_bsts()
samples_deterministic <- null_model_deterministic()
samples_unfocused <- null_model_unfocused()
```

### Table and figures

The table and figures in the manuscript can be re-created using

``` r
t1 <- table1()
print(t1)
t2 <- table2()
print(t2)

library('cowplot')
p1 <- figure1()
p2 <- figure2()
p3 <- figure3()
p4 <- figure4()
ggsave("figure1.pdf", p1, width=18, height=6.6, dpi=300, units="cm")
ggsave("figure2.pdf", p2, width=18, height=6.6, dpi=300, units="cm")
ggsave("figure3.pdf", p3, width=18, height=11.1, dpi=300, units="cm")
ggsave("figure4.pdf", p4, width=15.9, height=11.1, dpi=300, units="cm")
```
