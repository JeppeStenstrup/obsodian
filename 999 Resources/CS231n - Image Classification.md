[[CS231n]]

[link](https://cs231n.github.io/classification/)

# Image Classification

## Motivation
The goal of image classification is to label a given image with one of a fixed set if labels. An example could be the given labels `{cat, dog, hat, mug}`, where the [[Image Classification Model|image classification model]] takes in an image, evaluates it, an assigns a probability score to each if the four labels, i.e. `{cat:82%, dog:15%, hat:2%, mug:1%}`.

## The image
What are the images in the image classification model's eyes? Number.

An image is made up of pixels, and those pixels have a mix of red, green, and blue (each with a value of 0-255), which means that for each pixel in a given image, there are 3 values; first layer all red values, second layer all green values, and third layer all blue values.

So an image is a three dimensional matrix, with the size if $\text{image width} \times \text{image height} \times 3$.

## Challenges
- Viewpoint variation
	- At which angle are we looking at the cat? Front, side, top, bottom?
- Scale variation
	- Is it filling out the whole frame or is it sitting on a fence in a little portion of the image?
- Deformation
	- Objects in images can be deformed, could be a cat lying funny, or a lens illusion, i.e. a wide angle lens where edges are stretched or skewed
- Occlusion
	- Maybe only part of the subject is visible in the frame, maybe only the cats head is visible
- Background clutter
	- Parts of the subject may blend into that surroundings
- Intra-class variation
	- The specified subject may be a very large group of objects, i.e. _chair_.
- ![[Pasted image 20220910204623.png]]

## Data-driven approach
The approach to teaching an AI to recognize specific objects in images is not like any other algorithm we've been taught in uni; it's more like how a child would learn.

We bombard the computer with as many pictures of the subjects as we can, and develop learning algorithms that, with iterations, pick up on visual cues of each class of subject.

This approach is called the "Data-driven approach", since it relies on first accumulating as much [[Training data|training data]] as possible, which consists of both the image, and the given subject class.

![[Pasted image 20220913171128.png]]

