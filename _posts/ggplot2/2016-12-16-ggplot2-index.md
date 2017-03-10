---
title: ggplot2 Graphing Library | Plotly
permalink: ggplot2/
description: ggplot2 is a graphing library for R. Use ggplot2 with Plotly to create interactive, online ggplot2 charts with D3.js.
layout: langindex
language: ggplot2
---

<h1 class="centered">Plotly ggplot2 Library</h1>
<div class="row centered btnrow">
  <a href="/ggplot2/getting-started/" class="button no_underline">Getting Started</a>
  <a href="/ggplot2/user-guide/" class="button no_underline">User Guide</a>
</div>

<div>Plotly for ggplot2 is an interactive, browser-based charting library built on the open source javascript graphing library,
<a href="https://plot.ly/javascript" target="_blank">plotly.js</a>. It works entirely locally, through the <a href="http://www.htmlwidgets.org/" target="_blank">HTML widgets</a> framework.
</div>







```r
library(plotly)

dsamp <- diamonds[sample(nrow(diamonds), 1000), ]
p <- qplot(carat, price, data=dsamp, colour=clarity)

p <- ggplotly(p)

# Create a shareable link to your chart
# Set up API credentials: https://plot.ly/r/getting-started
chart_link = plotly_POST(p, filename="ggplot2/intro-1")
chart_link
```

<iframe src="https://plot.ly/~RPlotBot/4257.embed" width="800" height="600" id="igraph" scrolling="no" seamless="seamless" frameBorder="0"> </iframe>

<h6>Plotly graphs are interactive. Click on the legend entries to toggle traces, click and drag on the canvas to zoom, shift and click to pan.</h6>


```r
library(plotly)

set.seed(100)
d <- diamonds[sample(nrow(diamonds), 1000), ]

p <- ggplot(data = d, aes(x = carat, y = price)) +
geom_point(aes(text = paste("Clarity:", clarity)), size = .5) +
geom_smooth(aes(colour = cut, fill = cut)) + facet_wrap(~ cut)

p <- ggplotly(p)


# Create a shareable link to your chart
# Set up API credentials: https://plot.ly/r/getting-started
chart_link = plotly_POST(p, filename="ggplot2/intro-2")
chart_link
```

<iframe src="https://plot.ly/~RPlotBot/4259.embed" width="800" height="600" id="igraph" scrolling="no" seamless="seamless" frameBorder="0"> </iframe>

<div>
<p>
<code>ggplotly</code> works by <a href="https://plot.ly/ggplot2/user-guide">serializing ggplot2 figures into plotly's universal graph JSON</a>. See the <a href="http://ropensci.github.io/plotly/ggplot2/">ggplot2 ??? plotly test tables</a> for current ggplot2 conversion coverage. Submit issues or contribute on <a href="https://github.com/ropensci/plotly/issues">rOpenSci</a>.
</p></div>

<div>
<p>
Plotly's ggplot2 graphs are hosted online in <a href="https://plot.ly/plans">your plotly account</a> or <a href="https://plot.ly/r/offline">drawn locally in RStudio</a>. They can be embedded in <a href="https://plot.ly/r/dashboards">HTML pages</a>, <a href="https://plot.ly/r/knitr">Knitr documents</a>, or <a href="https://plot.ly/r/shiny-tutorial">Shiny apps</a>. You don't need to use ggplot2 to use Plotly with R, you can also use Plotly's native <a href="https://plot.ly/r/">R graphing library</a>.
</p>
</div>

{% assign languagelistimg = site.posts | where:"page_type":"example_index" | where:"language","ggplot2"  | where:"has_thumbnail",true | sort: "order"  %}
{% assign languagelist = site.posts | where:"page_type":"example_index" | where:"language","ggplot2" %}

{% include documentation_eg.html %}