---
title: 'Week 10: Emotional Arousal and Hot Cognition'
author: Annelies Quinton
date: '2023-11-21'
slug: []
categories: []
tags: []
---

## Introduction

This week’s blog looks at the impact of emotions on political behavior, such as anxiety and disgust. This blog replicates Clifford and Jerit’s (2018) study, which considers the effects of disgust and anxiety on political behavior. They consider how people react to public health threats, specifically trying to understand how anxiety and disgust play into one’s response and the likelihood of being an “informed, activate public” (Clifford and Jerit, 2018, pg. 266).

In order to identify these effects, they provide participants with a fake news headline and blurb about a disease. To manipulate stress, the participants either learn the disease the disease is incredibly dangerous and high transmittable (high stress) or not very serious and low chance of spreading (low stress). To manipulate digust, the symptoms are either traditionally disgusting (diarrhea and boils) or painful (joint pains and headaches). The study then measured ability to correctly identify symptoms and whether they want more information.

Cliford and Jerit have three hypotheses about the impact of anxiety and disgust on information uptake and search:

1.  “An object that induces disgust should increase retention of information related to the source of the emotion” (pg. 267)
2.  “While disgust may improve memory of the source of emotional arousal, it will impair recall of information that is not the primary elicitor of disgust” (pg. 267)
3.  “A person who feels disgusted about a threat will avoid the source of disgust and new information about the topic” (pg. 268)

## Data

In study 1, the data involves 1000 participants. Data is drawn from a YouGov survey between December 14th - 21st, 2015. The data has been cleaned with new variable names.

A few of the key variables are listed below:

| Variable Name         | Variable Description                                                                                                                                                                            |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `treat_rand1`         | Treatment assignment: 1-Low Anxiety/Low Disgust, 2-High Anxiety/Low Disgust, 3-Low Anxiety/High Disgust, and 4-High Anxiety/High Disgust                                                        |
| `disgust`             | Self reported feeling of how well DISGUST describes respondent’s emotional reaction to virus: 1-Not Well At All, 2- Not Too Well, 3-Somewhat Well, 4-Very Well, 5-Extremely Well, 8-Skipped     |
| `grossed_out`         | Self reported feeling of how well GROSSED OUT describes respondent’s emotional reaction to virus: 1-Not Well At All, 2- Not Too Well, 3-Somewhat Well, 4-Very Well, 5-Extremely Well, 8-Skipped |
| `repulsed`            | Self reported feeling of how well REPULSED describes respondent’s emotional reaction to virus: 1-Not Well At All, 2- Not Too Well, 3-Somewhat Well, 4-Very Well, 5-Extremely Well, 8-Skipped    |
| `afraid`              | Self reported feeling of how well AFRAID describes respondent’s emotional reaction to virus: 1-Not Well At All, 2- Not Too Well, 3-Somewhat Well, 4-Very Well, 5-Extremely Well, 8-Skipped      |
| `anxious`             | Self reported feeling of how well ANXIOUS describes respondent’s emotional reaction to virus: 1-Not Well At All, 2- Not Too Well, 3-Somewhat Well, 4-Very Well, 5-Extremely Well, 8-Skipped     |
| `worried`             | Self reported feeling of how well WORRIED describes respondent’s emotional reaction to virus: 1-Not Well At All, 2- Not Too Well, 3-Somewhat Well, 4-Very Well, 5-Extremely Well, 8-Skipped     |
| `fatigue`             | Identification of FATIGUE as a symptom: 1-Yes, 2- No                                                                                                                                            |
| `headaches`           | Identification of HEADACHES as a symptom: 1-Yes, 2- No                                                                                                                                          |
| `diarrhea`            | Identification of DIARRHEA as a symptom: 1-Yes, 2- No                                                                                                                                           |
| `joint_pain`          | Identification of JOINT PAIN as a symptom: 1-Yes, 2- No                                                                                                                                         |
| `boil`                | Identification of BOILS as a symptom: 1-Yes, 2- No                                                                                                                                              |
| `warts`               | Identification of WARTS as a symptom: 1-Yes, 2- No                                                                                                                                              |
| `fever`               | Identification of FEVER as a symptom: 1-Yes, 2- No                                                                                                                                              |
| `look_up`             | Self-reported likelihood of looking up more info: 1-Not likely at all, 2-Not too likely, 3-Somewhat likely, 4-Very likely, 5-Extremely likely, 8-Skipped                                        |
| `share`               | Self-reported likelihood of talking with friends or family about disease in next week: 1-Not likely at all, 2-Not too likely, 3-Somewhat likely, 4-Very likely, 5-Extremely likely, 8-Skipped   |
| `page_article_timing` | Time spent in seconds on page containing article about disease                                                                                                                                  |

