# Computer Vision - Assignment 2 - Report 
Paul Asquin, CentraleSupélec MSc in AI March 2019

## Introduction
This project aim was to develop a method to identify humans moving in front of a ground-fixed camera without using Deep Learning methods. In order to make such think possible, we had to work extensively with "classical techniques" in computer vision, and take advantage of the OpenCV library.

We will consider our project having, as input, the list of images where want to find humans, and as output, an list of shape (number_of_frame, id_of_box_in_the_frame, box boundaries), that will describe where are humans in the succession of images.

## Data pipeline
The most important point of this report is to present the data pipeline and how it ends up achieving the person recognition: here is the detailed process.

### Background  substraction
![enter image description here](https://ibb.co/PMcWGfn)
### Get contours

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
eyJoaXN0b3J5IjpbLTE4NzIxMzY4NzYsLTExMjQyODUyODAsLT
c1ODk4ODgzMF19
-->