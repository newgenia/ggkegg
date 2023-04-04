
<!-- README.md is generated from README.Rmd. Please edit that file -->

# ggkegg

## Installation

``` r
devtools::install_github("noriakis/ggkegg")
```

## Example

``` r
library(ggkegg)
library(ggfx)
ggkegg("hsa04130",
  convert_org = c("pathway","hsa","ko","compound"))+
  geom_node_rect()+
  geom_node_text(aes(label=converted_name,
                     filter=!undefined & converted_name!="STX8"),
                 size=2)+
  with_outer_glow(geom_node_text(aes(label=converted_name,
                                     filter=!undefined & converted_name=="STX8"),
                  size=3),
                  colour="white",
                  expand=3)+
  geom_edge_link(arrow = arrow(length = unit(1, 'mm')), 
                 end_cap = circle(5, 'mm'),
                 start_cap = circle(5, "mm"))
```

<img src="man/figures/README-unnamed-chunk-2-1.png" width="2400" style="display: block; margin: auto;" />