## Treatment Conditions

- 1: Low Anxiety/Low Disgust

  - Disease has low transmission rates and symptoms are just painful (joint pains and headaches and fatigue)

- 2: High Anxiety/Low Disgust

  - Disease has high transmission rates and symptoms are just painful (joint pains and headaches and fatigue)

- 3: Low Anxiety/High Disgust

  - Disease has low transmission rates and symptoms are “disgusting” (boils and warts and fatigue)

- 4: High Anxiety/High Disgust

  - Disease has low transmission rates and symptoms are “disgusting” (boils and warts and fatigue)

## Manipulation Check

Before running more in-depth analyses understanding to the impacts of anxiety and disgust, it is important to make sure the manipulation of inducing anxiety and disgust was successful.

This means treatment groups 3 and 4 should have the highest levels of disgust and treatment groups 2 and 4 should have the highest levels of anxiety.

The table below shows that this true. The difference appears to be especially clear for disgust. The highest anxiety level is for group 2 (high anxiety and low disgust). The highest disgust level is for group 4 (high anxiety and high disgust). These results are consistent with the findings from Clifford and Jerit (2018).

<div id="hlwoldluxv" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#hlwoldluxv table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
&#10;#hlwoldluxv thead, #hlwoldluxv tbody, #hlwoldluxv tfoot, #hlwoldluxv tr, #hlwoldluxv td, #hlwoldluxv th {
  border-style: none;
}
&#10;#hlwoldluxv p {
  margin: 0;
  padding: 0;
}
&#10;#hlwoldluxv .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}
&#10;#hlwoldluxv .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}
&#10;#hlwoldluxv .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}
&#10;#hlwoldluxv .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}
&#10;#hlwoldluxv .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}
&#10;#hlwoldluxv .gt_column_spanner_outer:first-child {
  padding-left: 0;
}
&#10;#hlwoldluxv .gt_column_spanner_outer:last-child {
  padding-right: 0;
}
&#10;#hlwoldluxv .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}
&#10;#hlwoldluxv .gt_spanner_row {
  border-bottom-style: hidden;
}
&#10;#hlwoldluxv .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}
&#10;#hlwoldluxv .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}
&#10;#hlwoldluxv .gt_from_md > :first-child {
  margin-top: 0;
}
&#10;#hlwoldluxv .gt_from_md > :last-child {
  margin-bottom: 0;
}
&#10;#hlwoldluxv .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}
&#10;#hlwoldluxv .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#hlwoldluxv .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}
&#10;#hlwoldluxv .gt_row_group_first td {
  border-top-width: 2px;
}
&#10;#hlwoldluxv .gt_row_group_first th {
  border-top-width: 2px;
}
&#10;#hlwoldluxv .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#hlwoldluxv .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_first_summary_row.thick {
  border-top-width: 2px;
}
&#10;#hlwoldluxv .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#hlwoldluxv .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}
&#10;#hlwoldluxv .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#hlwoldluxv .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#hlwoldluxv .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#hlwoldluxv .gt_left {
  text-align: left;
}
&#10;#hlwoldluxv .gt_center {
  text-align: center;
}
&#10;#hlwoldluxv .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}
&#10;#hlwoldluxv .gt_font_normal {
  font-weight: normal;
}
&#10;#hlwoldluxv .gt_font_bold {
  font-weight: bold;
}
&#10;#hlwoldluxv .gt_font_italic {
  font-style: italic;
}
&#10;#hlwoldluxv .gt_super {
  font-size: 65%;
}
&#10;#hlwoldluxv .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}
&#10;#hlwoldluxv .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}
&#10;#hlwoldluxv .gt_indent_1 {
  text-indent: 5px;
}
&#10;#hlwoldluxv .gt_indent_2 {
  text-indent: 10px;
}
&#10;#hlwoldluxv .gt_indent_3 {
  text-indent: 15px;
}
&#10;#hlwoldluxv .gt_indent_4 {
  text-indent: 20px;
}
&#10;#hlwoldluxv .gt_indent_5 {
  text-indent: 25px;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_heading">
      <td colspan="3" class="gt_heading gt_title gt_font_normal gt_bottom_border" style><strong>Average Anxiety and Disgust Based on Treatment Group</strong></td>
    </tr>
    &#10;    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="Article treatment">Article treatment</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Avg. Anxiety">Avg. Anxiety</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Avg. Disgust">Avg. Disgust</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td headers="treat_rand1" class="gt_row gt_center">1</td>
