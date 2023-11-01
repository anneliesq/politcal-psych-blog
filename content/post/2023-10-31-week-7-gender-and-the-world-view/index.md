---
title: 'Week 7: Gender and the World View'
author: "Annelies Quinton"
date: "2023-10-31"
output: pdf_document
categories: []
tags: []
slug: []
---

## Introduction:

This week's blog evaluates the impact of gender on political outcomes, specifically surrounding conflict and war. Through past weeks, I have introduced the idea of SDO (Social Dominance Theory) and evolutionary principles that carry to today's decisions. These ideas are significant with regard to gender. We see that women are typically more liberal than men (lower SDO scores). Further, due to different reproductive strategies, men have an evolved trait that males power, in this case through political careers, for desirable than compared to women. These discrepancies are evident across political representation: 26 out of197 world leaders are women and only 6% of countries have more than 50% women in their legislative body (partially due to gender quotas).

This blog is driven by Trager and Barnhart (2023)'s study. They consider whether gender contributes to a country's likelihood of initiating war with another country. I consider the likelihood of war over since the 1900s, the difference between woman's suffrage and woman's civil liberties as a predictor variable for polity score, and the geographic trends for woman's suffrage.

## Class Notes:

-   Why are women typically more liberal than men?

    -   Different reproductive strategies, men have more of a taste of hierarchy, and have an evolved trait that makes men more likely to seek power and political careers

    -   boys and girls are socialized differently: competitive sports

    -   influence of siblings:

-   systematic differences in political behavior:

    -   men are far more likely to hold political office than women

    -   men are on average more conservative

-   only 26/197 world leaders are women

    -   only 6 countries with more than 50% women (but could be due to quotas)

-   sexual selection leads to different selected pressures that demonstrates how and why women and men behave differently

    -   males have a taste for power

-   sources of deferentially socialized political behavior across genders:

    -   Household: parents and siblings

    -   sports: socialization reinforcing biology

-   Trager and Barnhart (2023): how women shape the politics of war

    -   women are more likely to engage in democratic peaceship

    -   "increasing levels of women suffrage = reduction conflict"

    -   "increasing democratic features without women has no impact on conflict likelihood"

    -   place with higher levels of political empowerment for women, gender gap is larger

## Section Notes:

-   interaction terms:
-   for question 6:
    -   init\~suffrage + polity + polity\*suffrage
        -   identify effect on polity for different suffrage
        -   compare between suffrage and civilliberties





## Introduction:



## Data:

The data utilized in this blog is country-level data, organized by county and year, from Trager and Barnhart (2023). There are a total of 9,865 entries, across 157 countries and spanning from 1990 to 2007. The primary variables of interest are `polity`, `suffrage`, `wcivillibs.`

| Variable Name     | Variable Description                                                                                                                    |
|--------------------------|----------------------------------------------|
| `ccode1`          | Unique country code                                                                                                                     |
| `country_name`    | Country name                                                                                                                            |
| `year`            | Year                                                                                                                                    |
| `init`            | The number of overall conflicts initiated by the country specified by `ccode1` during the year specified by `year`                      |
| `init_autoc`      | The number of overall conflicts initiated by the country specified by `ccode1` **with autocracies** during the year specified by `year` |
| `init_democ`      | The number of overall conflicts initiated by the country specified by `ccode1` **with democracies** during the year specified by `year` |
| `democracynosuff` | Indicator variable for a democracy without women's suffrage. 1 if the country is a democracy without women's suffrage, 0 otherwise.     |
| `polity`          | Polity democracy score for the country specified by `ccode1` during the year specified by `year`                                        |
| `suffrage`        | Indicator variable for a country with women's suffrage (Women have the right to vote AND Polity \> 1)                                   |
| `autocracy`       | Indicator variable for a country with an autocratic government (Polity \< 5)                                                            |
| `nuclear`         | Indicator variable for whether the country is a nuclear power                                                                           |
| `wcivillibs`      | Measure of the degree of civil liberty women enjoy, ranging from 0-1, where higher values mean women have more civil liberties          |

## Is War Common?

I first consider the aggregated number of wars initiated by each country each year. The histogram below shows the number of country's that initiated a certain number of wars. Each year is evaluated separately, indicating why the y value of count is nearly 8,000 for the 0 bar. It is evident that 0 is the highest frequency and 1 and 2 are the next highest peaks. From this graph, it is apparent that wars are relatively uncommon. However, this graph fails to show the total wars for a given country or the time-based trends that could be occurring.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-3-1.png" width="672" />
## When Does War Happen?
The histogram below shows the average number of wars per year. There are obvious spikes around the first and second world wars, significantly with World War II. However, after WW2, there does not appear to be an upward or downward trend, indicating war could be relatively stable and more peaceful. However, this does not consider the increasing number of countries over the years. 

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-4-1.png" width="672" />
## More Countries, More Wars?
The histogram below depicts the number of wars for a given year. There is an obvious upward trend in this count. This could be attributed to numerous factors including more countries and decolonization. Further, there is not an indicator for the intensity of conflict, meaning these results have some ambiguity as World War's are rated at the same degree as a less prominent conflict. 


<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-5-1.png" width="672" />



```
## 
## ====================================================================
##                                   Dependent variable:               
##                     ------------------------------------------------
##                                           init                      
##                               (1)                     (2)           
## --------------------------------------------------------------------
## polity                      -0.002                   -0.004         
##                             (0.002)                 (0.003)         
##                                                                     
## suffrage                    0.064*                                  
##                             (0.038)                                 
##                                                                     
## polity:suffrage            -0.011**                                 
##                             (0.005)                                 
##                                                                     
## wcivillibs                                         -0.182***        
##                                                     (0.035)         
##                                                                     
## polity:wcivillibs                                    0.008*         
##                                                     (0.004)         
##                                                                     
## Constant                   0.193***                 0.279***        
##                             (0.013)                 (0.021)         
##                                                                     
## --------------------------------------------------------------------
## Observations                 9,865                   9,223          
## R2                           0.002                   0.006          
## Adjusted R2                  0.002                   0.005          
## Residual Std. Error    0.659 (df = 9861)       0.673 (df = 9219)    
## F Statistic         8.132*** (df = 3; 9861) 17.075*** (df = 3; 9219)
## ====================================================================
## Note:                                    *p<0.1; **p<0.05; ***p<0.01
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-7-1.png" width="672" />
