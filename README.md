# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:

* Make a pipeline that finds lane lines on the road from each image


[//]: # (Image References)

[image1]: ./saved_images/grayscale.jpg "Grayscale"
[image2]: ./saved_images/blur_image.jpg "BlurImage"
[image3]: ./saved_images/canny_image.jpg "canny_image"
[image4]: ./saved_images/masked_edge.jpg "masked_edge"
[image5]: ./saved_images/combo.jpg "combo"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 

1. Converted the images to grayscale
2. Use gaussian blur with gaussian kernel 5
3. I use canny technic to find edges
4. Set region of 

		[[0, y], [x, y], [int(5.*x/9), int(5.*y/8)], [int(4.*x/9), int(5.*y/8)]]

5. use hough line techinc to find lines in the mased masked_edge
6. draw these line


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by only concider the lines with slop in [1/4, 3/4] or [-3/4, -1/4]

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]
![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]


### 2. Identify potential shortcomings with your current pipeline


shortcoming 1: because of lack of light or the lane lines are not clear, the roude might be not clear that we fail to detect any edge

shortcoming 2: if the roude has bad condition, might fail to detect edges of lane lines



### 3. Suggest possible improvements to your pipeline

use threshold to filter image in the first step
