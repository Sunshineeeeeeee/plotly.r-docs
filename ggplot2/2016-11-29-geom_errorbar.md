---
name: geom_errorbar
permalink: ggplot2/geom_errorbar/
description: Examples of geom_errobar in R and ggplot2
layout: base
thumbnail: thumbnail/error-bar.jpg
language: ggplot2
page_type: example_index
display_as: statistics
order: 2
output:
  html_document:
    keep_md: true
---


### Basic Error Bar


```r
library(plotly)

df <- data.frame(x = 1:10,
                 y = 1:10,
                 ymin = (1:10) - runif(10),
                 ymax = (1:10) + runif(10),
                 xmin = (1:10) - runif(10),
                 xmax = (1:10) + runif(10))

p <- ggplot(data = df,aes(x = x,y = y)) + 
    geom_point() + 
    geom_errorbar(aes(ymin = ymin,ymax = ymax)) + 
    geom_errorbarh(aes(xmin = xmin,xmax = xmax))

fig <- ggplotly(p)

fig
```

<div id="htmlwidget-58af81f645beef4bf0a5" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-58af81f645beef4bf0a5">{"x":{"data":[{"x":[1,2,3,4,5,6,7,8,9,10],"y":[1,2,3,4,5,6,7,8,9,10],"text":["x:  1<br />y:  1","x:  2<br />y:  2","x:  3<br />y:  3","x:  4<br />y:  4","x:  5<br />y:  5","x:  6<br />y:  6","x:  7<br />y:  7","x:  8<br />y:  8","x:  9<br />y:  9","x: 10<br />y: 10"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"rgba(0,0,0,1)","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(0,0,0,1)"}},"hoveron":"points","showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[1,2,3,4,5,6,7,8,9,10],"y":[1,2,3,4,5,6,7,8,9,10],"text":["ymin: 0.04701585<br />ymax:  1.715026<br />x:  1<br />y:  1","ymin: 1.09288698<br />ymax:  2.985903<br />x:  2<br />y:  2","ymin: 2.14916122<br />ymax:  3.910597<br />x:  3<br />y:  3","ymin: 3.79489421<br />ymax:  4.725415<br />x:  4<br />y:  4","ymin: 4.51751928<br />ymax:  5.221503<br />x:  5<br />y:  5","ymin: 5.16768982<br />ymax:  6.217257<br />x:  6<br />y:  6","ymin: 6.20955853<br />ymax:  7.036026<br />x:  7<br />y:  7","ymin: 7.24306763<br />ymax:  8.606842<br />x:  8<br />y:  8","ymin: 8.12320470<br />ymax:  9.563651<br />x:  9<br />y:  9","ymin: 9.99529409<br />ymax: 10.987979<br />x: 10<br />y: 10"],"type":"scatter","mode":"lines","opacity":1,"line":{"color":"transparent"},"error_y":{"array":[0.715025511337444,0.985903028631583,0.910596688743681,0.725415027933195,0.221503012813628,0.217257420765236,0.0360261681489646,0.606841949746013,0.563651326810941,0.987979338504374],"arrayminus":[0.952984154457226,0.907113023800775,0.850838777143508,0.205105792498216,0.482480716425925,0.83231018204242,0.790441471384838,0.756932365940884,0.876795304240659,0.00470591313205659],"type":"data","width":17.5605015689995,"symmetric":false,"color":"rgba(0,0,0,1)"},"showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[1,2,3,4,5,6,7,8,9,10],"y":[1,2,3,4,5,6,7,8,9,10],"text":["xmin: 0.8092332<br />xmax:  1.468216<br />x:  1<br />y:  1","xmin: 1.1271521<br />xmax:  2.376137<br />x:  2<br />y:  2","xmin: 2.3721838<br />xmax:  3.152176<br />x:  3<br />y:  3","xmin: 3.8140853<br />xmax:  4.887586<br />x:  4<br />y:  4","xmin: 4.0992375<br />xmax:  5.952463<br />x:  5<br />y:  5","xmin: 5.5532663<br />xmax:  6.709155<br />x:  6<br />y:  6","xmin: 6.9441395<br />xmax:  7.049240<br />x:  7<br />y:  7","xmin: 7.9983755<br />xmax:  8.868216<br />x:  8<br />y:  8","xmin: 8.1702322<br />xmax:  9.367570<br />x:  9<br />y:  9","xmin: 9.1832534<br />xmax: 10.986645<br />x: 10<br />y: 10"],"type":"scatter","mode":"lines","opacity":1,"line":{"color":"transparent"},"error_x":{"array":[0.468215611530468,0.376136912964284,0.15217550797388,0.887585789896548,0.952462557237595,0.709155170014128,0.0492400911170989,0.868216076632962,0.367570340167731,0.986645363038406],"arrayminus":[0.190766756888479,0.872847944963723,0.627816166263074,0.185914746019989,0.900762544712052,0.44673366821371,0.0558605447877198,0.00162454484961927,0.829767777817324,0.816746585536748],"type":"data","width":11.9650422920528,"symmetric":false,"color":"rgba(0,0,0,1)"},"showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null}],"layout":{"margin":{"t":26.2283105022831,"r":7.30593607305936,"b":40.1826484018265,"l":31.4155251141553},"plot_bgcolor":"rgba(235,235,235,1)","paper_bgcolor":"rgba(255,255,255,1)","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[0.0281677318480797,11.5084776311903],"tickmode":"array","ticktext":["3","6","9"],"tickvals":[3,6,9],"categoryorder":"array","categoryarray":["3","6","9"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"y","title":{"text":"x","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"yaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[-0.500032329105306,11.5350275131525],"tickmode":"array","ticktext":["0","3","6","9"],"tickvals":[0,3,6,9],"categoryorder":"array","categoryarray":["0","3","6","9"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"x","title":{"text":"y","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"shapes":[{"type":"rect","fillcolor":null,"line":{"color":null,"width":0,"linetype":[]},"yref":"paper","xref":"paper","x0":0,"x1":1,"y0":0,"y1":1}],"showlegend":false,"legend":{"bgcolor":"rgba(255,255,255,1)","bordercolor":"transparent","borderwidth":1.88976377952756,"font":{"color":"rgba(0,0,0,1)","family":"","size":11.689497716895}},"hovermode":"closest","barmode":"relative"},"config":{"doubleClick":"reset","showSendToCloud":false},"source":"A","attrs":{"506e92510d":{"x":{},"y":{},"type":"scatter"},"506e46b23d9c":{"ymin":{},"ymax":{},"x":{},"y":{}},"506e73ceb410":{"xmin":{},"xmax":{},"x":{},"y":{}}},"cur_data":"506e92510d","visdat":{"506e92510d":["function (y) ","x"],"506e46b23d9c":["function (y) ","x"],"506e73ceb410":["function (y) ","x"]},"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>

