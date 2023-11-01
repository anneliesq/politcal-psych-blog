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

## Suffrage and Initating Conflict

After considering the trends of war, I now bring gender into the equation. The histograms below show the proportion of wars initiated in a year. The y-axis is the density. For the no-suffrage graph, the graph peaks at ten wars per year, whereas for the suffrage graph, the peak is at 5 wars. This means there is a possible associations between woman's suffrage and fewer wars in a year.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-6-1.png" width="672" />

## Modeling Conflict:

I know consider if number of wars initiated can be modeled through polity scores and a variable relating to women in society: suffrage or civil liberties. In both models, I consider an interaction term between the women variable and polity. This accounts for heterogeneous effects. For example, what is the effect of having suffrage versus no suffrage.


<table style="text-align:center"><caption><strong>Regresion Results</strong></caption>
<tr><td colspan="4" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"></td><td colspan="3"><em>Dependent variable:</em></td></tr>
<tr><td></td><td colspan="3" style="border-bottom: 1px solid black"></td></tr>
<tr><td style="text-align:left"></td><td colspan="3">Wars Initiated</td></tr>
<tr><td style="text-align:left"></td><td>(1)</td><td>(2)</td><td>(3)</td></tr>
<tr><td colspan="4" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">Polity</td><td>-0.004<sup>**</sup></td><td>-0.002</td><td>-0.004</td></tr>
<tr><td style="text-align:left"></td><td>(0.002)</td><td>(0.002)</td><td>(0.003)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Suffrage</td><td>0.0001</td><td>0.064<sup>*</sup></td><td></td></tr>
<tr><td style="text-align:left"></td><td>(0.026)</td><td>(0.038)</td><td></td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Polity:Suffrage</td><td></td><td>-0.011<sup>**</sup></td><td></td></tr>
<tr><td style="text-align:left"></td><td></td><td>(0.005)</td><td></td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Woman Civil Libs.</td><td></td><td></td><td>-0.182<sup>***</sup></td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td>(0.035)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Polity:Woman Civil Libs.</td><td></td><td></td><td>0.008<sup>*</sup></td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td>(0.004)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Constant</td><td>0.185<sup>***</sup></td><td>0.193<sup>***</sup></td><td>0.279<sup>***</sup></td></tr>
<tr><td style="text-align:left"></td><td>(0.012)</td><td>(0.013)</td><td>(0.021)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td></tr>
<tr><td colspan="4" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">Observations</td><td>9,865</td><td>9,865</td><td>9,223</td></tr>
<tr><td style="text-align:left">R<sup>2</sup></td><td>0.002</td><td>0.002</td><td>0.006</td></tr>
<tr><td style="text-align:left">Adjusted R<sup>2</sup></td><td>0.002</td><td>0.002</td><td>0.005</td></tr>
<tr><td colspan="4" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"><em>Note:</em></td><td colspan="3" style="text-align:right"><sup>*</sup>p<0.1; <sup>**</sup>p<0.05; <sup>***</sup>p<0.01</td></tr>
</table>

## Suffrage (No interaction term)

The first model I have fitted  wars initiated as the outcome variable and `polity` and `suffrage` as the predictor variables. The adjusted R\^2 value is .002, which is incredibly low, indicating this is a very poor model. However, looking at the coefficients:

-   Polity has a value of -0.004, meaning for every 1 unit increase in polity wars decrease by .004 (higher polity, less wars)

-   Suffrage has a value of 0.0001, meaning that when suffrage is present wars increase by .0001.


## Suffrage (Interaction term)
The second model I have fitted has wars initiated as the outcome variable and `polity` and `suffrage` as the predictor variables, with an interaction term. Like the first model, the adjusted R\^2 value is .002, which is incredibly low. Looking at the coefficients:

-   Polity has a value of -0.002, meaning for every 1 unit increase in polity wars decrease by .002 (higher polity, less wars)

