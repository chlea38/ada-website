---
layout: post
title: The story behind plot summaries
---

Movie summaries contain a lot of hidden information about the film industry and should be examined with the same passion and attention as a Shakespeare manuscript. 
In this part, we will study and compare the hidden story behind the summaries of each of the 4 regions, across different topics.

## Female representation

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

