---
title       : Log-Log Regression
subtitle    : Allometric, and other scaling
author      : Andrew Jackson
job         : Associate Professor
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax, bootstrap, quiz]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

--- &vcenter

## Still just linear regression
But now with log transformed data on the x and y axes




![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png) 


--- .class #id 

## Focus on length-mass relationships

- How does the mass of an organism scale with its length?
- Scaling is related to interesting biological and ecological processes
   - Metabolic costs
   - Transport of molecules over membranes
   - Predation or fishing / harvesting
   - Diet
   - Ecological scaling laws (abundance and biomass)

--- .class #id 

## Scaling of simple shapes

- How does a cube scale with its length?
- $Mass = Density * Volume$
- Assume density stays the same no matter what size, so $Mass \propto Volume$
- $Volume = L_1 * L_2 * L_3$
- $Volume = a * L ^ b$
- So if the cube stays the same shape (i.e. it remains a cube)
   - How does mass change if length is doubled?
   - $Volume = 2L_1 * 2L_2 * 2L_3 = 2 * L ^ 3$
- Isometric scaling is when the object stays the same shape as it grows or shrinks

--- &two-cols w1:58% w2:38%
## Spherical cows

*** {name: left}
> - How does mass of a sphere change with length?
> - $Volume = \frac{4}{3} * \pi * r ^ 3$
> - $Volume = \frac{4}{3} * \pi * \frac{L^3}{2^3} = \frac{4}{3*9} * \pi * L^3$
> - Again, $Volume$, and hence $Mass$ changes with $Length^3$
> - So, generally we have...
> - $Volume = (some ~ number) * L^3$
> - $Volume = a * L ^ b$
> - Where for isometric scaling of $Volume$ (or $Mass$) with $Length$, $b = 3$

*** {name: right}
<img src="assets/img/SphericalCow2.gif" href="https://commons.wikimedia.org/wiki/File:SphericalCow2.gif#/media/File:SphericalCow2.gif">

--- .class #id 

## A general equation for scaling of Mass to Length
> - $Mass = a * Length ^ b$
> - Take the Log of both sides (doesnt matter what logarithmic base)
> - $\log(M) = \log(a * L ^ 3)$
> - $\log(M) = \log(a) + \log(L^b)$
> - $\log(M) = \log(a) + b * \log(L)$
> - $Y = b_0 + b_1 * X$
> - where... $\log(a) = b_0$
> - so... $a = e^{b_0}$
> - and... $b_1 = b$ and is simply the power in the allometric equation

--- &two-cols w1:68% w2:28%

##  What do these coefficients mean? - Intercept

*** {name: left}

> - on a log-log scale what does the intercept mean?
> - $\log(M) = b_0 + b_1 * \log(L)$
> - the intercept is the coefficient, or multiplier of $Length$
> - $M = e^{b_0} * Length ^ b_1$
> - Recall that spheres and cubes only differ in their coefficients
> - $Volume_{cube} = [1] * L^3$
> - $Volume_{sphere} = [\frac{4}{3*9} * \pi] * L^3$
> - So, $b_0$, our intercept, which in the allometric equation is $e^{b_0}$ 
tells us that the shapes differ between two species, and in some ways might tell
us how

*** {name: right}

<img src="assets/img/cod-and-plaice.jpg">

--- .class #id 

##  What do these coefficients mean? - Slope
If the coefficient of $Length$ is exactly 3, then the fish are growing 
isometrically and staying exactly the same shape. that is their width and depth 
is growing in proportion to their length.

<img src="assets/img/cod-isometric.jpg">

--- .class #id 

##  What do these coefficients mean? - Slope
If the coefficient of $Length$ is less than 3, then the fish are putting on less 
mass than you would predict which means their width and/or depth is not 
increasing in proportion to their length and they are becoming thinner as they 
get longer.

<img src="assets/img/cod-thinner.jpg">

--- .class #id 

##  What do these coefficients mean? - Slope
If the coefficient of $Length$ is greater than 3, then the fish are putting on 
more mass than you would predict which means their width and/or depth is not 
increasing in proportion to their length and they are becoming broader as they 
get longer.

<img src="assets/img/cod-fatter.jpg">

--- &vcenter

##  Mass - Length scaling in Finnish Fish
![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3-1.png) 


--- &radio
## Question

With a scaling relationship of $Mass = 0.01 * Length ^ {3.15}$, is mass scaling:

1. Isometrically
2. _Faster_
3. Slower

*** .hint
Isometric scaling for mass which is directly proportional to volume would be to power 3

*** .explanation
3.15 is larger than 3, so these fish are putting on more mass for a given length as they get larger.

--- &two-cols w1:48% w2:48%
## Exactly how much of an increase?

*** {name: left}
> - This is just a linear equation
> - $\log_{10}(M) = -2.01 + 3.15 * \log_{10}(L)$
> - so a one unit increase in $\log_{10}(M)$ leads to a 3.15 unit increase 
in $\log_{10}(L)$
> - but these are in $\log_{10}$ units...


*** {name: right}

![plot of chunk unnamed-chunk-4](assets/fig/unnamed-chunk-4-1.png) 

--- &radio
## Question

If $\log_{10}(Mass)$ increases by one unit, how much does mass increase by?

1. + 10 grams
2. + 9 grams
3. _10 times larger_
4. 100 times larger

*** .hint
$10 = \log_{10}(1)$

*** .explanation
If we consider we have $y = \log_{10}(x)$ and add one $y$ then we have $y + 1 = 1 + \log_{10}(x)$ which is 
equal to $y + 1 = \log_{10}(10) + \log_{10}(x)$ which by applying the rule `log of product is sum of logs` 
gives us $y + 1 = \log_{10}(10 * x)$. So, a one unit increase in $y$ which reprents $\log_{10}(x)$ results in an increase in $x$ by a multiplication of 10. 

--- &two-cols w1:48% w2:48%
## Exactly how much of an increase?

*** {name: left}

> - $\log_{10}(M) = -2.01 + 3.15 * \log_{10}(L)$
> - so a one unit increase in $\log_{10}(M)$ leads to a 3.15 unit increase 
in $\log_{10}(L)$
> - which translates into: every 10-fold increase in $Length$ results in a 
$10^{3.15} = 1413$ proportional increase in $Mass$.
> - So $L \mapsto 10*L$ means 
$M \mapsto 10^{3.15} * M = 1413 * M$
> - or, which might make more sense in this scale of data, a 0.1 or 10% increase 
in $Length$ results in a $10^{0.315} = 2.1 \approx 2$ which is an  
approximate doubling in $Mass$


*** {name: right}

![plot of chunk unnamed-chunk-5](assets/fig/unnamed-chunk-5-1.png) 

--- &two-cols w1:18% w2:78%

## Brain - Body mass scatterplot  

This slide **should** have two columns of variable width 

*** {name: left}

- point 1
- point 2
- point 3

*** {name: right}

- point 4
- point 5
- point 6

```