-   Suffrage has a value of 0.064, meaning that when suffrage is present wars increase by .064.

-   Suffrage and Polity has a negative value of -0.011, measuring the effect that polity and suffrage have on each other. For a one unit increase in polity and when suffrage is present, wars initated decreases by an additional -0.011.

Therefore, polity decreases wars, especially when suffrage is present.
In comparison to the first model, polity decreased in magnitude but suffrage increased. This means the inclusion of the interaction term helped distinguish the impacts of suffrage on polity.

### Women Civil Liberty

The second model is fitted the same way as the first, about suffrage is replaced with women's civil liberties. The adjusted R\^2 is slightly higher, but still incredibly low. Evaluating the coefficients:

-   Polity has a value of negative 0.004, slightly higher in magnitude than the first model.

-   Woman's Civil Liberties has a value of 0.008, meaning that when civil liberties are present, wars increase by 0.008.

-   Woman's Civil Liberties and Polity has a negative value of -0.279, measuring the effect that polity and Woman's Civil Liberties have on each other. For a one unit increase in polity and woman's civil liberties, wars initiated decreases by an additional -0.279 units.

Therefore, polity decreases wars, especially when woman's civil liberties are high.

Comparing the models, woman's civil liberties appears to have a higher value coefficient, indicating there is more of an effect when using it as a predictor than just suffrage.

## Predicting Conflict:
The graph below shows the predicted number of conflicts initiated per year, depending on whether suffrage was present in democracies. These graphs visualize the regression results from the first model above.  For both graphs, as polity increases, wars decrease. This is most drastic for suffrage democracies and non-suffrage democracies. 
<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-8-1.png" width="672" />

## Discussion:
The results above have shown that countries with higher polity scores (more democratic) initiate less war, especially when women are granted suffrage. However, it is also evident that woman, holding polity constant, correspond to an increase in wars initiated. Trager and Barnhart discuss a similar dilemma. They claim: “Countries that elect women to the legislature are more peaceful, but women legislators in those countries do not appear to be more peaceful than men in those countries” (126). This is seen through the data because democracies with women are more peaceful than democracies without women, but suffrage alone has a negative relationship to peace. This negative relationship could be part of the analysis for women are more extreme than males. 

The contradiction between suffrage in democracies being more peaceful and women as more extremes  has been dubbed the "leadership paradox", in which women leaders lean to more extremes than their male counterparts. How to reconcile this dilemma is difficult as it generally desired for women to be involved in politics, but peace is also a desirable political outcome. Although the extreme is present, it could be argued that women lean towards extremes because they are generally the minority gender in politics and face higher levels of scrutiny. Making hard and direct decisions may be necessary to prove competence to constituents, more so than for men. Gender quotas could serve as a way to increase women in office and possibly reduce the gender bias in politics. However, this comes with significant trade-offs as quotas can go against the ideals of direct-democracy by limiting a voter's choice in whom they can vote for. 

Another option is to take a wider perspective and consider the impact of having more democracies worldwide. Trager and Barnhart update the Democratic Peace Theory (democratic countries are less likley to go to war against other democratic countries) to "Democracies with women’s
suffrage are less likely to go to war with other democracies, but democracies without women’s suffrage are not" (Section 7, slide 20). This means that increasing woman's suffrage and democracies globally can reduce peace. This offers a more idealist solution, as forcing democracies on countries has many ethical consequences and would likely instigate war!

Overall, leadership paradox offers an interesting commentary on impacts of women in power, but I do not believe it is a reason to fear women in power. Returning to SDO and the evolutionary aspects of gender, there is a greater reason to believe the environment, not women, are responsible for this divergence in behavior. Creating a more inclusive space in politics is a good way to start ameliorating the impact of the leadership paradox. 

## References
Trager, R. F. and Barnhart, J. N. (2023). The Suffragist Peace: How Women Shape the Politics of War. Oxford University Press, New York. (Chapters 1–6).
