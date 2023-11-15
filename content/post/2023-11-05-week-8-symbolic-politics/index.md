---
title: 'Week 8: Symbolic Politics'
author: Annelies Quinton
date: '2023-11-05'
slug: []
categories: []
tags: []
---



## Introduction:

This week's blog post evaluates the presence of symbolic attitudes in the political sphere. Symbolic attitudes can be described as stable, constrained, and influential toward other people and objects (have power). One application of symbolic attitudes can be seen by Reny and Newman (2021), in which they evaluate how symbolic predispositions impact people's reactions to the George Floyd protests. Specifically, the authors consider police favorability and people's perception toward Black Americans.

In this blog, I replicate some of the findings by Reny and Newman (2021), specifically how perceptions toward police and Black Americans before and after the killing of George Floyd change based on different racial groups. Further, I consider the predictive power of political ideology and the date for various model types.

## Data:

The data utilized in this blog is from Reny and Newman (2021). They "exploit" a survey already "in the field", including when the murder of George Floyd occurred. The survey was a weekly survey assessing individuals ideologies and beliefs toward certain topics, including police favorability and one's perception of the level of discrimination in U.S faced by Black Americans. The data spans 419 days, from July 18th, 2019 to September 9th, 2020. The data includes 378,507 entries.

A list of key variables utilized in this blog can be found below:

| Variable Name                   | Variable Description                                                                                                                                                                           |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `race_ethnicity`                | Race or ethnicity. Levels labelled in data: 1-White, 2-Black or AfAm, 3-American Indian or Alaskan Native, 4 through 14- Asian or Pacific Islander (details in labels), and 15-Some other race |
| `hispanic`                      | Of Hispanic, Latino, or Spanish origin. Levels labelled in data: 1-Not Hispanic, 2-15 Hispanic of various origins                                                                              |
| `day_running`                   | Day relative to onset of George Floyd protests (day 0)                                                                                                                                         |
| `pid7`                          | Party identification on a seven point scale with strong, weak, lean: 1-Strong Democrat to 7-Strong Republican with 4-Independent.                                                              |
| `group_favorability_the_police` | Favorability towards the police: 1-Very favorable, 2-Somewhat favorable, 3-Somewhat unfavorable, 4-Very unfavorable                                                                            |
| `discrimination_blacks`         | Perceptions of the level of discrimination in US faced by Blacks: 1-None at all, 2-A little, 3-A moderate amount, 4-A lot, 5-A great deal                                                      |
| `day`                           | The date the respondent took the survey                                                                                                                                                        |
| `before`                        | indicator variable for the date relative to the killing of George Floyd (1= before, 0 = after)                                                                                                 |

## Comparison in Averages:

First, I consider how police favorability and perception of Black Americans changes, an average, before and after the killing of George Floyd. I perform a t-test to assess this difference. For each of the variables, I consider the average favorability for the variable, conditioned on before or after the killing.

### Police:

The results below show the difference in average favorability toward police before the killing of George Floyd and after. From these results we see there is a significant decline in favorability after the killing. This is due to the small p-value and the confidence interval not including zero, allowing us to reject the null hypothesis that there was no relationship between the murder and change in favorability. Looking directly at the means, the mean of x (before the killing) is smaller than the mean of y (after the killing). Favorability of police is coded on a 1-4 scale in which 1 is very favorable and 4 is very unfavorable. Therefore, a postive difference in \~0.15 means that on average, police favoriability decreased by \~0.15.





![](images/Screen%20Shot%202023-11-05%20at%205.31.13%20PM.png)

### Perception of Discrimination Faced By Black Americans

Similar to police favorability, we can assess the average perception of discrimination faced by Black Americans. The results show there was a significant increase in perception of discrimination due to the confidence interval not including zero and a small p-value (reject null hypothesis). The means show that, on average, perception of discrimination increased by \~0.14 before and after the killing of George Floyd. This is because discrimination is coded on a 1-5 scale, in which higher numbers are associated with higher levels of discrimination.



