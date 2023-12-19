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

Joléa considers female representation a pivotal theme, and the portrayal of women in text demands meticulous scrutiny. This careful examination aims to delineate the cinematic industry that aligns most seamlessly with the ideals and aspirations of our cherished actress.

TODO: replace with the plots


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
    </style>
</head>
<body>

<div id="imageContainer">
    <label for="imageSelector">Area: </label>
    <select id="imageSelector" onchange="showSelectedImage()">
        <option value="Asia">Asia</option>
        <option value="Europe">Europe</option>
        <option value="India">India</option>
        <option value="NorthernAmerica">Northern America</option>
    </select>

    <img id="Asia" src="images/flore.jpg" alt="Image 1">
    <img id="Europe" src="images/flore.jpg" alt="Image 2" class="hidden">
    <img id="India" src="images/flore.jpg" alt="Image 3" class="hidden">
    <img id="NorthernAmerica" src="images/flore.jpg" alt="Image 4" class="hidden">
</div>

<script>
    // Show the first image initially
    document.getElementById('Asia').classList.remove('hidden');

    function showSelectedImage() {
        // Hide all images
        var images = document.querySelectorAll('img');
        images.forEach(function (image) {
            image.classList.add('hidden');
        });

        // Show the selected image
        var selectedImageId = document.getElementById('imageSelector').value;
        var selectedImage = document.getElementById(selectedImageId);
        if (selectedImage) {
            selectedImage.classList.remove('hidden');
        }
    }
</script>

</body>
</html>

