
**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 
* I converted the images to grayscale
* I used the Gaussian fliter for smoothing
* Use Canny function for lane line detection
* Selected the region where relat to Lane line detection
* Use Hough transformation to get the lane line data

In order to draw a single line on the left and right lanes, I modified the draw_lines() function:
* Scan all the lines which are detected by Hough transform
* Calculate the similar line slop to get the same direction lines' equation parameter(y=Ax+C) and end point(the farest point from car)
* Draw the line with particular equation parameter from end point to start point(which y=539)

### 2. Identify potential shortcomings with your current pipeline

* Cannot pass the chanllege video, I think one reason is that I didn't use color selection, so the tree and other car would effect the performance.(I have tried to add the colort selection, but the output line cannot match the image properly.)
* And another shortcoming is if the lane lines aren't in the center region, the line detection's performance also wil be effect.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to add correct color selection, and also do some tuning about region select and Hough transform parameter.
