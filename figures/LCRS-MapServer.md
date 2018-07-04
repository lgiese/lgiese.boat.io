Here should emerge a nice leaflet map.

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
library(mapview)
library(leaflet)
```


```{r, echo = FALSE, eval = TRUE, warning=FALSE}
m <- leaflet()
m <- addTiles(m)
m

```





