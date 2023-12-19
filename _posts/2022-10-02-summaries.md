---
layout: post
title: The story behind plot summaries
---

Movie summaries contain a lot of hidden information about the film industry and should be examined with the same passion and attention as a Shakespeare manuscript. 
In this part, we will study and compare the hidden story behind the summaries of each of the 4 regions, across different topics.

## Female representation

<!DOCTYPE html>
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

        .hidden {
            display: none;
        }
    </style>
</head>
<body>

<div id="imageContainer">
    <img id="Asia" src="images/flore.jpg" alt="Image 1" class="hidden">
    <img id="Europe" src="images/flore.jpg" alt="Image 2" class="hidden">
    <img id="India" src="images/flore.jpg" alt="Image 3" class="hidden">
    <img id="Northern america" src="images/flore.jpg" alt="Image 4" class="hidden">

    <button onclick="showImage('image1')">Show Image 1</button>
    <button onclick="showImage('image2')">Show Image 2</button>
    <button onclick="showImage('image3')">Show Image 3</button>
    <button onclick="showImage('image4')">Show Image 4</button>
</div>

<script>
    function showImage(imageId) {
        // Hide all images
        var images = document.querySelectorAll('img');
        images.forEach(function (image) {
            image.classList.add('hidden');
        });

        // Show the selected image
        var selectedImage = document.getElementById(imageId);
        if (selectedImage) {
            selectedImage.classList.remove('hidden');
        }
    }
</script>

</body>
</html>


##