![](images/Screen%20Shot%202023-11-05%20at%205.32.46%20PM.png)

## Replication of Reny and Newman (2021):

After considering how these perceptions changed on average, I next consider these trends based on racial groups. The graphs below replicate the regression discontinuity design visualization created by Reny and Newman (2021).

For each racial group indentified in the survey (Non-Hispanic White, Asian Americans, Black Americans, Lationos, and other races), I have plotted the average rating (perception or favorability) for each day and shown the overall trend line. I create a separate trend line for before the killing and after, denoted by the dashed line at day 0 (killing of George Floyd).





<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-5-1.png" width="672" />

### Perception of Discrimination Faced by Black Americans

In the the left column, we see the perception of discrimination faced by Black Americans. For all groups, there is a significant jump at the threshold (day 0), indicating a higher level of perception of discrimination. However, we can see that this is more significant for certain groups. Specifically, this appears the least apparent for Black Americans. Black Americans already had the highest level of perception before the killing than any other racial group. From these graphs we also see that after the killing, there is a spike, but by 100 days after, the levels appear to return to baseline. This means that the killing created immediate change, but not necessarily lasting change in perceptions.

### Favorability Toward the Police

In the right column, favorability of the police is graphed for each racial group. Similar to the left column, for all racial groups there is a significant jump at the threshold, indicating a decrease in favorability of police. Like the left column, Black Americans started out with the highest level of unfavorability, but they also appear to have one of the higher spikes at the threshold. Prior to the threshold, each racial groups appears to have relatively stable attitudes toward police and like the left column, the spike at the threshold soon returns back to the baseline.

## Modeling Favorability:

