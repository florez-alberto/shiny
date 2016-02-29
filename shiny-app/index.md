---
title       : Body Mass Index Application
subtitle    : Made for Developing Data Products - Coursera Course
author      : Alberto Florez
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

 

## Body Mass Index (BMI)  
  
* First published in 1972, its been the standard for body fat measure.
  
* Although not perfect, due to its simplicity its widely used and even recommended by the WHO since 1980.  
  
* The BMI is universally expressed in kg/m2, resulting from mass in kilograms and height in meters.  
  
* BMI ranges from underweight to obese and is commonly employed among children and adults to predict health outcomes. 



--- .class #id 


## Limitations  
* BMI is proportional to mass and inversely proportional to the square of the height.
* Taller individuals tend to have a higher BMI compared to the body fat level, and smaller individuals tend to have narrower normal weight frames.
* BMI categories are generally regarded as a satisfactory tool for measuring whether sedentary individuals are underweight, overweight or obese with various exceptions, such as: athletes, children, the elderly, and the infirm.

--- .class #id 


## Some information about the shiny app
* The shiny app is a very simple calculator provided with the function  
  

```r
BodyMass <- function(weight, height){
  weight/height^2
}
```
  
  
Also, with avery simple classifier to put given BMI into WHO categories  


```r
Categ <- function(x) {
  if (x <= 15) {
    print ("Very severely underweight")
  }
  if (15 < x & x <= 16){
    print ("severely underweight")
  }
  if(16 < x & x <= 18.5){
    print("underweight")
  }
  if (18.5< x & x<= 25){
    print ("Normal (healthy weight)")
    }
  if (25< x & x <= 30){
    print  ("overweight")
  }
  if (30< x & x <= 35){
    print  ("Obese Class I (Moderately obese)")
  }
  if (35< x & x <= 40){
    print  ("Obese Class II (Severely obese)")
  }
  if (40< x ){
    print  ("Obese Class III (Very severely obese)")
  }
  
}
```


--- .class #id 


## Example
  
  
The user inputs its height and weight (in meters and kilograms) and the BMI and category are automatically calculated by the app.


```r
example <- BodyMass (70, 1.70)
print(example)
```

```
## [1] 24.22145
```

```r
Categ(example)
```

```
## [1] "Normal (healthy weight)"
```

--- .class #id 




