### Margin Error Bar


```r
library(plotly)

population <- data.frame(Year=seq(1790, 1970, length.out=length(uspop)), 
                         Population=uspop, 
                         Error=rnorm(length(uspop), 5))

library(ggplot2)
p <- ggplot(population, aes(x=Year, y=Population, 
                       ymin=Population-Error, ymax=Population+Error))+
  geom_line()+
  geom_point(pch=2)+
  geom_errorbar(width=0.9)

fig <- ggplotly(p)

fig
```

<div id="htmlwidget-1ff3012710c032d0739b" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-1ff3012710c032d0739b">{"x":{"data":[{"x":[1790,1800,1810,1820,1830,1840,1850,1860,1870,1880,1890,1900,1910,1920,1930,1940,1950,1960,1970],"y":[3.93,5.31,7.24,9.64,12.9,17.1,23.2,31.4,39.8,50.2,62.9,76,92,105.7,122.8,131.7,151.3,179.3,203.2],"text":["Year: 1790<br />Population:   3.93<br />Population - Error:  -0.03263009<br />Population + Error:   7.89263","Year: 1800<br />Population:   5.31<br />Population - Error:   0.13773535<br />Population + Error:  10.48226","Year: 1810<br />Population:   7.24<br />Population - Error:   1.82419508<br />Population + Error:  12.65580","Year: 1820<br />Population:   9.64<br />Population - Error:   3.79647140<br />Population + Error:  15.48353","Year: 1830<br />Population:  12.90<br />Population - Error:   8.01835483<br />Population + Error:  17.78165","Year: 1840<br />Population:  17.10<br />Population - Error:  12.01056354<br />Population + Error:  22.18944","Year: 1850<br />Population:  23.20<br />Population - Error:  16.97004299<br />Population + Error:  29.42996","Year: 1860<br />Population:  31.40<br />Population - Error:  26.12166216<br />Population + Error:  36.67834","Year: 1870<br />Population:  39.80<br />Population - Error:  34.93557059<br />Population + Error:  44.66443","Year: 1880<br />Population:  50.20<br />Population - Error:  45.01834609<br />Population + Error:  55.38165","Year: 1890<br />Population:  62.90<br />Population - Error:  57.45381451<br />Population + Error:  68.34619","Year: 1900<br />Population:  76.00<br />Population - Error:  70.91997473<br />Population + Error:  81.08003","Year: 1910<br />Population:  92.00<br />Population - Error:  85.25874109<br />Population + Error:  98.74126","Year: 1920<br />Population: 105.70<br />Population - Error:  98.83444859<br />Population + Error: 112.56555","Year: 1930<br />Population: 122.80<br />Population - Error: 117.87305497<br />Population + Error: 127.72695","Year: 1940<br />Population: 131.70<br />Population - Error: 126.20288406<br />Population + Error: 137.19712","Year: 1950<br />Population: 151.30<br />Population - Error: 146.10788769<br />Population + Error: 156.49211","Year: 1960<br />Population: 179.30<br />Population - Error: 173.08505419<br />Population + Error: 185.51495","Year: 1970<br />Population: 203.20<br />Population - Error: 197.42180290<br />Population + Error: 208.97820"],"type":"scatter","mode":"lines+markers","line":{"width":1.88976377952756,"color":"transparent","dash":"solid"},"hoveron":"points","showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","marker":{"autocolorscale":false,"color":"rgba(0,0,0,1)","opacity":1,"size":5.66929133858268,"symbol":"triangle-up-open","line":{"width":1.88976377952756,"color":"rgba(0,0,0,1)"}},"opacity":1,"error_y":{"array":[3.96263009077538,5.17226464558962,5.41580491783526,5.84352859814523,4.88164517003112,5.08943645961059,6.22995700858238,5.27833784441223,4.86442941371253,5.18165390670018,5.44618548790198,5.08002526770123,6.74125891069239,6.86555140733623,4.92694502958354,5.49711594114785,5.19211230716283,6.21494581377243,5.7781970970095],"arrayminus":[3.96263009077538,5.17226464558962,5.41580491783526,5.84352859814523,4.88164517003112,5.08943645961059,6.22995700858238,5.27833784441224,4.86442941371253,5.18165390670018,5.44618548790198,5.08002526770123,6.74125891069239,6.86555140733623,4.92694502958354,5.49711594114785,5.19211230716283,6.21494581377243,5.7781970970095],"type":"data","width":1.01311623699693,"symmetric":false,"color":"rgba(0,0,0,1)"},"frame":null}],"layout":{"margin":{"t":26.2283105022831,"r":7.30593607305936,"b":40.1826484018265,"l":43.1050228310502},"plot_bgcolor":"rgba(235,235,235,1)","paper_bgcolor":"rgba(255,255,255,1)","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[1780.505,1979.495],"tickmode":"array","ticktext":["1800","1850","1900","1950"],"tickvals":[1800,1850,1900,1950],"categoryorder":"array","categoryarray":["1800","1850","1900","1950"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"y","title":{"text":"Year","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"yaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[-10.4831714501646,219.428738456399],"tickmode":"array","ticktext":["0","50","100","150","200"],"tickvals":[0,50,100,150,200],"categoryorder":"array","categoryarray":["0","50","100","150","200"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"x","title":{"text":"Population","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"shapes":[{"type":"rect","fillcolor":null,"line":{"color":null,"width":0,"linetype":[]},"yref":"paper","xref":"paper","x0":0,"x1":1,"y0":0,"y1":1}],"showlegend":false,"legend":{"bgcolor":"rgba(255,255,255,1)","bordercolor":"transparent","borderwidth":1.88976377952756,"font":{"color":"rgba(0,0,0,1)","family":"","size":11.689497716895}},"hovermode":"closest","barmode":"relative"},"config":{"doubleClick":"reset","showSendToCloud":false},"source":"A","attrs":{"506e1ce0e289":{"x":{},"y":{},"ymin":{},"ymax":{},"type":"scatter"},"506eb0c86cd":{"x":{},"y":{},"ymin":{},"ymax":{}},"506e559e24dd":{"x":{},"y":{},"ymin":{},"ymax":{}}},"cur_data":"506e1ce0e289","visdat":{"506e1ce0e289":["function (y) ","x"],"506eb0c86cd":["function (y) ","x"],"506e559e24dd":["function (y) ","x"]},"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>

### What About Dash?

[Dash for R](https://dashr.plot.ly/) is an open-source framework for building analytical applications, with no Javascript required, and it is tightly integrated with the Plotly graphing library. 

Learn about how to install Dash for R at https://dashr.plot.ly/installation.

Everywhere in this page that you see `fig`, you can display the same figure in a Dash for R application by passing it to the `figure` argument of the [`Graph` component](https://dashr.plot.ly/dash-core-components/graph) from the built-in `dashCoreComponents` package like this:


```r
library(plotly)

fig <- plot_ly() 
# fig <- fig %>% add_trace( ... )
# fig <- fig %>% layout( ... ) 

library(dash)
library(dashCoreComponents)
library(dashHtmlComponents)

app <- Dash$new()
app$layout(
    htmlDiv(
        list(
            dccGraph(figure=fig) 
        )
     )
)

app$run_server(debug=TRUE, dev_tools_hot_reload=FALSE)
```
