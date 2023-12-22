---
layout: post
title: Movies genre
---

Joléa's background eccompass experience in multiple genres, displaying equal adeptness in portraying a tormented character in an art-house film as she does embodying the effervescent lead in a romantic comedy. However, she seeks clarity on where she's most likely to secure consistent roles and establish herself across various movies. Her aspiration is to specialize in a single genre, aiming to become one of its illustrious figure. How can she strategically pivot and sharpen her acting skills to achieve this goal?
To answer this question, we aim to find the movie genres which are the most prominent accross the different geographical regions

### Exploring cinematic diversity wolrdwide
The dataset offered a rich array of movie genres, including highly specific and distinct ones. To enhance the analysis' meaning, the initial movie genres were grouped into broader categories, covering multiple *sub-genres*. This clustering process utilized pre-existing word embeddings and clustering techniques.
Additionally, movies accounting for less than 2% of the total collection were consolidated under an *Others* category to simplify of representation of this huge variety of genres.
Finally, it's important to note that a movie can fall into multiple genres, resulting in proportions that don't necessarily sum up to one.

Let's thus have an comprehensive look at the variety of genres in our different geographical areas, as well as their prevalence.
![genres](plots/genres_wordcloud.png)

The diversity in genres is remarkable! Now, let's center our attention on the top five genres within each region. These genres might offer Jolea a more promising career trajectory and stable job opportunities.

<iframe src="plots/top_5_movie_genres.html" title="Top 5 movie genres" style="width: 100%; height: 100%;"></iframe>

These findings provide only a condensate of our data, that is spanning almost a century of movies. Yet, do the most prolific movie genres today mirror those from two decades ago? Are there indications of emerging genres in recent years? Let's delve deeper into the data to scrutinize the evolution of the top movie genres over time. From now on, we will exclude the 'Others' category, as it doesn't contribute meaningful insights into specific movie genres within this context.

### Genre trends through the ages

<iframe src="plots/movie_genres_over_years.html" title="Evolution of movie genres" style="width: 100%; height: 100%;"></iframe>

In general, comedy-drama (or simply *drama*) remains steadfast as one of the top two movie genres. It appears to offer Jolea a stable career path teeming with opportunities. This holds true regardless of her chosen work location, leaving no doors closed to her.
However, does she have ample space in this genre as a woman? Is there a particular region more inclined to embrace her?  Exploring gender representation within this specific movie genre across our four geographical regions will shed light on these crucial questions.

### Drama's gender portrait
Men occupy roughly 60% of roles in the drama cinematic industry, maintaining this majority across all geographical areas. Additionally, actresses consistently tend to be younger than actors across all regions. Time is of the essence, Jolea—your career won't wait! Unless it can in some specific places?

![gender_drama](plots/gender_drama.png)

Let's see if there is variation in age distribution across geographical regions for actresses.

![age_drama](plots/age_comparison_drama.png)
While statistical significance exists in age differences across regions, the practical impact on career opportunities might not be as pronounced as initially inferred...  On side note though, India might not offer the most favorable environment to conclude a career...
