---
title: 'Week 5: The Political Psychology of Trump Indictment'
author: Annelies Quinton
date: '2023-10-17'
slug: []
categories: []
tags: []
---





## Introduction:

This week's blog post considers the public opinion around the Trump indictments. Former President Trump was charged with 91 crimes, two being federal indictments, one in New York, and one in Georgia. These indictments have significance in two ways: he is the first former President to be charged with state or federal crimes, and these trials will be ongoing during the presidential campaign (Lecture (10/11), slide 5).

In this blog, I consider two behaviors voters can express.

-   **Constraint**: the extent to which peoples' opinions are correlated with each other

-   **Consistency**: the extent to which peoples' opinions on the same issues vary

The question driving this blog is whether people have constrained opinion about Trump and his indictment across survey measures? I will also consider how demographics play into whether constraint is present.

## Data:

The data used in this blog is a cleaned version of the raw survey data stored in Roper Center iPoll Archive. The full data and documentation for the last wave are available [here](https://ropercenter.cornell.edu/ipoll/study/31120497).

The data spans three waves: June 9-10, Aug 2-3, Aug 15-16.

The data includes categorical variables on various politically charged questions, relating to the topic of the indictment. The variables attempt to assess the individual's opinion toward the indictment and the strength of their opinion.

The survey also includes demographic data, such as race, gender, income, and education.

A full list of the variables and their descriptions can be found below:

| Variable Name            | Variable Description                                                                                                                                                                                                                                                                            |
|---------------------------|---------------------------------------------|
| `id`                     | Unique respondent ID                                                                                                                                                                                                                                                                            |
| `wave`                   | Survey wave (1 \~ 3)                                                                                                                                                                                                                                                                            |
| `date`                   | Survey date (June 9-10, Aug 2-3, Aug 15-16)                                                                                                                                                                                                                                                     |
| `fav_trump`              | "Overall, do you have a favorable or unfavorable impression of Trump?" (Favorable, Unfavorable, No opinion, Don't know, Skipped)                                                                                                                                                                |
| `fav_biden`              | "Overall, do you have a favorable or unfavorable impression of Biden?" (Favorable, Unfavorable, No opinion, Don't know, Skipped)                                                                                                                                                                |
| `indictment`             | Each wave of surveys asked respondents' opinion about a different Trump indictment. The `indictment` variable shows the sentence that the wave used to describe the indictment.                                                                                                                 |
| `charge_serious`         | "Do you think the charges against Donald Trump in this case are" (Very serious, Somewhat serious, Not too serious, Not serious at all, Don't know, Skipped)                                                                                                                                     |
| `should_be_charged`      | "Do you think Donald Trump should or should not have been charged with a crime in this case?" (Should, Should not, Don't know, Skipped)                                                                                                                                                         |
| `politically_motivated`  | "Do you think the charges against Donald Trump in this case are politically motivated, or not?" (Yes, No, Don't know, Skipped)                                                                                                                                                                  |
| `suspend_campaign`       | "Do you think Donald Trump should or should not suspend his presidential campaign because of this indictment?" (Should, Should not, Don't know, Skipped)                                                                                                                                        |
| `doj_hunter_nonpartisan` | "On another subject, how confident are you that the U.S. Justice Department is handling its investigation of Hunter Biden in a fair and nonpartisan manner?" (Very confident, Somewhat confident, Not so confident, Not confident at all, Don't know, Skipped) (asked only in the wave 2 and 3) |
| `impeach_biden_hunter`   | "Do you think the U.S. House of Representatives should or should not start an impeachment inquiry into Joe Biden related to business deals his son Hunter Biden had in China and Ukraine?" (Should, Should not, Don't know, Skipped) (asked only in the wave 2)                                 |
| `PID`                    | Self-reported party identification (A Democrat, A Republican, An Independent, Something else, Skipped)                                                                                                                                                                                          |
| `age4`                   | Categorical variable indicating age (4 Categories)                                                                                                                                                                                                                                              |
| `educ5`                  | Categorical variable indicating educational attainment                                                                                                                                                                                                                                          |
| `gender`                 | Binary variable for gender                                                                                                                                                                                                                                                                      |
| `inc7`                   | Categorical variable indicating income level (7 Categories)                                                                                                                                                                                                                                     |
| `race`                   | Respondent's self-identified race (available only in the wave                                                                                                                                                                                                                                   |

## Defining Constraint

In order to empirically assess constraint, it is necessary to define constraint in theoretical terms, relating to one's opinion about Trump and his indictment.

The theoretical definition is whether an individual holds the same opinion on whether the charges are serious and if he should be charged. These questions correspond to each other, so similarity means constraint.

The method I chose to calculate constraint is through creating two binary variables (`charge_serious_binary` and `should_be_charged_binary`) and taking the average of these scores for each entry. `charge_serious_binary` is `1` if the existing charge_serious variable is either "Not too serious" or "Not serious at all" and `0` for "Somewhat serious" and "Very serious"). `should_be_charged_binary` is `1` for when the existing variable `should_be_charged` is "Should not" and `0` for "Should". By taking the mean of these values, an individual will either score a 0, 0.5, or 1.

### What do these scores mean:

-   Constraint of `0` or `1`: person exhibited constraint by scoring the same on both categories.

-   Constrain of `0.5`: person did not exhibit constraint by scoring differently on both categories.



<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-3-1.png" width="672" />

## Constraint By Demographics

### Constraint By Education

The graph below demonstrates how constraint varies across education level. It is evident that for higher educated people, those with bachelors degree or higher, they is a significantly higher number of constrained people. Further, across all education levels, the number of constrained people (either `0` or `1`) is higher than the number of `0.5` people.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-4-1.png" width="672" />

### Cosntrained By Income:

The graphs below show how average constraint varies across income. Similar to the education graph, people with the highest level of income appear to also have the most significant difference levels of constraint, favoring `0` and `1`.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-5-1.png" width="672" />

### Trade offs With This Approach:

By only looking at two variables, it is difficult to get a robust definition of constraint. Another method would be to consider all of the political questions and take the averages of those. However, this would make it difficult to understand what the non `0` or `1` values mean. It would require identifying a scale of constraint. What does it mean if a person scores a 25%.

## Constraint (2nd Calculation):

To test if considering more variables changes these outcomes, I have similarly created binary variables for `politically_motivated`, `suspend_campaign`, and `fav_trump`.



### Constraint By Education

The graphs below similarly show constrain by education level. The histograms all appear fairly symmetric. This makes sense given that both `0` and `1` can be seen as contrained. Further, a similar trend appears in which higher education is associated with higher levels of constraint.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-7-1.png" width="672" />

## Beyond the Binary: Don't Know Entries

Having dealt primarily with binary variables, it is also important to consider when entries like "Don't Know" appear. To assess the prevalence of "Don't Know", I created a binary variable for `should_be_charged` and `charge_serious` indicating whether the respondent entered "Don't Know". A `1` means the respondent responsed "Don't Know" on both of the questions, whereas a `0` means they responded "Don't Know" on neither of the questions. The following section looks at different demographic breakdowns for "Don't Know" entries

### Education:



<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-9-1.png" width="672" />

### Income:

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-10-1.png" width="672" />

From the two graph displays above, it is evident that the highest number of `0`s from those who are educated and high income. This indicates a possible association between these demographics and the likelihood to have strong political opinions.

## Modeling: Demographics and Trump Indictment

To evaluate the relationship between opinions toward the Trump Indictment and demographics, I have fitted four models with demographics as the predictors and `politically_motivated` as the outcome variable.

The regression table below shows the variables in each model and the outcome statistics.




Regression Results
========================================================
                           Dependent variable:          
                  --------------------------------------
                          Politically Motivated         
                    (1)       (2)       (3)       (4)   
--------------------------------------------------------
Party [PID]       0.738*** 0.724***  0.727***           
                  (0.019)   (0.023)   (0.023)           
                                                        
Education [educ5]          -0.040*** -0.040*** -0.075***
                            (0.010)   (0.009)   (0.010) 
                                                        
Age [age4]                 -0.018**  -0.018**           
                            (0.009)   (0.009)           
                                                        
Income [inc7]               -0.002              -0.004  
                            (0.007)             (0.006) 
                                                        
Gender                       0.022                      
                            (0.022)                     
                                                        
Constant          0.155*** 0.337***  0.337***  0.890*** 
                  (0.016)   (0.051)   (0.043)   (0.036) 
                                                        
--------------------------------------------------------
Observations       1,337      937       937      2,178  
R2                 0.519     0.534     0.534     0.035  
Adjusted R2        0.518     0.532     0.532     0.034  
========================================================
Note:                        *p<0.1; **p<0.05; ***p<0.01

<table style="text-align:center"><caption><strong>Regression Results</strong></caption>
<tr><td colspan="5" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"></td><td colspan="4"><em>Dependent variable:</em></td></tr>
<tr><td></td><td colspan="4" style="border-bottom: 1px solid black"></td></tr>
<tr><td style="text-align:left"></td><td colspan="4">Politically Motivated</td></tr>
<tr><td style="text-align:left"></td><td>(1)</td><td>(2)</td><td>(3)</td><td>(4)</td></tr>
<tr><td colspan="5" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">Party [PID]</td><td>0.738<sup>***</sup></td><td>0.724<sup>***</sup></td><td>0.727<sup>***</sup></td><td></td></tr>
<tr><td style="text-align:left"></td><td>(0.019)</td><td>(0.023)</td><td>(0.023)</td><td></td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Education [educ5]</td><td></td><td>-0.040<sup>***</sup></td><td>-0.040<sup>***</sup></td><td>-0.075<sup>***</sup></td></tr>
<tr><td style="text-align:left"></td><td></td><td>(0.010)</td><td>(0.009)</td><td>(0.010)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Age [age4]</td><td></td><td>-0.018<sup>**</sup></td><td>-0.018<sup>**</sup></td><td></td></tr>
<tr><td style="text-align:left"></td><td></td><td>(0.009)</td><td>(0.009)</td><td></td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Income [inc7]</td><td></td><td>-0.002</td><td></td><td>-0.004</td></tr>
<tr><td style="text-align:left"></td><td></td><td>(0.007)</td><td></td><td>(0.006)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Gender</td><td></td><td>0.022</td><td></td><td></td></tr>
<tr><td style="text-align:left"></td><td></td><td>(0.022)</td><td></td><td></td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:left">Constant</td><td>0.155<sup>***</sup></td><td>0.337<sup>***</sup></td><td>0.337<sup>***</sup></td><td>0.890<sup>***</sup></td></tr>
<tr><td style="text-align:left"></td><td>(0.016)</td><td>(0.051)</td><td>(0.043)</td><td>(0.036)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td><td></td><td></td></tr>
<tr><td colspan="5" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">Observations</td><td>1,337</td><td>937</td><td>937</td><td>2,178</td></tr>
<tr><td style="text-align:left">R<sup>2</sup></td><td>0.519</td><td>0.534</td><td>0.534</td><td>0.035</td></tr>
<tr><td style="text-align:left">Adjusted R<sup>2</sup></td><td>0.518</td><td>0.532</td><td>0.532</td><td>0.034</td></tr>
<tr><td colspan="5" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"><em>Note:</em></td><td colspan="4" style="text-align:right"><sup>*</sup>p<0.1; <sup>**</sup>p<0.05; <sup>***</sup>p<0.01</td></tr>
</table>



### Model 1: Party

Model 1 utilizes only one predictor, party. The predictor is statistically significant and the adusted R\^2 is 0.518, barely above 0.5

### Model 2: All Demographics

Model 2 is a multivariate regression with 5 predictors. Only party education, and age are statistically significant at the 95% confidence level. The adjusted R\^2 is slightly higher at 0.532

### Model 3: Only Statistically Significant Predictors

Model 3 kept only the statistically significant predictors from model 2 (party, education, and age). The adjusted R\^2 stayed the same at 0.532

### Model 4: Education and Income

Model 4 evaluates the variables assessed earlier in this blog: education and income. Only education is statistically significant and the adjusted R\^2 is extremely low at 0.032

### Comparison of Models:

Model 2 and 3 had the highest adjusted R\^2 values, although they are still relatively very small. This indicates that political motivation is difficult to model from these variables. Across the coefficient values, party had the highest value at 0.724. This can be interpreted as, holding all other variables constant, political motivation is expected to increase by 0.724 units when going from a Democrat (0) to a Republican (1). This makes sense given the question is pertaining to whether the indictment is politically motivated. Republicans would likely support Trump and consider external factors, such as political motivation, for the reason behind the indictments. Conversely, among the significant variables, age and education had the lowest values, both with a negative impact. Therefore, holding the other variables constant, increasing these variables, respectively, will have a negative impact on political motivation.

## Discussion:

The analyses presented in this blog seek to identify the behaviors driving opinions in the Trump indictment. In the first part of the blog, I looked at the relationship between constraint and education. The graphs show that as education increases, people are more likely to have political constraint. This corresponds to what the authors in *Voice and Equality* argue: "political engagement is a function of resources" (Verba, Schlozman, and Brady 1995). People with higher levels of education are more likely to follow the news and have the time and money to focus on political engagement. The second part of this claim, money, can be seen by the income distribution for constraint. Similar to education, higher levels of income correspond to higher levels of constraint.

The implications of these findings are relevant when considering the findings from [Week 3: Groups and Identities](https://anneliesq.github.io/politcal-psych-blog/post/2023-10-02-week-3-groups-and-identities/). In this blog, I found that for "strong partisans, political identities are more significant than for weak partisans" and this corresponding to what Iyengar, Sood, and Lelkes (2012) find when surveying reactions of parents to the idea of their child marrying a person of the opposite party. I think there is a connection between strong partisans and those are who politically constrained. High constraintment indicates and individual does not vary across their opinions, similar to someone with high partisanship. Therfore, people with higher levels of education and income are more likely to be strong partisans and likely politically engaged. This connection is significant because it demonstrates that those with money and education are the most politically engaged, and therefore more likely to have their beliefs represented in government.

Overall, political constraint among individuals is a desired outcome. We see that time and money are the main drivers of those who have higher levels of constraint. To increase political engagement, barriers at all levels of civic engagement is one way to reduce this divide. Considering just voting, increasing voting accessibility through mail-in ballots, national voting day, and increased polls and hours, are some ways to reduce the burden of voting, likely causing those without time and money to feel like voting is accessible and important.

## References:

Iyengar, Shanto, Gaurav Sood, and Yphtach Lelkes. 2012. "Affect, Not Ideology: A Social Identity Perspective on Polarization." Public Opinion Quarterly 76(3): 405--31.

Verba, Schlozman, and Brady 1995
