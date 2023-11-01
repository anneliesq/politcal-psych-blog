---
title: 'Week 1: Making Decisions'
author: Annelies Quinton
date: '2023-09-19'
slug: []
categories: []
tags: []
---

## Introduction

For this week’s post, I am looking at the relationship of perceived candidate competence and electoral success. The subjectivity of measuring competence illustrates how other variables may persist in an individual’s decision making process to ultimately determine competence. This idea can be defined as attribute substitution, in which a difficult question (such as defining competence) is substituted for an easier one. A method of substitution is evaluating a candidate’s competence based on their facial quality.

Through a psychological lens, this thought process is supported through the idea of different decision making systems in the brain. System 1 is described as our intuition and it is fast, automatic, and effortless. Conversely, system 2 is reasoning, and requires effort, time, and logic (Kahneman, D. 2003, 698). When connecting this idea to voting, one hypothesis is that for voters with less partisan loyalty or knowledge of the election, system 1 may be triggered and attribute substitution can occur, causing variables such as face ratings to determine one’s vote. 

Although this rationale may appear disconnected, in the paper *Candidate Faces and Election Outcomes: Is the Face–Vote Correlation Caused by Candidate Selection?*, the scholars find “higher quality challenger faces are selected into more competitive districts” (Atkinson et al. 2009, 230). They ultimately assert that “…incumbents from the most competitive districts would have higher facial quality than incumbents from the most safe incumbent districts due to the selection process of better faces to competitive districts, inducing a negative relationship between incumbent face and incumbent vote” (Atkinson et al. 2009, 236).

The data presented in this blog will address the question of whether seat safety is negatively correlated with incumbent facial quality?

## Data

The data used in this blog is a condensed and adapted version of the replication data for Atkinson et al. (2009). The variables of interest are `face_rating`,`incumbent`, `tossup`, and `face_rating`.

| Variable Name | Variable Description                                                                               |
|---------------|----------------------------------------------------------------------------------------------------|
| `cook`        | The assessment of the Senate race from the Cook Political Report in the year prior to the election |
| `year`        | The year of the election                                                                           |
| `state`       | The state in which the candidate was running                                                       |
| `face_rating` | The normalized rating of the candidate’s perceived competence based on an image of the face        |
| `incumbent`   | An indicator variable for whether the candidate was an incumbent                                   |
| `candidate`   | The candidate’s name                                                                               |
| `party`       | The candidate’s political party                                                                    |
| `tossup`      | An indicator variable for whether the race was one of two “tossup” categories according to Cook    |
| `jpg`         | A unique identifier for the photo of the candidate                                                 |

The data used in this blog is a condensed and adapted version of the [replication data](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/RSI8NR) for Atkinson et al. (2009).  The variables of interest are `face_rating`, `incumbent`, `tossup`, and `party`.

## Face Rating by Party

Before looking at seat safety and facial quality, it is important to evaluate trends in the data that could influence conclusions drawn. The graph below illustrates the distribution of face ratings based on the candidate’s party. From the graph, it is evident that there is little to no difference between the parties. This is significant in order for comparisons to be made between parties.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-1-1.png" width="672" />

## Face Rating: Incumbency and Toss-Up

To understand the relationship between incumbent seat safety and face rating, I looked at the spread of face ratings for four different groups:

### Incumbents:

`TT`: Incumbent in a toss-up race

`TF`: Incumbent not in a toss-up race

### Challengers:

`CT`: Challenger in a toss-up race

`CF`: Challenger not in a toss-up race

The table below displays the means for the four groups:

<div id="lbbonvmadw" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#lbbonvmadw table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
&#10;#lbbonvmadw thead, #lbbonvmadw tbody, #lbbonvmadw tfoot, #lbbonvmadw tr, #lbbonvmadw td, #lbbonvmadw th {
  border-style: none;
}
&#10;#lbbonvmadw p {
  margin: 0;
  padding: 0;
}
&#10;#lbbonvmadw .gt_table {
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
&#10;#lbbonvmadw .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}
&#10;#lbbonvmadw .gt_title {
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
&#10;#lbbonvmadw .gt_subtitle {
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
&#10;#lbbonvmadw .gt_heading {
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
&#10;#lbbonvmadw .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#lbbonvmadw .gt_col_headings {
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
&#10;#lbbonvmadw .gt_col_heading {
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
&#10;#lbbonvmadw .gt_column_spanner_outer {
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
&#10;#lbbonvmadw .gt_column_spanner_outer:first-child {
  padding-left: 0;
}
&#10;#lbbonvmadw .gt_column_spanner_outer:last-child {
  padding-right: 0;
}
&#10;#lbbonvmadw .gt_column_spanner {
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
&#10;#lbbonvmadw .gt_spanner_row {
  border-bottom-style: hidden;
}
&#10;#lbbonvmadw .gt_group_heading {
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
&#10;#lbbonvmadw .gt_empty_group_heading {
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
&#10;#lbbonvmadw .gt_from_md > :first-child {
  margin-top: 0;
}
&#10;#lbbonvmadw .gt_from_md > :last-child {
  margin-bottom: 0;
}
&#10;#lbbonvmadw .gt_row {
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
&#10;#lbbonvmadw .gt_stub {
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
&#10;#lbbonvmadw .gt_stub_row_group {
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
&#10;#lbbonvmadw .gt_row_group_first td {
  border-top-width: 2px;
}
&#10;#lbbonvmadw .gt_row_group_first th {
  border-top-width: 2px;
}
&#10;#lbbonvmadw .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#lbbonvmadw .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}
&#10;#lbbonvmadw .gt_first_summary_row.thick {
  border-top-width: 2px;
}
&#10;#lbbonvmadw .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#lbbonvmadw .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#lbbonvmadw .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}
&#10;#lbbonvmadw .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}
&#10;#lbbonvmadw .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}
&#10;#lbbonvmadw .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#lbbonvmadw .gt_footnotes {
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
&#10;#lbbonvmadw .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#lbbonvmadw .gt_sourcenotes {
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
&#10;#lbbonvmadw .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#lbbonvmadw .gt_left {
  text-align: left;
}
&#10;#lbbonvmadw .gt_center {
  text-align: center;
}
&#10;#lbbonvmadw .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}
&#10;#lbbonvmadw .gt_font_normal {
  font-weight: normal;
}
&#10;#lbbonvmadw .gt_font_bold {
  font-weight: bold;
}
&#10;#lbbonvmadw .gt_font_italic {
  font-style: italic;
}
&#10;#lbbonvmadw .gt_super {
  font-size: 65%;
}
&#10;#lbbonvmadw .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}
&#10;#lbbonvmadw .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}
&#10;#lbbonvmadw .gt_indent_1 {
  text-indent: 5px;
}
&#10;#lbbonvmadw .gt_indent_2 {
  text-indent: 10px;
}
&#10;#lbbonvmadw .gt_indent_3 {
  text-indent: 15px;
}
&#10;#lbbonvmadw .gt_indent_4 {
  text-indent: 20px;
}
&#10;#lbbonvmadw .gt_indent_5 {
  text-indent: 25px;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_heading">
      <td colspan="3" class="gt_heading gt_title gt_font_normal gt_bottom_border" style>Facial Rating Based on Incumbency and Toss-up</td>
    </tr>
    &#10;    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="Incumbent/Toss-up Status">Incumbent/Toss-up Status</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Avg. Face Rating">Avg. Face Rating</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="No. Candidates">No. Candidates</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr class="gt_group_heading_row">
      <th colspan="3" class="gt_group_heading" scope="colgroup" id="1. Incumbents (T_)">1. Incumbents (T_)</th>
    </tr>
    <tr class="gt_row_group_first"><td headers="1. Incumbents (T_)  seat_safety" class="gt_row gt_left">TF</td>
<td headers="1. Incumbents (T_)  mean_face" class="gt_row gt_right">0.26983541</td>
<td headers="1. Incumbents (T_)  candidates" class="gt_row gt_right">173</td></tr>
    <tr><td headers="1. Incumbents (T_)  seat_safety" class="gt_row gt_left">TT</td>
<td headers="1. Incumbents (T_)  mean_face" class="gt_row gt_right">0.51120600</td>
<td headers="1. Incumbents (T_)  candidates" class="gt_row gt_right">11</td></tr>
    <tr class="gt_group_heading_row">
      <th colspan="3" class="gt_group_heading" scope="colgroup" id="2. Challengers (C_)">2. Challengers (C_)</th>
    </tr>
    <tr class="gt_row_group_first"><td headers="2. Challengers (C_)  seat_safety" class="gt_row gt_left">CF</td>