<td headers="Avg. Anxiety" class="gt_row gt_right">2.191964</td>
<td headers="Avg. Disgust" class="gt_row gt_right">2.177778</td></tr>
    <tr><td headers="treat_rand1" class="gt_row gt_center">2</td>
<td headers="Avg. Anxiety" class="gt_row gt_right">2.381132</td>
<td headers="Avg. Disgust" class="gt_row gt_right">2.200000</td></tr>
    <tr><td headers="treat_rand1" class="gt_row gt_center">3</td>
<td headers="Avg. Anxiety" class="gt_row gt_right">2.181102</td>
<td headers="Avg. Disgust" class="gt_row gt_right">2.521569</td></tr>
    <tr><td headers="treat_rand1" class="gt_row gt_center">4</td>
<td headers="Avg. Anxiety" class="gt_row gt_right">2.199203</td>
<td headers="Avg. Disgust" class="gt_row gt_right">2.541833</td></tr>
  </tbody>
  &#10;  
</table>
</div>

## Cronbach’s Alpha:

Cronbach’s alpha is a measure of how internally consistent the answers to multiple questions are. This is an important measure when using indexes of multiple measures aimed at a single concept.

The formula is shown below:

![](images/Screen%20Shot%202023-11-21%20at%207.47.35%20PM.png)

### Anxiety

The results below the show the Cronbach’s alpha for disgust. The Cronbach’s alpha below 0.7 are regarded as insufficiently internally consistent.

The Cronsbach’s alpha is: 0.917 (highly consistent)

![](images/Screen%20Shot%202023-11-21%20at%207.41.53%20PM.png)

### Disgust

The Cronbach’s alpha is: 0.932 (highly consistent, more so than anxiety)

![](images/Screen%20Shot%202023-11-21%20at%207.41.47%20PM.png)

## Modeling Correct Symptoms

Before getting into the results of the hypotheses, I create a multivariate linear regression, modeling the likelihood of identifying correct symptoms based on how long an individual spends reading the article, their party affiliation, and education level.

The regression table below shows the results. Time spent reading is the only variable that is significant, but only at the 90% confidence level. This means that for every one unit increase in time spent reading, there is a .0001 increase in likelihood of identifying correct symptoms, holding all other variables constant.

