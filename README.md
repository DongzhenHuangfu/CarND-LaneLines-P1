# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

In this project, I design a programm to recognize lane line automatically, which is useful for driverless driving.

Instructions
---

The function can operate one the pictures or videos.

To operate on the different image in the template _test_images_, just change the parameter `i` in `[5]` according to the list in `[4]`.

To operate on the different video in the template _video_images_, just run the code. If you want to operate it on the other video, you may:

1. save the video in the template _video_images_
2. use the same way like `[8]`, `[9]` shown

There are some functions which have the similar names, like `draw_line` and `draw_line1`, the difference between these functions are the different method they are using.

Further information can be found in the [writeup](./writeup.md)

List of files
---

1. examples: some example for checking
2. test_image: images for testing
3. test_image_output: output for the test of images
4. video_image: videos for testing
5. test_image_output: output for the test of videos
6. open.bat: quick way to open the .ipynb file
7. P1.ipynb: code file
8. P1.html: code file containing results
9. writeup.md: brief intruduction to the code

Notice
---

This programm is only suitable for the case, that the camera is on the proper position of the car like the test image or video show. But it's enough for the most case.

Further, the detectable lane lines must be straight, or at least almost straight in front of the car. 