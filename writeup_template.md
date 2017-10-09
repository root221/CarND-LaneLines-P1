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

My pipeline consisted of 6 steps. First, I converted the images to grayscale, then I remove the noise. Next, I apply canny to find the 
edges, then I keep only the region of interest. After that, I apply hough line transform to find lines, then I combine the lines with the origin image.


In order to draw a single line on the left and right lanes, I modified the draw_lines() function. First, separating line segments by their slope, then add the right line segments coordinate into right_lane_x , right_lane_y and left line segments coordinate into left_lane_x, left_lane_y.Next, find the equation of line of best fit for the points in the left_lane_x , left_lane_y list, and same for the right lane. Then, draw a single line on the left and right lanes according to the equation find previously.


Result image:

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be when there is other line one the lane.

Another shortcoming could be what if the lane isn't straight.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to only find vertical edge.

Another potential improvement could be maybe instead of fitting a line, try to fit Quadratic function.
