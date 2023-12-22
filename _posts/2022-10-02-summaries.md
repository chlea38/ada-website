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

A comprehensive analysis of the vocabulary used in each summary was conducted to identify the most recurrent words related to females. The visual representation highlights variations in the frequency of appearance across regions. 

![tokens](plots/tokens_wordcloud.png)

While the pronoun "she" consistently appears first in each region, other words differ slightly based on cinematic industries. Notably, in the Northern American vocabulary, women are often depicted in relational roles, with dominant words such as "sister," "wife," "mother," "daughter," and even "girlfriend."

#### How sentences containing female-related words are perceived?

To gauge the overall tone of sentences, sentiment analysis was applied to those containing words related to females. 

![sentiment](plots/sentiment_scores.png)

The results reveal that the majority of sentences exhibit a neutral sentiment towards females. Interestingly, the second most prevalent sentiment is negative, suggesting that women are predominantly portrayed neutrally or negatively. Notably, India stands out with the highest proportion of positive sentiment, followed by Europe.

#### How are women depicted in the plot summaries?

NLP analysis of plot summaries enables the extraction of correferences, referring to words associated with female-related terms within the summaries. Examining these correferences provides valuable insights into how women are portrayed across diverse cinematic industries. By scrutinizing the representation of women on screen, we can discern the most fitting roles for our esteemed actress, Joléa.

The accompanying images offer a detailed exploration of the most frequently occurring words linked to females in the summaries. Correferences have been categorized based on their part of speech, including nouns, adjectives, verbs, and proper nouns. This categorization allows for a more granular understanding of the linguistic elements shaping the portrayal of women in cinematic narratives.

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
        The noteworthy observation drawn from these reference plots is the prevalence of the term "husband" in the initial three regions, seemingly implying that women should be defined by their marital status. Another significant term is "home," ranking first in Asia and Europe, suggesting the perception of women as an integral part of domestic life. Notably, the term "kitchen" is discernible in Europe, reinforcing the persistent stereotype about women. <br>
        Delving into Joléa's values, we discern words like "leader" in Asia or "fighter" in India, aligning with the strong character of our actress.
    </div>

    <img id="ADJ" class="to-be-hidden hidden" src="plots/ADJ_correferences_wordcloud.png" alt="Image 2">
    <div id="ADJCaption" class="caption hidden to-be-hidden">
        Examining adjectival references reveals predominantly age-related, class-related, and emotion-related descriptors used to characterize women.
        Particularly, young women appear dominant in Asia and India, whereas middle-aged women take precedence in Europe and Northern America. <br>
        Women seem to be portrayed as strong and independent in Asia, as indicated by terms such as "successful," "battlefield," "anti-communist," and "criminal," portraying them not just as homemakers but as individuals fighting for their values. Joléa would appreciate this apparent strength. <br>
        Conversely, prevalent adjectives in Europe concerning women include "dead," "sick," "pet," "servitude," and even "suspicious." The same holds for Northern America with terms like "dead," "unobserved," "fanatical," "pregnant," and "useless."
        What actress would want to represent an industry casting women in such a degrading light? Certainly not Joléa.
    </div>

    <img id="VERB" class="to-be-hidden hidden" src="plots/VERB_correferences_wordcloud.png" alt="Image 3">
    <div id="VERBCaption" class="caption hidden to-be-hidden">
        Once again, Asia positions women in significant values-driven roles, with words like "participate," "escape," "happens," "want," and "hide-and-seek," portraying women as masters of their own destiny. <br>
        In contrast, India seems to depict women primarily as "housemaids" and "governesses," roles that do not align with Joléa's interests.
    </div>

    <img id="PROPN" class="to-be-hidden hidden" src="plots/PROPN_correferences_wordcloud.png" alt="Image 4">
    <div id="PROPNCaption" class="caption hidden to-be-hidden">
        Analyzing proper nouns related to females in summaries is intriguing as it allows us to determine if women are consistently linked to male characters. Across all regions, the prominent nouns include "father," "son," "ex-wife," "brother," and even "lover," all of which establish connections between women and men.
        
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

## A word for Joléa's carreer

In summarizing the comprehensive analyses conducted across linguistic elements, distinct patterns emerge in the portrayal of women across diverse regions. Nouns, such as "husband" and "home," underscore a perception of women tied to traditional domestic roles in Asia and Europe. Adjectives further illuminate regional distinctions, portraying Asian women as strong and independent, while Europe and Northern America lean towards more negative descriptors. Verbs reinforce these differences, emphasizing women's agency in Asia and traditional roles in India.

Joléa's values, evident in associated adjectives and verbs, align with the depiction of strong, independent women, especially in the Asian context. The consistent linkage of women to male figures in proper nouns underscores a prevailing theme of defining women in relation to men.

Expanding the analysis to include recurrent vocabulary and sentiment, the Northern American vocabulary emphasizes relational aspects of women's identities, with words like "sister" and "wife" prevailing. Sentiment analysis reveals a predominant neutral tone, with India and Europe standing out as exceptions with more positive portrayals.

Taken together, these insights underscore the nuanced and varied representation of women across different cultural contexts. The linguistic nuances and sentiment trends contribute to a deeper understanding of how cinematic industries shape societal perceptions of women. The findings prompt critical reflections on the potential societal impact of these portrayals and advocate for a more inclusive and empowering representation of women in media. Additionally, the ability to ADApt to evolving cultural narratives is crucial for fostering positive and diverse portrayals of women in the ever-changing landscape of media.