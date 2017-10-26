
<!-- README.md is generated from README.Rmd. Please edit that file -->
styles
======

The goal of styles is to create and apply ggplot-style themes to base plots.

Installation
------------

You can install styles from github with:

``` r
# install.packages("devtools")
devtools::install_github("lizhmartin/styles")
```

Example
-------

This is a basic example which shows you how to solve a common problem:

``` r
library(styles)

# create a new style:
colour <- "darkblue"
colour_light <- scales::alpha(colour, 0.5)

better <- new_style(par = list(pch = 16,
                               fg = grey(0.6),
                               col.axis = grey(0.4),
                               col.lab = grey(0.2),
                               las = 1,
                               col.main = grey(0.4),
                               col.sub = grey(0.4),
                               tcl = -0.25),
                    graphics = list(axis = list(hadj = 0.5),
                                    hist.default = list(col = colour,
                                                        border = "white",
                                                        main = "",
                                                        ylab = "count"),
                                    plot.xy = list(col = colour,
                                                   lwd = 2.5,
                                                   cex = 1.5),
                                    barplot.default = list(col = colour,
                                                           border = NA,
                                                           space = 0.3),
                                    boxplot.default = list(col = colour_light,
                                                           border = colour,
                                                           pars = list(boxwex = 0.8,
                                                                       staplewex = 0.5,
                                                                       outwex = 0.5,
                                                                       cex = 1,
                                                                       whisklty = "solid")),
                                    title = list(line = 2)))



plot_mat <- matrix(1:8, nrow = 2, byrow = FALSE)
layout(plot_mat)

example_plots()

style(better)
example_plots()
```

![](README-example-1.png)

``` r

remove_style()
```
