# **Finding Lane Lines on the Road** 

## Writeup Template

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (picture with only one line in each side)

[image1]: ./test_images_output/oneline_solidWhiteCurve.jpg "Grayscale"

[//]: # (picture with many lines in each side)

[image2]: ./test_images_output/solidWhiteCurve.jpg "Grayscale"

---

### Reflection

### 1. Describe my pipeline. As part of the description, explain how my modified the draw_lines() function.

My pipeline consisted of 5 steps： 

First, I converted the images to grayscale, 

Then I use gaussian_blur to smooth the pciture and use canny for finding the edges

After that, I start to define the region that need to be worked on, at this point I used two ways.

1.just the same as I learned in the class, I defined one region to work on.
2.Cause in the challenging part there is too many noise in the region between two lines, so I 	defined two regions with each of them containg just one line, in the same time, I mmodified the function region_of_interest and also the function draw_lines. 

To make things easier, I added an input parameter in function hough_lines named method, when "method" is 1, it will use two regions(b), otherwise, it use only one region(a). In my code, every function with a name which follow character "1" after the origin name is for two regions.

Then I used Hough transformation and out put the pictures.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by the following steps:

1. calculate the angle of reach line in the lines with math.atan2()
2. kick out the line which is "not so verticle" by judging its angle and its x value on the bottom.
3. divide the lines into two groups by judging its angle a, lines with abs(a) < 0.5*pi are in the one group, others are in the one group. And in the meantime find the point with the lowest y value(on the uppest position).
4. calculating the average angle of each group
5. with the average angle and the uppest point I can draw one line from the uppest point to the bottom.

To show that, I output every photos, the photo with the name beginning with "oneline_" is is the output of only one line in each side. As an example you can see the pictures below:



If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]

![alt text][image2]

### 2. Identify potential shortcomings with my current pipeline


One potential shortcoming would be what would happen when there is too many noise, the line I draw in the will be really annoying, cause the average angle is not close to the traffic line anymore. 

Another shortcoming could be: the line I draw for the dashed traffic line will be very short sometimes, cause it fail to recognize the dashed traffic line which is far away with too shor length.

Further, if you look frame by frame in the challenging video you will find that, there is one part of the road, where the yellow line are hardly recognized, cause the gradient for the pixles are really low.


### 3. Suggest possible improvements to my pipeline

A possible improvement would be to make the line for the dashed traffic line more stable.

Another potential improvement could be to try to make the yellow line in the challenging video more clear.
