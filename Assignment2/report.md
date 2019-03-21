# Computer Vision - Assignment 2 - Report 
Paul Asquin, CentraleSupélec MSc in AI March 2019

## Introduction
This project aim was to develop a method to identify humans moving in front of a ground-fixed camera without using Deep Learning methods. In order to make such think possible, we had to work extensively with "classical techniques" in computer vision, and take advantage of the OpenCV library.

We will consider our project having, as input, the list of images where want to find humans, and as output, an list of shape (number_of_frame, id_of_box_in_the_frame, box boundaries), that will describe where are humans in the succession of images.

## Data pipeline
The most important point of this report is to present the data pipeline and how it ends up achieving the person recognition: here is the detailed process.

### Background  substraction
![Background substraction](https://i.ibb.co/xY1gqR0/287.jpg =250x)
The OpenCV background substractor definitively is a great tool for this project: we created a _createBackgroundSubtractorMOG2_ object and applied images to it, allowing the object to generate masked-images such as the one displayed on the top. The background substractor puts in evidence the moving entities: indeed, we can see the pedestrians moving, but we have a lot of noise, from the tarp moving with the wind to the people shadows. We will have to combine this tool with others.

### Get contours
In order to work with the background-substracted images, we choose to use the _findContours method: after having resized and then applied a GaussianBlur

### Box merging

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
eyJoaXN0b3J5IjpbLTE1OTUwODYxNTcsLTExMjQyODUyODAsLT
c1ODk4ODgzMF19
-->