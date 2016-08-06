---
title       : Old cars stop distance predictor
subtitle    : How the application works
author      : Eduardo Bortoluzzi Junior
job         : Data Science student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---




## Summary

The application predicts the stop distance of the car from its speed using
the [shiny](http://shiny.rstudio.com/) framework.

It creates the prediction model from the R dataset <font style="font-weight:bold;color:red;">cars</font>, 
which has 50 observations with 2 variables. The data 
in this dataset were recorded in 1920s, so, outdated but good for the framework
demonstration.

This cars dataset has the variable <font style="font-weight:bold;color:red;">speed</font> 
in <font style="font-style:italic;">mph</font> and the variable 
<font style="font-weight:bold;color:red;">distance</font> in
<font style="font-style:italic;">ft</font>, and the application allows the user
to choose the units he wants: metric or imperial.

The conversion between the units are done at the server side before doing the
prediction and at each time the units are changed.

The application can be accessed from the URL:

<https://eduardob.shinyapps.io/devdataprod-shiny/>

--- #center .center

## Application's screen

<div style='text-align: center;'>
    <img src='assets/img/app.png' />
</div>


---

## The cars dataset

The cars dataset has the distribution below:

<img src="assets/fig/unnamed-chunk-1-1.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />

---

## Linearizing the cars dataset

When doing a linear prediction model, the goal is to maximize the Adjusted
R-squared.


As seen on the previous slide, the dataset is not very linear. The adjusted 
r-squared from it is 0.6438102.


If the square root of the distance is used instead, the adjusted r-squared is 
improved to 0.7033592, so the prediction was done with
the square root of the distance.

<img src="assets/fig/unnamed-chunk-4-1.png" title="plot of chunk unnamed-chunk-4" alt="plot of chunk unnamed-chunk-4" style="display: block; margin: auto;" />
