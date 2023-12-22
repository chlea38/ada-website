---
layout: post
title: The story behind plot summaries
---

Movie summaries contain a lot of hidden information about the film industry and should be examined with the same passion and attention as a Shakespeare manuscript. 
In this part, we will study and compare the hidden story behind the summaries of each of the 4 regions, across different topics.

## Reading between the lines

The textual data primarily encodes insights into how personna and common themes are portrayed across various movies. Uncovering such details from raw texts involves a nuanced approach, requiring a careful examination between the lines, coupled with the application of machine learning techniques. All plot summaries have undergone meticulous processing using the [Stanford Core NLP pipeline](https://stanfordnlp.github.io/CoreNLP/pipeline.html), and the outcomes of this processing are neatly presented in the accompanying dataset. Our current objective is to delve into this dataset to unearth the inherent narratives within each plot summary.

This supplementary dataset encompasses a wealth of features related to the text, including:
- In-depth analysis of each word in the text, revealing details such as its lemma (root word) or its part of speech (noun, adjective, etc.).
- Identification of dependencies between words within the same sentence.
- Recognition of co-references related to the same entity throughout the text.

Various techniques, such as extracting words linked to a common theme, assessing the sentiment embedded in sentences containing those words, and scrutinizing words frequently associated with theme-related terms, serve as diverse approaches to deciphering the subtleties within these movie plot summaries. Let's delve into what these features unveil about the movies.

## Female representation in plot summaries

Joléa considers female representation a pivotal theme, and the portrayal of women in text demands meticulous scrutiny. This careful examination aims to delineate the cinematic industry that aligns most seamlessly with the ideals and aspirations of our cherished actress. To this aim, we built a vocabulary of female-related words and will go throught the different resuts.


#### What are the most recurrent female-related words?

Each words of each summaries were analyzed to extract the most recurrent female-related words. In the image below, you can observe the differences of appearance of each words according to the region.

![tokens](plots/tokens_wordcloud.png)

If the prounoun "she" appears first in each region, the other words differs a bit according to the cinematic industries. Specifically, in the vocabulary of northern america, women seems to be depicted as someone's relative more than in other countries: "sister", "wife", "mother" or "daughter" or even "girlfriend" are dominent words. 

TODO


#### How are women depicted in the plot summaries?

NLP analysis of plot summaries is able to extract correferences, that is the words linked to female-related words in the summaries. Analysis of those correferences can provide a lot of insight on how women are represented in the different cinematic industries. Through the analysis of women portrayal on the screen, we can choose the most adequate for our dear Joléa.

In the following images, you can dive into the most recurrent words linked to females in the summaries. Correferences were separated into their part-of-speech (nouns, adjectives, verbs and proper nouns).

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
    <label for="imageSelector">Part of speech: </label>
    <select id="imageSelector" onchange="showSelectedImage()">
        <option value="NOUN">Nouns</option>
        <option value="ADJ">Adjectives</option>
        <option value="VERB">Verbs</option>
        <option value="PROPN">Proper nouns</option>
    </select>

    <img id="NOUN" class="to-be-hidden" src="plots/NOUN_correferences_wordcloud.png" alt="Image 1">
    <div id="NOUNCaption" class="caption to-be-hidden">
    The striking information that can be extracted from these correferences plots is the extensivity of the "husband" word within the three first areas, as if women should be defined by their mariage. Another important word is "home", which is first in Asia and Europe. 
    </div>

    <img id="ADJ" class="to-be-hidden hidden" src="plots/ADJ_correferences_wordcloud.png" alt="Image 2">
    <div id="ADJCaption" class="caption hidden to-be-hidden">
    Within adjectives correferences, we can observe mainly age-related, class-related, and emotions-related adjectives to describe womens.
    Specifically, young womens appears to be dominents in Asia and India, while for Europe and Northern America it's midde-adged women that dominates. 
    </div>

    <img id="VERB" class="to-be-hidden hidden" src="plots/VERB_correferences_wordcloud.png" alt="Image 3">
    <div id="VERBCaption" class="caption hidden to-be-hidden">
    TODO
    </div>

    <img id="PROPN" class="to-be-hidden hidden" src="plots/PROPN_correferences_wordcloud.png" alt="Image 4">
    <div id="PROPNCaption" class="caption hidden to-be-hidden">
    TODO
    </div>
</div>

<script>

    function showSelectedImage() {
        // Hide all images and captions
        var elements = document.querySelectorAll('.to-be-hidden');
        elements.forEach(function (element) {
            element.classList.add('hidden');
        });

        // Show the selected image and caption
        var selectedImageId = document.getElementById('imageSelector').value;
        var selectedImage = document.getElementById(selectedImageId);
        var selectedCaption = document.getElementById(selectedImageId + 'Caption');
        
        if (selectedImage && selectedCaption) {
            selectedImage.classList.remove('hidden');
            selectedCaption.classList.remove('hidden');
        }
    }
</script>

</body>
</html>

#### How sentences containing female-related words are perceived?

Sentiment analysis allows to get the general tone of sentences. We applied it on sentences containing words related to female.


![sentiment](plots/sentiment_scores.png)

If the vast majority of sentences show a neutral sentiment towards female, the second category to dominates is the negative sentiment, as if women were depicted neutraly or negatively in majority. The regions showing the biggest proportion of positive sentiment is India, followed by Europe. 


