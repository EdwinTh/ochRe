
Australia-themed Colour Palettes
================================

Ochre is a brownish-yellow pigment that occurs naturally in soils across Australia. Historically, ochre has been used for artwork by many indigenous cultures, including the Aboriginal people of Australia.

The goal of `ochRe` is to provide colour palettes inspired by Australian art, landscapes and wildlife. The palettes can be used in conjunction with `ggplot2` or `plot` to provide colours to data plots. There are 16 different palettes (at the moment!), each one based on an iconic Australian artwork, landscape or creature. Some palettes are more suitable for displaying qualitative data, others will look fabulous used in sequential plots. More information can be found in the vignette, including which palettes work best for those with impaired colour vision.

``` r
# load the ochRe vignette
vignette("ochre")
```

Installation
------------

You can install `ochRe` from github with:

``` r
# You need to install the 'devtools' package first
devtools::install_github("ropenscilabs/ochRe")
```

The Palettes
------------

``` r
pal_names <- names(ochre_palettes)

par(mfrow=c(length(ochre_palettes)/2, 2), lheight = 2, mar=rep(1, 4), adj = 0)
for (i in 1:length(ochre_palettes)){
    viz_palette(ochre_palettes[[i]], pal_names[i])
}
```

![](README_files/figure-markdown_github-ascii_identifiers/see_palettes-1.png)

Example
-------

This is a basic example of how to use the `namatjira_qual` palette in a plot.

``` r
library(ochRe)
library(ggplot2)
ggplot(diamonds) + geom_bar(aes(x = cut, fill = clarity)) +
  scale_fill_ochre()
```

![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-2-1.png)

In this example we use the `winmar` palette directly via the `colorRampPalette()` function (for the base plot connoisseurs).

``` r
## basic example code
pal <- colorRampPalette(ochre_palettes[["winmar"]])
image(volcano, col = pal(20))
```

![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-3-1.png)

Individual palettes can be visualised using the viz\_palette function

``` r
viz_palette(ochre_palettes[["tasmania"]])
```

![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-4-1.png)
