---
title: 'Week 3: Groups and Identities'
author: "Annelies Quinton"
date: "2023-10-02"
output: pdf_document
categories: []
tags: []
slug: []
---

## Introduction:

This week’s blog post considers the role of groups and identities in politics, specifically around party affiliation and the impacts of polarization. The study outlined in the blog serves as a replication of Iyengar, Sood, and Lelkes (2012) study. They seek to find the “proportion upset, displeased, or unhappy, if progeny married someone from another party.” To replicate this study, our class took a survey asking their happiness level (very unhappy to very happy) if their child married a Republican and, similarly, if they married a democrat. One caveat to the survey was that a portion the class received a survey in which they were told the spouse spoke “frequently about their political beliefs”, another survey said “rarely spoke about their political beliefs”, and the third served as the control, not including a statement about speaking habits.

For each individual, their political affiliation was also recorded from past survey results. The driving question for this blog is whether reactions (happiness levels) looked different for weak vs. strong partisans? Strong partisans are those who “identifies as a strong member of either major party.”

## Data:

The data collected in this survey includes 60 entries (individuals) and includes 12 variables. The variables used in this analysis are listed below:

| Variable Name     | Variable Description                                                                                                    |
|-------------------|-------------------------------------------------------------------------------------------------------------------------|
| `treatment`       | Which treatment condition the respondent was randomly assigned to                                                       |
| `marryDemocrat`   | The respondent’s answer to how happy they would be if their child married a Democrat                                    |
| `marryRepublican` | The respondent’s answer to how happy they would be if their child married a Republican                                  |
| `inPartyHappy`    | Indicator variable for whether the respondent would be happy if their child married a member of their own party         |
| `outPartyUnhappy` | Indicator variable for whether the respondent would be unhappy if their child married a member of the other major party |
| `polarized`       | Indicator variable for whether the respondent was effectively polarized                                                 |
| `strongPARTISAN`  | Indicator variable for whether the respondent identifies as a strong member of either major party                       |

In addition to these variables, I created an additional categorical variable, `reaction_value` , which quantifies the happiness levels on a scale of 0-4, where 0 is “Very unhappy” and 4 is “Very happy”. The purpose of converting this scale to numbers is that it allows for numerical analysis (such as averages), that are comparable among groups.

Additionally, it is important to note how `polarized` is defined.`Polarized` is an indicator variable that takes the value “TRUE” if the respondent responded “TRUE” to both `outPartyUnhappy` and `inPartyHappy`, and “FALSE” otherwise.

### Missing Data:

Another important element to the analysis of the data, is understanding where missing data is present. From the graph below, we see that missing data is significantly in the “rarely” treatment group. This means that the proportions of “rarely” are being inflated by missing data. However, when I calculate the proportions of entries in each treatment group, with and without NA’s, there is no discrepancy. The following analyses include all data.

<img src="staticunnamed-chunk-3-1.png" width="672" />

## Marry Republican Reactions:

First, I considered the different reactions to “marry republican” for strong/weak partisans. The reason for looking at just “marry republican” not “marry democrat” is that no student self-reported being republican, and only 4 lean toward the republican party. Although, I do filter the data to only consider Democrats.

<img src="staticunnamed-chunk-5-1.png" width="672" />

<img src="staticunnamed-chunk-8-1.png" width="672" />

<div id="ygnhavuita" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#ygnhavuita table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
&#10;#ygnhavuita thead, #ygnhavuita tbody, #ygnhavuita tfoot, #ygnhavuita tr, #ygnhavuita td, #ygnhavuita th {
  border-style: none;
}
&#10;#ygnhavuita p {
  margin: 0;
  padding: 0;
}
&#10;#ygnhavuita .gt_table {
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
&#10;#ygnhavuita .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}
&#10;#ygnhavuita .gt_title {
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
&#10;#ygnhavuita .gt_subtitle {
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
&#10;#ygnhavuita .gt_heading {
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
&#10;#ygnhavuita .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#ygnhavuita .gt_col_headings {
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
&#10;#ygnhavuita .gt_col_heading {
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
&#10;#ygnhavuita .gt_column_spanner_outer {
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
&#10;#ygnhavuita .gt_column_spanner_outer:first-child {
  padding-left: 0;
}
&#10;#ygnhavuita .gt_column_spanner_outer:last-child {
  padding-right: 0;
}
&#10;#ygnhavuita .gt_column_spanner {
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
&#10;#ygnhavuita .gt_spanner_row {
  border-bottom-style: hidden;
}
&#10;#ygnhavuita .gt_group_heading {
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
&#10;#ygnhavuita .gt_empty_group_heading {
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
&#10;#ygnhavuita .gt_from_md > :first-child {
  margin-top: 0;
}
&#10;#ygnhavuita .gt_from_md > :last-child {
  margin-bottom: 0;
}
&#10;#ygnhavuita .gt_row {
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
&#10;#ygnhavuita .gt_stub {
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
&#10;#ygnhavuita .gt_stub_row_group {
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
&#10;#ygnhavuita .gt_row_group_first td {
  border-top-width: 2px;
}
&#10;#ygnhavuita .gt_row_group_first th {
  border-top-width: 2px;
}
&#10;#ygnhavuita .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#ygnhavuita .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}
&#10;#ygnhavuita .gt_first_summary_row.thick {
  border-top-width: 2px;
}
&#10;#ygnhavuita .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#ygnhavuita .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#ygnhavuita .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}
&#10;#ygnhavuita .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}
&#10;#ygnhavuita .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}
&#10;#ygnhavuita .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#ygnhavuita .gt_footnotes {
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
&#10;#ygnhavuita .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#ygnhavuita .gt_sourcenotes {
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
&#10;#ygnhavuita .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#ygnhavuita .gt_left {
  text-align: left;
}
&#10;#ygnhavuita .gt_center {
  text-align: center;
}
&#10;#ygnhavuita .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}
&#10;#ygnhavuita .gt_font_normal {
  font-weight: normal;
}
&#10;#ygnhavuita .gt_font_bold {
  font-weight: bold;
}
&#10;#ygnhavuita .gt_font_italic {
  font-style: italic;
}
&#10;#ygnhavuita .gt_super {
  font-size: 65%;
}
&#10;#ygnhavuita .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}
&#10;#ygnhavuita .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}
&#10;#ygnhavuita .gt_indent_1 {
  text-indent: 5px;
}
&#10;#ygnhavuita .gt_indent_2 {
  text-indent: 10px;
}
&#10;#ygnhavuita .gt_indent_3 {
  text-indent: 15px;
}
&#10;#ygnhavuita .gt_indent_4 {
  text-indent: 20px;
}
&#10;#ygnhavuita .gt_indent_5 {
  text-indent: 25px;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_heading">
      <td colspan="2" class="gt_heading gt_title gt_font_normal gt_bottom_border" style>P-Values for Each Treatment Group</td>
    </tr>
    &#10;    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="Treatment">Treatment</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="P.Value">P.Value</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td headers="Treatment" class="gt_row gt_left">Control</td>
<td headers="P.Value" class="gt_row gt_right">0.008570627</td></tr>
    <tr><td headers="Treatment" class="gt_row gt_left">Rarely</td>
<td headers="P.Value" class="gt_row gt_right">0.076467727</td></tr>
    <tr><td headers="Treatment" class="gt_row gt_left">Frequently</td>
<td headers="P.Value" class="gt_row gt_right">0.274335643</td></tr>
  </tbody>
  &#10;  
</table>
</div>

<img src="staticunnamed-chunk-12-1.png" width="672" />
