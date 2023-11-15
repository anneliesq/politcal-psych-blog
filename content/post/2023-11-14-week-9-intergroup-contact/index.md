---
title: 'Week 9: Intergroup Contact'
author: Annelies Quinton
date: '2023-11-14'
slug: []
categories: []
tags: []
---



## Introduction:

In this week's blog post, I am examining the idea of intergroup contact within a society. This includes situations like public transportation, sports, and neighborhoods. With all societies becoming significantly more diverse, understanding the outcomes of this on individuals is imperative. Will intergroup contact create *conflict* or *contact?*

-   Conflict: sharing space causes negative attitudes and behaviors.

-   Contact: sharing space causes positive attitudes

This blog seeks to answer the question of whether contact with a member of an outgroup can change people's perception of that group? The study and methods in this blog is a recreation of the study conducted by Dong Wang, Iain Johnstonand Baoyu Wang. Wang et al. (2021). They conducted an experiment on a group of Chinese students to determine if imagined social contact could reduce antipathy toward Japanese people. I also use class-wide data that resembles the Wang et a. (2021) study, in which students students imagined social contact with a member of the opposite political party.

## Data

In both studies, Wang et al. (2021) and the class survey, subjects were asked to imagine a bus ride, either one in which they talked to a Japanese (other political party) person (treatment) or just enjoyed the scenery (control). They were then asked a series of questions to assess their affective feelings toward the out-group and toward their own group.

**Wang et al. (2021):**

The data from the Wang et al.(2021) study includes 120 responses with 24 variables.

A list of the important variables to this blog are shown below:

| Variable Name                                           | Variable Description                                                                                                                                                                                    |
|------------------------|------------------------------------------------|
| `treated`                                               | Binary variable equal to `TRUE` if the subject was told to imagine a bus ride with a Japanese person (the treatment) and `FALSE` if the subject was told to imagine the scenery on a bus ride (control) |
| `JapanWarm`, `JapanAdmire`, `JapanRespect`, `JapanPos`  | Affective feeling about Japanese people ranging from 1 (cool) to 7 (warm/admiration/respect/positive)                                                                                                   |
| `ChinaWarm`, `ChinaAdmire`, `ChinaRespect`, `ChinaPos`, | Affective feeling about Chinese people ranging from 1 (loathing) to 7 (warm/admiration/respect/positive)                                                                                                |
| `WarmDiff`, `AdmireDiff`, `RespectDiff`, `AdmireDiff`   | Difference between the Chinese and Japanese (warm/admiration/respect/positive) score                                                                                                                    |
| `JapanAffect`, `ChinaAffect`                            | Average affective feelings about each group                                                                                                                                                             |

**Class:**

The data from the class survey inlcudes 55 rows and 59 columns.

A list of the important variables is shown below:

| Variable Name          | Variable Description                                                                                                                                                                                                           |
|-----------------------|-------------------------------------------------|
| `Treated`              | Binary variable equal to `TRUE` if the subject was told to imagine a bus ride with a member of the opposing political party (the treatment) and `FALSE` if the subject was told to imagine the scenery on a bus ride (control) |
| `InPartyAffect_(1-4)`  | Affective feelings about the in-party using the same numbering scheme as above                                                                                                                                                 |
| `InPartyAffect_avg`    | Average affective feelings about the in-party                                                                                                                                                                                  |
| `OutPartyAffect_(1-4)` | Affective feelings about the out-party using the same numbering scheme as above                                                                                                                                                |
| `OutPartyAffect_avg`   | Average affective feelings about the out-party                                                                                                                                                                                 |
| `AffectDiff_avg`       | Average difference in affective feelings between in-party and out-party                                                                                                                                                        |

## Part 1: Wang et al. (2021):

In the first section of the blog, I analyze the data presented by Want et al. (2021). I first consider average affect scores for Chinese versus Japanese people and compare these for the control and treatment groups. I then consider the difference in averages to identify statistical significance of the treatment. Finally, I model affect scores based on chosen control variables.





### Distribution of Affect Scores

The histograms below show the distribution of average affect scores for Chinese and Japanese for the control and treatment groups. The dotted line shows the median for each of these groups. For both the control and treatment groups, there is a significant difference between Chinese and Japanese ratings. Both groups have higher ratings for Chinese people.



<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-4-1.png" width="1440" />

### Positivity Score Averages