In this section of the blog, I attempt to model the two outcome variables (`group_favorability_the_police` and `discrimination_blacks` from two predictor variables: political ideology and an indicator variable for the day (before =1, after = 0).

For each outcome variable, I consider two model types: linear and logit models.

## Probit Vs. Regression:

OLS models work best for continuous outcome variables, whereas probit models are effective when the outcome variable is categorical. Unlike using least squared in OLS regression, a probit model uses Maximum Likelihood Estimation to predict the parameters. An ordered probit model is effective when the response variable is categorical and ordered. This means the values have an obvious order.

For this blog, I use the response variable of `group_favorability_the_police`. As shown above, this variable takes values between 1-4, where 1 is very favorable and 4 is very unfavorable. Further, although this variable is ordinal, the difference between each level is not the same. Very favorable to somewhat favorable is less than somewhat favorable to somewhat unfavorable. For these reasons, an ordered probit model appears more appropriate for the given response variable.

### Police favorability:

#### Linear Regression

Theregression output belowdisplays the regression results for favorability of the police. Both variables are significant at the 95% confidence level. Further, both variables are negative. This that for a one unit increase in each variable, police favorability will decrease on the scale, but increase overall because lower values are associated with higher levels of favorability.

**Political Ideology:** as political ideology increases by 1 unit (become more republican), holding data constant, police favorability decreases by 0.214 units (become more favorable).

**Indicator Variable:** for dates before the killing, police favorability was 0.157 lower (become more favorable) than after the killing, holding political ideology constant.


<table style="text-align:center"><caption><strong>Regression Results</strong></caption>
<tr><td colspan="2" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"></td><td><em>Dependent variable:</em></td></tr>
<tr><td></td><td colspan="1" style="border-bottom: 1px solid black"></td></tr>
<tr><td style="text-align:left"></td><td>Police Favorability</td></tr>
<tr><td colspan="2" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">Political Ideology</td><td>-0.127<sup>***</sup></td></tr>
<tr><td style="text-align:left"></td><td>(0.001)</td></tr>
<tr><td style="text-align:left"></td><td></td></tr>
<tr><td style="text-align:left">Indicator for Date</td><td>-0.169<sup>***</sup></td></tr>
<tr><td style="text-align:left"></td><td>(0.004)</td></tr>
<tr><td style="text-align:left"></td><td></td></tr>
<tr><td style="text-align:left">Constant</td><td>2.646<sup>***</sup></td></tr>
<tr><td style="text-align:left"></td><td>(0.004)</td></tr>
<tr><td style="text-align:left"></td><td></td></tr>
<tr><td colspan="2" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">Observations</td><td>326,797</td></tr>
<tr><td style="text-align:left">R<sup>2</sup></td><td>0.088</td></tr>
<tr><td style="text-align:left">Adjusted R<sup>2</sup></td><td>0.088</td></tr>
<tr><td colspan="2" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"><em>Note:</em></td><td style="text-align:right"><sup>*</sup>p<0.1; <sup>**</sup>p<0.05; <sup>***</sup>p<0.01</td></tr>
</table>

#### Probit

Probit models are helpful when there is an ordinal bounded response variable (such as with police favorability)

**Political Ideology**: As political ideology increases by 1 unit (become more republican), holding date constant, police favorability decreases in log odds by 0.179 units (become more favorable). This is slightly lower than what the linear

**Date**: For dates after the killing, police favorability was log odds 0.002 lower (become more favorable) for each unit increase in days, holding ideology constant. That means that as days progressed, police became more favorable.

The intercepts are the expected odds when other variables are zero. For example, the very favorable \|\
somewhat favorable intercept (1\|2) is -1.234. This is the expected log-odds of having a "very favorable" attitude towards the police, when other variables are zero.



![](images/Screen%20Shot%202023-11-07%20at%2012.54.39%20PM.png){width="457"}

## Interpretation:

This blog utilized the data in Reny and Newman (2021) to evaluate perceptions toward Black Americans and favorability toward the police after the killing of George Floyd. In the section section ("Replicaiton of Reny and Newman (2021)"), I recreate the regression discontinuity in time figures. Similar to Reny and Newman who find a "ubiquitous shift in public attitudes" after the killing of George Floyd, the data shows for all races, this event caused police favorability to decrease and perception of Black Discrimination to increase. With regard to symbolic politics, we would expect little change before and after the killing of George Floyd, indicating these beliefs are constant and powerful, regardless of the environment. Although this appears to contradict Reny and Newman's theory of symbolic politics, their theory actually involves the consideration of partisanship.

This additional aspect of the theory, partisanship, is described by the charts below in addition to high and low prejudice respondents and strong democrats and republicans. Among these groups, Reny and Newman found that for high predjudice and strong republicans, symbolic politics was present. The graphs below, taken from Reny and Newman (2021), illustrate that there is little change before and after the killing for these two groups. To assess prejudice, Reny and Newman consider two indicators: "a Black--White favorability differential, which subtracts Black from white favorability Likert scales, and the 'generations' item from the well-known racial resentment scale." These results make sense intuitively because those who hold strong opinions are less likely to be swayed by an event or protest. The difference between strong republicans and strong democrats is interesting to me, but I think SDO has relevance to this difference. In past weeks, we found that republicans exhibit higher levels of SDO and are less open to new experiences than democrats. I think this degree of openness is reflected as strong democrats are being swayed by the event but not strong republicans.

![](images/Screen%20Shot%202023-11-07%20at%209.08.24%20PM.png){width="203"}

## Implications

These results illustrate how instigating change is extremely difficult, especially when the target audience is highly prejudiced and holding symbolic attitudes. These protests lasted months, involved thousands of individuals, and garnered world-wide attention and, yet, little difference in opinion is reflected. These findings show that high levels of conservatism and high prejudiced individuals exhibit high degrees of symbolic attitudes. In class we discussed how symbolic attitudes are introduced at young ages and reinforced thorughout life. If we consider symbolic politics to be harmful because of their inability to adapt to the world, reducing this crystallization of beliefs at a young age could reduce this tendency. Areas such as lessons in early in education that reduce racial biases is one place to start.

## References:

Reny, T. T. and Newman, B. J. (2021). The Opinion-Mobilizing Effect of Social Protest against Police Violence: Evidence from the 2020 George Floyd Protests. American Political Science Review, pages 1--9.
