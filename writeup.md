# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

I did not modify the draw_lines() function. Instead, I make sure its arguments are left and right lanes.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied Gaussian blur and get edges by Canny algorithm. After that, I picked up lines using Hough Transformation and draw those lines to the image.

In order to draw a single line on the left and right lanes, I make sure arguments of draw_lines() are left and right lanes and no other lines.



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there are some other lines other than lane on the ground, they mess up the lane because I used the mean of slope. 

Another shortcoming could be during turning, large portion of the line is not straight and it messes up the mean of slope.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to clean up the lane list, for example, get rid of outliers slope.

Another potential improvement could be to keep track of lane slope. In reality, the slope of lane in camera should never have sudden change. In stead of stateless, the program can cache the slope of last moment and remove outlier slopes in the slope list.

