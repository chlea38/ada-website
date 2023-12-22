---
layout: post
title: Movies genre
---

Joléa's background eccompass experience in multiple genres, displaying equal adeptness in portraying a tormented character in an art-house film as she does embodying the effervescent lead in a romantic comedy. However, she seeks clarity on where she's most likely to secure consistent roles and establish herself across various movies. Her aspiration is to specialize in a single genre, aiming to become one of its illustrious figure. How can she strategically pivot and sharpen her acting skills to achieve this goal?
To answer this question, we aim to find the movie genres which are the most prominent accross the different geographical regions

## Exploring cinematic diversity wolrdwide

The dataset offered a rich array of movie genres, including highly specific and distinct ones. To enhance the analysis' meaning, the initial movie genres were grouped into broader categories, covering multiple _sub-genres_. This clustering process utilized pre-existing word embeddings and clustering techniques.
Additionally, movies accounting for less than 2% of the total collection were consolidated under an _Others_ category to simplify of representation of this huge variety of genres.
Finally, it's important to note that a movie can fall into multiple genres, resulting in proportions that don't necessarily sum up to one.

That said, let's delve into the diverse tapestry of genres across various regions. What better way to get an overview of their prevalence than using a word cloud?
![genres](plots/genres_wordcloud.png)

The genre diversity stands out, even post-genre clustering and condensing lesser-represented genres into the 'Others' category. Interestingly, 'Others' remains notably substantial even after clustering, emphasizing numerous specific genre categories, albeit with fewer movies.

Among these categories, genres like _comedy drama_ emerge as particularly dominant. These genres could pave the way for Jolea's promising career path with more stable job opportunities. Let's thus shift our focus to the top five genres within each region: which are they, and what proportion of movies belong to those categories?

![genres_top_5](plots/top_5_movies_genres.png)
Indeed, comedy drama consistently holds a spot in the top two across all regions! We will sometimes evoke this cluster as _drama_ in the following steps, as it encompass both drama and related genres. Dominance of other genres varies across different regions.
However, these findings provide only a single point condensate of our data, that is spanning almost a century of movies. Yet, do the most prolific movie genres today mirror those from two decades ago? Did some of the top genres only emerged in recent years? Let's explore the data further to examine how the top movie genres have evolved over time. For this analysis, we'll exclude the 'Others' category, which doesn't provide significant insights into specific movie genres in this context.

## Genre trends through the ages

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Image Selector</title>
    <style>
        #imageContainer {
            text-align: center;
            margin-top: 20px;
        }
        #imageSelector {
            border-radius: 8px;
            padding: 8px;
            border: 1px solid #ccc;
            font-size: 16px;
            margin-bottom: 20px;
        }
        .hidden {
            display: none;
        }
        .caption {
            margin-top: 10px;
            font-style: italic;
        }
    </style>
</head>
<body>

<div id="imageContainer">
    <label for="imageSelector">Region: </label>
    <select id="imageSelector" onchange="showSelectedImage()">
        <option value="1">Asia</option>
        <option value="2">Europe</option>
        <option value="3">India</option>
        <option value="4">Northen America</option>
    </select>
    <img id="1" class="to-be-hidden2" src="plots/genre_time_1.png" alt="Image 1">
    <div id="Caption1" class="caption to-be-hidden2">
    </div>
    <img id="2" class="to-be-hidden2 hidden" src="plots/genre_time_2.png" alt="Image 2">
    <div id="Caption2" class="caption hidden to-be-hidden2">
    </div>
    <img id="3" class="to-be-hidden2 hidden" src="plots/genre_time_3.png" alt="Image 3">
    <div id="Caption3" class="caption hidden to-be-hidden2">
    </div>
    <img id="PROPN" class="to-be-hidden2 hidden" src="plots/genre_time_4.png" alt="Image 4">
    <div id="Caption4" class="caption hidden to-be-hidden2">
    </div>
</div>

<script>

    function showSelectedImage() {
        // Hide all images and captions
        var elements = document.querySelectorAll('.to-be-hidden2');
        elements.forEach(function (element) {
            element.classList.add('hidden');
        });

        // Show the selected image and caption
        var selectedImageId = document.getElementById('imageSelector').value;
        var selectedImage = document.getElementById(selectedImageId);
        var selectedCaption = document.getElementById('Caption'+selectedImageId);
        
        if (selectedImage && selectedCaption) {
            selectedImage.classList.remove('hidden');
        }
    }
</script>

</body>
</html>

In general, drama remains steadfast as one of the top movie genres over the years. It has shown resilience in remaining prolific across various periods, presenting Jolea with a reliable career path rich in opportunities without the risk of fading away. This holds true regardless of her chosen work location, leaving no doors closed to her.
Nevertheless, one critical question arises: will she find ample space in this genre as a woman? Might a specific region be more receptive to her presence? Exploring gender representation within this specific movie category across our four geographical regions will help shed light on these crucial questions.

## Drama's gender portrait

We can tackle this inquiry through two approaches: What is the proportion of actresses in the drama films? What age tend to have actors and actresses when they perform in such film?
Let's see how this looks in our different geographical areas !
![gender_drama](plots/gender_drama.png)

Men occupy roughly 60% of roles in the drama cinematic industry, maintaining this majority across all geographical areas. Additionally, actresses consistently tend to be younger than actors, regardless of the region. Time is of the essence, Jolea—your career won't wait! Unless it can in some specific regions ?
Our one-way ANOVA revealed a _p-value below 0.05_, indicating that the mean age of actresses is different in at least one area. Post-hoc multiple testing using Tukey HSD will allow us to determine which region exhibit statistically significant different mean actresses age.

![age_drama](plots/age_comparison_drama.png)
The statistical analysis highlights significant mean age differences among every combination of regions. Yet, upon examining the box plots, the practical implications on career opportunities might not be as substantial as initially assumed. Indeed, differences of a few years might hold low significance in the grand scheme of life. One side note though, India might not offer the most favorable environment to conclude a career, exhibiting lower proportion of more mature actresses compare to other regions.

<div class="message">
  <h2>
    Recommendations for Joléa’s Career
  </h2>
  <p>
    CONTENT
    <br><br>
    CONTENT
  </p>
</div>
