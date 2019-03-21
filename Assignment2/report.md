# Computer Vision - Assignment 2 - Report 
Paul Asquin, CentraleSupélec MSc in AI March 2019

## Introduction
This project aim was to develop a method to identify humans moving in front of a ground-fixed camera without using Deep Learning methods. In order to make such think possible, we had to work extensively with "classical techniques" in computer vision, and take advantage of the OpenCV library.

We will consider our project having, as input, the list of images where want to find humans, and as output, an list of shape (number_of_frame, id_of_box_in_the_frame, box boundaries), that will describe where are humans in the succession of images.

## Data pipeline
The most important point of this report is to present the data pipeline and how it ends up achieving the person recognition: here is the detailed process.

### Background  substraction
![Background substraction image 287](https://i.ibb.co/xY1gqR0/287.jpg =250x)
The OpenCV background substractor definitively is a great tool for this project: we created a _createBackgroundSubtractorMOG2_ object and applied images to it, allowing the object to generate masked-images such as the one displayed on the top. The background substractor puts in evidence the moving entities: indeed, we can see the pedestrians moving, but we have a lot of noise, from the tarp moving with the wind to the people shadows. We will have to combine this tool with others.

### Get contours
In order to work with the background-substracted images, we have chosen to work with contours as a start for the box finding. After having resized and then applied a _GaussianBlur_ to the images in order to rub out the resize effects, we used the _findContours_. By drawing every contours in the same image, we can obtain results such as this one:

![Contour image 287](https://i.ibb.co/rM6ZL9t/download.png =250x)

Indeed, we managed to extract the humans, but we also extracted part of the tarp. We will create a first step of boxes with the results of this methods: 1 box correspond to the boundaries of 1 contour.

### Box merging

Sometimes, the same person can be cut in multiple contours: legs, bust, head... All split apart. In order to override that kind of problem, we have chosen to merge together two boxes that would be close one of the other, and stack one on the top of the other. This way, we are able to have 1 unique box per human, and still boxes with part of the tarp.

### Box ratio filter

Humans are not cubic: unless if pedestrians are crawling on the ground, they should be taller than larger. This way, we eject from or list of potential-human-boxes the ones that haven't a height/width ratio between 1 and 12. This lead to a score of ~0.18, that we want to improve with other techniques.

### HOG & SVM
We wanted to have a SVM guessing if what its seeing is a human or a random background sample. Then, we have implemented dataset generation function
#### Positive (human) and negative (background) dataset
We generated datasets made of 15px*30px images containing pedestrians in the first case, or random background element (as long as they don't overfit on humans) to train a binary SVM classifier. 

#### SVM Training
The SVM training has been done by appling first a _HOG_ transform to the images as a way the reduce the information in the input pipeline. This led also to flatten data, required for or SVM. At the end of the day, our SVM managed to reach awesome pedestrians recognition skills with an accuracy of 0.93 on the test set.

### Inertia consistency
We have implemented a function that was checking 

## Outputs

## Pros, cons and possible improvements
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQzNzU3ODQxNSw2MzgyOTU3MywtMTEyND
I4NTI4MCwtNzU4OTg4ODMwXX0=
-->