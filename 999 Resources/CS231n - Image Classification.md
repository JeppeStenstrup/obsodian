[[CS231n]]

[link](https://cs231n.github.io/classification/)

# Image Classification

## Motivation
The goal of image classification is to label a given image with one of a fixed set if labels. An example could be the given labels `{cat, dog, hat, mug}`, where the [[Image Classification Model|image classification model]] takes in an image, evaluates it, an assigns a probability score to each if the four labels, i.e. `{cat:82%, dog:15%, hat:2%, mug:1%}`.

## The image
What are the images in the image classification model's eyes? Number.

An image is made up of pixels, and those pixels have a mix of red, green, and blue (each with a value of 0-255), which means that for each pixel in a given image, there are 3 values; first layer all red values, second layer all green values, and third layer all blue values.

So an image is a three dimensional matrix, with the size if $\text{image width} \times \text{image height} \times 3$.