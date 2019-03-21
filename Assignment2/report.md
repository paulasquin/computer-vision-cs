# Computer Vision - Assignment 2 - Report 
Paul Asquin, CentraleSupélec MSc in AI March 2019

## Introduction
This project aim was to develop a method to identify humans moving in front of a ground-fixed camera without using Deep Learning methods. In order to make such think possible, we had to work extensively with "classical techniques" in computer vision, and take advantage of the OpenCV library.

We will consider our project having, as input, the list of images where want to find humans, and as output, an list of shape (number_of_frame, id_of_box_in_the_frame, box boundaries), that will describe where are humans in the succession of images.
## Project structure

### Box class
In order to work on this project, we decided to create our own "box" class. This object is made of simple attributes: the coordinates of the 

### Interface class

### SVM class

### General functions

## Data pipeline

### Background  substraction

### Get contours

### Box merging

### Box ratio filter

### HOG & SVM
#### Positive (human) dataset
#### Negative (background) dataset

#### SVM Training

### Inertia consistency

## Outputs

## Pros, cons and possible improvements
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1NzIyMjcxMCwtMTEyNDI4NTI4MCwtNz
U4OTg4ODMwXX0=
-->