<td headers="2. Challengers (C_)  mean_face" class="gt_row gt_right">-0.18920420</td>
<td headers="2. Challengers (C_)  candidates" class="gt_row gt_right">222</td></tr>
    <tr><td headers="2. Challengers (C_)  seat_safety" class="gt_row gt_left">CT</td>
<td headers="2. Challengers (C_)  mean_face" class="gt_row gt_right">-0.01519612</td>
<td headers="2. Challengers (C_)  candidates" class="gt_row gt_right">38</td></tr>
  </tbody>
  &#10;  
</table>
</div>

Rows 1 and 2 show face ratings for incumbents in either a toss-up or safe seat. The data shows incumbents in toss-ups have a higher facial rating compared to incumbents in safe seats. In fact, they have the highest overall average rating across the four groups. This can be further broken down through the boxplots below:

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-5-1.png" width="672" />

These results can be further broken down by party:

<div id="kchwidszug" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#kchwidszug table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
&#10;#kchwidszug thead, #kchwidszug tbody, #kchwidszug tfoot, #kchwidszug tr, #kchwidszug td, #kchwidszug th {
  border-style: none;
}
&#10;#kchwidszug p {
  margin: 0;
  padding: 0;
}
&#10;#kchwidszug .gt_table {
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
&#10;#kchwidszug .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}
&#10;#kchwidszug .gt_title {
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
&#10;#kchwidszug .gt_subtitle {
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
&#10;#kchwidszug .gt_heading {
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
&#10;#kchwidszug .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#kchwidszug .gt_col_headings {
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
&#10;#kchwidszug .gt_col_heading {
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
&#10;#kchwidszug .gt_column_spanner_outer {
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
&#10;#kchwidszug .gt_column_spanner_outer:first-child {
  padding-left: 0;
}
&#10;#kchwidszug .gt_column_spanner_outer:last-child {
  padding-right: 0;
}
&#10;#kchwidszug .gt_column_spanner {
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
&#10;#kchwidszug .gt_spanner_row {
  border-bottom-style: hidden;
}
&#10;#kchwidszug .gt_group_heading {
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
&#10;#kchwidszug .gt_empty_group_heading {
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
&#10;#kchwidszug .gt_from_md > :first-child {
  margin-top: 0;
}
&#10;#kchwidszug .gt_from_md > :last-child {
  margin-bottom: 0;
}
&#10;#kchwidszug .gt_row {
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
&#10;#kchwidszug .gt_stub {
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
&#10;#kchwidszug .gt_stub_row_group {
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
&#10;#kchwidszug .gt_row_group_first td {
  border-top-width: 2px;
}
&#10;#kchwidszug .gt_row_group_first th {
  border-top-width: 2px;
}
&#10;#kchwidszug .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#kchwidszug .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}
&#10;#kchwidszug .gt_first_summary_row.thick {
  border-top-width: 2px;
}
&#10;#kchwidszug .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#kchwidszug .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#kchwidszug .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}
&#10;#kchwidszug .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}
&#10;#kchwidszug .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}
&#10;#kchwidszug .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#kchwidszug .gt_footnotes {
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
&#10;#kchwidszug .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#kchwidszug .gt_sourcenotes {
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
&#10;#kchwidszug .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#kchwidszug .gt_left {
  text-align: left;
}
&#10;#kchwidszug .gt_center {
  text-align: center;
}
&#10;#kchwidszug .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}
&#10;#kchwidszug .gt_font_normal {
  font-weight: normal;
}
&#10;#kchwidszug .gt_font_bold {
  font-weight: bold;
}
&#10;#kchwidszug .gt_font_italic {
  font-style: italic;
}
&#10;#kchwidszug .gt_super {
  font-size: 65%;
}
&#10;#kchwidszug .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}
&#10;#kchwidszug .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}
&#10;#kchwidszug .gt_indent_1 {
  text-indent: 5px;
}
&#10;#kchwidszug .gt_indent_2 {
  text-indent: 10px;
}
&#10;#kchwidszug .gt_indent_3 {
  text-indent: 15px;
}
&#10;#kchwidszug .gt_indent_4 {
  text-indent: 20px;
}
&#10;#kchwidszug .gt_indent_5 {
  text-indent: 25px;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_heading">
      <td colspan="2" class="gt_heading gt_title gt_font_normal gt_bottom_border" style>Facial Rating Based on Incumbency and Toss-up</td>
    </tr>
    &#10;    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="Incumbent/Toss-up Status">Incumbent/Toss-up Status</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Avg. Face Rating">Avg. Face Rating</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr class="gt_group_heading_row">
      <th colspan="2" class="gt_group_heading" scope="colgroup" id="1. Republican Incumbent (T_)">1. Republican Incumbent (T_)</th>
    </tr>
    <tr class="gt_row_group_first"><td headers="1. Republican Incumbent (T_)  seat_party" class="gt_row gt_left">rep_TF</td>