In this section I selected one of the affect measures, positivity and conducted a t-test for Japanese and Chinese ratings for the treatment and control. I then conducted a t-test for average ratings between the treatment and control.

#### Chinese



![](images/Screen%20Shot%202023-11-14%20at%209.55.10%20PM.png)

The t-test shows that the mean rating for Chinese among the treated is lower than that of the control. However, these results are statistically insignificant.

#### Japanese



![](images/Screen%20Shot%202023-11-14%20at%209.45.53%20PM.png)

The t-test shows that the mean rating for Japanese among the treated is higher than that of the control. Further, these results are statistically significant, demonstrating the treatment was effective in improving the positivity rating of Japanese people among Chinese students in this study.

### Average Affection Difference Comparison



![](images/Screen%20Shot%202023-11-14%20at%208.49.42%20PM.png)

This t-test considers the difference in average affect scores between Chinese and Japanese people for the treatment and control grups. The output is the mean difference between ratings. A lower value demonstrates there is less animosity toward Japanese people. The results are statistically significant and show that the treated had a smaller difference than the control, indicating the treatment was effective.

### Modeling Affect:

-   Dependent Variable : `AffectDiff_avg`

-   Control Variables: **`jpfriend`** and `age`

-   (Null) Hypothesis 1a: There will no be difference between those with a Japanese friend and those without's ratings of Chinese versus Japanese people after receiving the treatment about imagining positive contact with a Japanese person.

    -   If we find that there is a statistically significant difference between these groups, we would reject the null hypothesis that there is no difference in the effect of the treatment on having a Japanese friend or not.
    -   I would expect those with Japanese friends to be less critical toward Japanese people in general. This could be due to heuristic thinking, in which people substitute the question of their opinion toward Japanese people with their opinion toward their Japanese friend.

-   (Null) Hypothesis 2a: There will be no difference in ratings between older versus younger people

    -   If we find that there is a statistically significant difference between older and younger respondents,we would reject the null hypothesis that there is no difference in the effect of the treatment on those of different ages.
    -   In this age demographic, I would expect older people to be less critical because they have spent more time away from home, where traditional beliefs, such as cemented symbolic attitudes like disapproval toward Japanese people, would likely exist.


<table style="text-align:center"><caption><strong>Regression Results</strong></caption>
<tr><td colspan="2" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"></td><td><em>Dependent variable:</em></td></tr>
<tr><td></td><td colspan="1" style="border-bottom: 1px solid black"></td></tr>
<tr><td style="text-align:left"></td><td>Difference in Affection For Chinese and Japanese</td></tr>
<tr><td colspan="2" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">Treatment</td><td>-0.647<sup>**</sup></td></tr>
<tr><td style="text-align:left"></td><td>(0.287)</td></tr>
<tr><td style="text-align:left"></td><td></td></tr>
<tr><td style="text-align:left">Has Japanese Friend</td><td>0.180</td></tr>
<tr><td style="text-align:left"></td><td>(0.297)</td></tr>
<tr><td style="text-align:left"></td><td></td></tr>
<tr><td style="text-align:left">Age</td><td>-0.041</td></tr>
<tr><td style="text-align:left"></td><td>(0.046)</td></tr>
<tr><td style="text-align:left"></td><td></td></tr>
<tr><td style="text-align:left">Constant</td><td>2.114<sup>**</sup></td></tr>
<tr><td style="text-align:left"></td><td>(1.044)</td></tr>
<tr><td style="text-align:left"></td><td></td></tr>
<tr><td colspan="2" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">Observations</td><td>120</td></tr>
<tr><td style="text-align:left">R<sup>2</sup></td><td>0.051</td></tr>
<tr><td style="text-align:left">Adjusted R<sup>2</sup></td><td>0.026</td></tr>
<tr><td colspan="2" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"><em>Note:</em></td><td style="text-align:right"><sup>*</sup>p<0.1; <sup>**</sup>p<0.05; <sup>***</sup>p<0.01</td></tr>
</table>

#### Interpretation

-   [Treatment]{.underline}: The coefficient value for treatment demonstrates that when subjects receive the subject, the difference between ratings for Chinese and Japanese people decrease by 0.647, when holding age and whether the person has a Japanese friend constant.