<table style="text-align:center">
<caption>
<strong>Regression Results</strong>
</caption>
<tr>
<td colspan="2" style="border-bottom: 1px solid black">
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
<em>Dependent variable:</em>
</td>
</tr>
<tr>
<td>
</td>
<td colspan="1" style="border-bottom: 1px solid black">
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
Correct Symptoms
</td>
</tr>
<tr>
<td colspan="2" style="border-bottom: 1px solid black">
</td>
</tr>
<tr>
<td style="text-align:left">
Time Spent Reading
</td>
<td>
0.0001<sup>\*</sup>
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
(0.00004)
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
</td>
</tr>
<tr>
<td style="text-align:left">
Party ID
</td>
<td>
-0.008
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
(0.007)
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
</td>
</tr>
<tr>
<td style="text-align:left">
Education
</td>
<td>
0.010
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
(0.010)
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
</td>
</tr>
<tr>
<td style="text-align:left">
Constant
</td>
<td>
0.327<sup>\*\*\*</sup>
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
(0.047)
</td>
</tr>
<tr>
<td style="text-align:left">
</td>
<td>
</td>
</tr>
<tr>
<td colspan="2" style="border-bottom: 1px solid black">
</td>
</tr>
<tr>
<td style="text-align:left">
Observations
</td>
<td>
962
</td>
</tr>
<tr>
<td style="text-align:left">
R<sup>2</sup>
</td>
<td>
0.006
</td>
</tr>
<tr>
<td style="text-align:left">
Adjusted R<sup>2</sup>
</td>
<td>
0.003
</td>
</tr>
<tr>
<td colspan="2" style="border-bottom: 1px solid black">
</td>
</tr>
<tr>
<td style="text-align:left">
<em>Note:</em>
</td>
<td style="text-align:right">
<sup>*</sup>p\<0.1; <sup>**</sup>p\<0.05; <sup>***</sup>p\<0.01
</td>
</tr>
</table>

The plot below shows that none of the variables are statistically significant at the 95% confidence level because 0 is included in the confidence interval.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-8-1.png" width="672" />

## Evaluating the Hypotheses:

### Hypothesis 1

Hypothesis 1 states that “an object that induces disgust should increase retention of information related to the source of the emotion” (pg. 267). This can be assessed through analyzing the percentage of individuals who correctly identified the correct symptoms for high disgust and low disgust groups.

The t-test below shows that there is ~ 0.04 average increase in correct symptom recollection, but the results are statistically insignificant. This is different from Clifford and Jerit (2018) because they control for anxiety. Their results find that in people in the high disgust condition were more “likely to remember both symptoms than respondents in the low disgust condition (70% vs. 61%, ~ 10 percentage points)” (pg. 270). There results are significant at the 90% confidence level. Their results confirm hypothesis 1.

<img src="images/Screen%20Shot%202023-11-21%20at%207.14.26%20PM.png" width="466" />

### Hypothesis 2

Hypothesis 2 states that “while disgust may improve memory of the source of emotional arousal, it will impair recall of information that is not the primary elicitor of disgust” (pg. 267). To test this, we can compare likelihood of reporting fatigue as a symptom. Fatigue is one of the symptoms reported for all conditions, so not identifying this as a symptom would indicate “impaired recall of information”, regardless of the treatment condition.

The t-test below shows that in high disgust situations, people are 10 percentage points less likely to identify fatigue as a symptom. In low digust conditions, 78% correcelty identify fatigue as a symptom, but in high disgust conditions, this drops to 69%. This results are statistically significant and consistent with the findings in Clifford and Jerit (2018).

<img src="images/Screen%20Shot%202023-11-21%20at%207.20.42%20PM.png" width="445" />

### Hypothesis 3

The third hypothesis states that “a person who feels disgusted about a threat will avoid the source of disgust and new information about the topic” (pg. 268). To test this hypothesis, I consider the variable `additional_info`, which indicates whether a participant sought out additional information. My analysis shows the results are statistically insignificant, however, Clifford and Jerit (2018) perform a more robust analysis for hypothesis 3. They consider 4 different variables assessing information search. They found that “disgust generated a qualitatively different reaction than did anxiety—one of avoidance rather than engagement.” Specifically, “anxiety increased informationsearch only in the absence of disgust” (pg. 272). This means that among the emotions, anxiety is the best predictor for understanding if a person will seek additional information.

<img src="images/Screen%20Shot%202023-11-21%20at%207.30.37%20PM.png" width="451" />

## Discussion

## References

Clifford, & Jerit, J. (2018). Disgust, Anxiety, and Political Learning in the Face of Threat. American Journal of Political Science, 62(2), 266–279. <https://doi.org/10.1111/ajps.12350>