<td headers="1. Republican Incumbent (T_)  mean_face" class="gt_row gt_right">0.2966962</td></tr>
    <tr><td headers="1. Republican Incumbent (T_)  seat_party" class="gt_row gt_left">rep_TT</td>
<td headers="1. Republican Incumbent (T_)  mean_face" class="gt_row gt_right">0.4296991</td></tr>
    <tr class="gt_group_heading_row">
      <th colspan="2" class="gt_group_heading" scope="colgroup" id="2. Republican Challenger (C_)">2. Republican Challenger (C_)</th>
    </tr>
    <tr class="gt_row_group_first"><td headers="2. Republican Challenger (C_)  seat_party" class="gt_row gt_left">rep_CF</td>
<td headers="2. Republican Challenger (C_)  mean_face" class="gt_row gt_right">-0.1246679</td></tr>
    <tr><td headers="2. Republican Challenger (C_)  seat_party" class="gt_row gt_left">rep_CT</td>
<td headers="2. Republican Challenger (C_)  mean_face" class="gt_row gt_right">0.1124187</td></tr>
    <tr class="gt_group_heading_row">
      <th colspan="2" class="gt_group_heading" scope="colgroup" id="3. Democrat Incumbent (T_)">3. Democrat Incumbent (T_)</th>
    </tr>
    <tr class="gt_row_group_first"><td headers="3. Democrat Incumbent (T_)  seat_party" class="gt_row gt_left">dem_TF</td>
<td headers="3. Democrat Incumbent (T_)  mean_face" class="gt_row gt_right">0.2413757</td></tr>
    <tr><td headers="3. Democrat Incumbent (T_)  seat_party" class="gt_row gt_left">dem_TT</td>
<td headers="3. Democrat Incumbent (T_)  mean_face" class="gt_row gt_right">0.6090143</td></tr>
    <tr class="gt_group_heading_row">
      <th colspan="2" class="gt_group_heading" scope="colgroup" id="4. Democrat Challenger (C_)">4. Democrat Challenger (C_)</th>
    </tr>
    <tr class="gt_row_group_first"><td headers="4. Democrat Challenger (C_)  seat_party" class="gt_row gt_left">dem_CF</td>
<td headers="4. Democrat Challenger (C_)  mean_face" class="gt_row gt_right">-0.2611161</td></tr>
    <tr><td headers="4. Democrat Challenger (C_)  seat_party" class="gt_row gt_left">dem_CT</td>
<td headers="4. Democrat Challenger (C_)  mean_face" class="gt_row gt_right">-0.1569904</td></tr>
  </tbody>
  &#10;  
</table>
</div>

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-7-1.png" width="672" />

The table and boxplots show that, broken down by party, incumbents in toss-up races had the highest facial rating. Democratic incumbents in toss-up races had the overall highest average rating.

## Discussion

The results demonstrate that toss-up incumbents had the highest facial rating, indicating that candidates with higher facial quality have an advantage in . These findings agree with what Atkinson et al. (2009) suggest, that seat safety is negatively correlated with incumbent facial quality. Atkinson et al. (2009) suggest these trends are because candidates with a better facial rating are deemed more competent, and will select into races in which they have a higher chance of winning. Therefore, lower quality candidates will select into less competitive races. This creates a correlation between facial quality and seat competitiveness (Atkinson et al. 2009, 231).

## References

Kahneman, D. (2003). A Perspective on Judgement and Choice: Mapping Bounded Rationality. *American Psychologist,* 58(9):697–720.

Atkinson, M. A., Enos, R. D., and Hill., S. J. (2009). Candidate faces and election outcomes: Is the face-vote correlation caused by candidate selection? *Quarterly Journal of Political Science*, 4:229–249.
