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
For this prediction task, we decided to implement a OneVsRestClassifier with a RandomForestClassifier as the underlying model.This option has proven to be quite effective in our predictions.

The obtained AUC values equal to 1 suggest that our model perfectly predicts the appropriate regions for futur stars most suited for the Indian or Asian movie industries. For people well-suited for the European and North American film industries are generally accurately identified by the model with AUCs respectively equal to 0.92 and 0.96.

<div style="display: flex; align-items: center;">

  <div style="flex: 2;">
    <img src="plots/model_ROC_curves.png" style="width: 100%;">
  </div>

  <div style="flex: 1; font-size: 10px;">
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
  </div>

</div>

For a deeper understanding of how this model classifies our actors, we can examine the importance assigned to each feature, as indicated by the model itself (here are the first ten). The most influential feature is revenue. Indeed, there is a distinct variation in revenue distribution among different regions. Additionally, we observe that the other significant features align with the most prevalent ethnicities in our four distinct regions.

<img src="plots/revenue_distribution_ttest" style="width: 100%;">

This Random forest classifier is particularly performant due to the fact that, during the pre-processing, we selectively retain only the few most popular ethnicities of each region to train our model. The high specificity of certain regions' ethnicities facilitate the prediction task.

For instance, in Indian films, only three ethnicities are represented, and two of them are exclusively associated with Indian movies, creating a highly influential feature. In contrast, actors linked to Europe and North America exhibit greater diversity, potentially contributing to the model's challenges in accurately predicting these regions. 
