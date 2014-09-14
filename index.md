---
title       : Impact of Relocating
subtitle    : DDP Slidify Assignment
author      : Pramesh Rogbeer
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
### 1. The Application 

**APPLICATION** :     [DDPFinal](http://example.com/) located at https://pramesh.shinyapps.io/DDPFinal/

**OBJECTIVE**: Provide you with a few predictions on what to expect if you plan to emigrate.

**DATA** : The simulation is based on real data (2013) available at the [UNDP site](http://hdr.undp.org/en/data) 



- The UNDP collects data from all over the world to calculate and publish, annually, a ***Human Development Index*** (HDI) for each country. This index is a measure of human wellbeing for the country. Several independent indicators are to be found in this HDI index. 

- A select few of these indicators were retained for use in the [DDPFinal](http://example.com/) application.

- The [DDPFinal](http://example.com/) application "predicts" how, compared to now, your quality of life could improve/degrade if you emigrated elsewhere

- the results are provided in tabular and graphical forms


Have fun !!



--- .class #id 

### 2. The Logic

### INPUT:  
 At the user interface: (1) your `current location` (2) where you want to `emigrate` , and (3) your `gender`

### OUTPUT: 
The output gives you the % change ( +ve or -ve) in 12 different indicators.  
Computation is quite straighforward :

`Result for Indicator = (Value for Current Location - Value for Destination ) ` (%)

### RESULTS:
The results are presented in:

- a table (all values are in %)
- a histogram with values >0 (improvements) and <0 (loss in quality)




--- .class #id 

### 3. The coding
Some key points of the code : the full code is on my [github](https://github.com/Pramesh1/DDProd)  
(I set `echo=FALSE` to hide the code - it is too long)

I preset the input variables as follows:

```r
countryNow="Mauritius"
countryFuture="Germany"
gender="Male"
```


Output Result:
(Please take a look at the app on shiny.io to get an explanation of the result)


```
##     hdi.rank hdi.gii     hdi hdi.r    le    gni taxes   cpi     hom   sat
## 63      90.5   -87.7    18.4  -0.5 -11.4 -135.2  -2.8 -25.7     2.6  -1.2
## 631  BETTER!   Worse BETTER! Worse Worse  Worse Worse Worse BETTER! Worse
##      free   trust
## 63     -7      15
## 631 Worse BETTER!
```


--- .class #id 

### 4. CHALLENGES:

The `csv` data was loaded to a variable in the `server.R` file. But is was impossible to `dynamically`pass a list (countries listing) to the input part of the `ui.R`file. This problem could not be solved despite intensive search on the web.
I finally ended up building this list inside the `ui.R` file itself. 

Then there was the famous `UTF-8` encoding problem ... The app was not launching on the shiny server eben if it was working perfectly well on my laptop. After some search on the web, i found i had to save them all with `UTF-8`encoding. Once this done everything came back to normal.


I enjoyed thgis projcct quite a lot.


