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

Sometimes, the same person can be cut in multiple contours: legs, 

### Box ratio filter

### HOG & SVM
#### Positive (human) dataset
#### Negative (background) dataset

#### SVM Training

### Inertia consistency

## Project structure

### Box class
In order to work on this project, we decided to create our own _Box_ class. This object is made of simple attributes: the value of minimum x, minimum y, maximum x, maximum y that are describing the boundaries of the box. We also have implemented a _is_overlap_ method, taking a _Box_ as parameters. This function will check if the two boxes are overlapping. These lines was a quick introduction to the kind of OOP structure we applied. It may look quite obvious, thus we will be pass the presentation of such details.

### Interface class
This class is held to generate the dataset

### SVM class

### General functions

## Outputs

## Pros, cons and possible improvements
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzU5MDgxNDY0LDYzODI5NTczLC0xMTI0Mj
g1MjgwLC03NTg5ODg4MzBdfQ==
-->