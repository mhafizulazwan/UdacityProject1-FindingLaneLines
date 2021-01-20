# **Finding Lane Lines on the Road** 
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps:

1. Converted the images to grayscale.

2. Detected edges using Canny Edge Detection method.

3. Selected a region of interest where this process is called masking.

4. Drew lines from the detected edges using Hough Transform.

5. Drew transparent lines on the original image.


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by 

differentiating the endpoints (x and y) of the right and left lines. To differentiate the endpoints, I 

utilized the gradient technique. If the gradient is positive, I saved the endpoints in a right line 

storage and if the gradient is negative, I saved the endpoints in a left line storage. With these left and 

right line storages in hand, I used np.polyfit() to compute the estimated slope and y-intercept of each 

line. Then, I used this information to draw (a single line) the right and left lines. 


Reader can run my ipython code to see the images in each step of the pipelines.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the light is not scattered as in the video of the optional challenge.

Another shortcoming could be to detect the lane lines even if it is not straight.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to further tuning the parameter especially on the Hough Transformation algorithm.

Another potential improvement could be to make the pipeline robust to any of the lane lines on the road.