-   [(Null) Hypothesis 1a:]{.underline} There is no statistically significant difference between ratings for those with and without a Japanese friends due to the treatment. Therefore, **we fail to reject the null hypothesis** that there is no difference between people with and without a Japanese friend's ratings of Chinese versus Japanese people after receiving the treatment about imagining positive contact with a Japanese person.

-   [(Null) Hypothesis 1a:]{.underline} There is no statistically significant difference between ratings for older and youger respondents due to the treatment. Therefore, **we fail to reject the null hypothesis** that there is no difference between younger and older people's ratings of Chinese versus Japanese people after receiving the treatment about imagining positive contact with a Japanese person.

The graph below visualizes these confidence intervals, demonstrating that none of the control variables, only treatment, are statistically significant because zero is included in the confidence interval.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-9-1.png" width="672" />

## Part 2: Class Data

In this section of the blog, I consider the data from the class survey that replicated the Wang et al. (2021) study. Rather than Chinese versus Japanese, this study considers the opposing political party. The out-party is equivalent to the Japanese in the Wang et al. (2021) study.







### Distribution of Affect Scores:

The histograms below show the average affect scores toward the in-party and out-party for the treated and control groups. The red dashed line displays the median. Like the graphs in the previous section, for both the treated and control, there is a large difference in the average affect scores for the in and out groups. For both treatment and control, the in-party receives a higher rating.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-13-1.png" width="1440" />

### Positivity Score Averages

After identifying the difference in affect scores, I look to measure this value through t-tests. I selected one of the affect measures, positivity, and then conducted a t-test for average ratings between the treatment and control.

#### In Group



![](images/Screen%20Shot%202023-11-14%20at%209.33.39%20PM.png)

The t-test displays the difference between positivity scores for treatment and control for the in-party. The results are statistically insignificant.

#### Out Group



![](images/Screen%20Shot%202023-11-14%20at%209.33.22%20PM.png)

The t-test displays the difference between positivity scores for treatment and control for the out-party. The results are statistically insignificant.

### Average Affection Difference Comparison



![](images/Screen%20Shot%202023-11-14%20at%209.33.05%20PM.png)

The t-test displays the difference between average affect scores between in-party and out-party, from the treatment and control. The results are statistically insignificant.

## Discussion

In Wang et al. (2021) they found it "clear that imagined social contact does lead to a narrowing in the perceived difference in overall feelings toward Chinese and Japanese people" (pg. 233), similar to the results I presented in part 1 of this blog. However, in the second part of the blog I replicate the analyses with the class data. Unlike with Wang et al. (2021), there is a not a statistically significant difference between the treatment and control groups.

This lack of statistical significance could be due to numerous factors. First, the class sample size is significantly smaller than the sample size in the original study. Further, as seen in earlier weeks, the political leanings of the class is homogeneous and favors the Democratic Party. For this reason, the results could actually be showing the impact of the treatment for democrats, not all people, regardless of political party affiliation. Additionally, the pool of subjects in the the class sample are students, similar to Wang et al. (2021). However, we are all fairly involved in government related topics. This bias towards politics could mean we are stronger partisans than the average student. A possible way to better replicate this study would be to get a more representative sample of students from different majors. Finally, despite these possible considerations for the difference, in the end, it could just be partisan and national identities are fundamentally different and the treatment is only effective for national identities. This could be because partisan identities are incredibly stationary in the United States, whereas relationship with other nations are more fluid and personal.

Overall, the Wang et al. (2021) study demonstrates hope that with increased interaction, negativity toward out-group members can be lessened. This idea is consistent with other scholars, such as Mousa (2020). The author finds that when Christians and Muslims are on the same team post-ISIS Iraq, there are more intergroup relations, such as voting for a teammate of the other religion to receive a sportsmanship award. Although, these results are only applicable to the soccer setting, reducing the study's external validity. However, the study still shows that intergroup relations can be improved at an environmental level. This has large implications for policy development. Policies with specific interventions toward faciliating intergroup contact, may produce similarly positive results. An example of this could be seen through schools. Schools with higher levels of diversity could receive more funding, making it appealing to be in a diverse setting.

## References

Mousa, S. (2020). Building social cohesion between Christians and Muslims through soccer in post-ISIS Iraq. Science, 369(6505):866--870.

Wang, D., Johnston, A. I., & Wang, B. (2021). The Effect of Imagined Social Contact on Chinese Students' Perceptions of Japanese People. Journal of Conflict Resolution, 65(1), 223-251.
