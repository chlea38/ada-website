---
layout: post
title: Modelling success
---

Joléa is among many "aspiring actors" wondering which is the most suitable region for their careers. This is why she asked ADAventurer to generate a prediction model. The goal of this model would be to predict which region is best fitted for a given actor based on:
- The desired income
- The prefered movie genre
- Ethnicity
- Gender

### Data pre-processing
The data preprocessing was the major challenge to create this predictive model. The labeled dataset links individual actors with their corresponding features to the region in which they predominantly appeared in movies. The major point was to creat a balanced data frame: balanced between the different features between the training and the testing set of each region and also balanced between the four regions.

In summary, here's what we did to achieve this:
- To address the imbalance caused by highly sparse features (due to diverse and specific ethnicities and movie genres), we retained only the most prevalent ethnicities and movie genres for each region.
- We performed upsampling on both the training and testing sets for each region before merging them.

And ... AbracADAbra! We now have a balanced dataset ready for model training.

### A performant model

<img src="plots/model_ROC_curves.png" alt="Connections distribution" style="width: 100%;">

<table>
  <thead>
    <tr>
      <th>Feature</th>
      <th>Average Importance</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Revenue</td>
      <td>0.165</td>
    </tr>
    <tr>
      <td>Indian person</td>
      <td>0.140</td>
    </tr>
    <tr>
      <td>Koreans</td>
      <td>0.119</td>
    </tr>
    <tr>
      <td>African Americans</td>
      <td>0.070</td>
    </tr>
    <tr>
      <td>English people</td>
      <td>0.062</td>
    </tr>
    <tr>
      <td>Japanese people</td>
      <td>0.044</td>
    </tr>
    <tr>
      <td>Honkongers</td>
      <td>0.042</td>
    </tr>
    <tr>
      <td>Jewish people</td>
      <td>0.034</td>
    </tr>
    <tr>
      <td>French</td>
      <td>0.032</td>
    </tr>
  </tbody>
</table>
