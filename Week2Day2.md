## Question 1:
Last week you did an exercise where you manually applied a 3x3 array as a filter to an image of two people ascending an outdoor staircase.  Modify the existing filter and if needed the associated weight in order to apply your new filters to the image 3 times.  Plot each result, upload them to your response, and describe how each filter transformed the existing image as it convolved through the original array and reduced the object size.  What are you functionally accomplishing as you apply the filter to your original array (see the following snippet for reference)?  Why is the application of a convolving filter to an image useful for computer vision?  Stretch goal: instead of using the misc.ascent() image from scipy, can you apply three filters and weights to your own selected image?  Again describe the results.

Filter #1: 
![](https://user-images.githubusercontent.com/67920289/88123397-d0657900-cb98-11ea-8cf8-9c73ef4ecc2c.png)

The first filter emphasized the horizontal lines in the image, and made the image more darker. 

Filter #2:
![](https://user-images.githubusercontent.com/67920289/88123436-e4a97600-cb98-11ea-9356-d96084c7d05f.png)

Undergoing another filter with a new weight of 1.0, there is a stronger focus on the horizontal lines than the original and first filtered image. 

Filter #3:
![](https://user-images.githubusercontent.com/67920289/88123477-f428bf00-cb98-11ea-8af0-e9035ae5dac9.png)

The third filter had a changed weight of 2.0, and the filter emphasized the horizontal lines even more. There is a stark contrast in black and white to the lines. 

When applying the filter to the orginial array, a few processes occur. First, every pixel of the image is scanned and looked at all together with its neighboring pixels (each pixel has a value). Then, we multiply out the values of the pixels with the equivalent weights defined by the filter. Convoling filters are important when analyzing an image through computer vision because it processes the image down to its raw features. After isolating abstract features of an image, a computer can better learn which label to assign new images with similar or different features.


## Question 2:
Another useful method is pooling.  Apply a 2x2 filter to one of your convolved images, and plot the result.  In effect what have you accomplished by applying this filter?  Can you determine from the code which type of pooling filter is applied, and the method for selecting a pixel value (see the following snippet)?  Did the result increase in size or decrease?  Why would this method be method?  Stretch goal:  again, instead of using misc.ascent(), apply the pooling filter to one of your transformed images.




## Question 3:
The lecture for today (Coding with Convolutional Neural Network) compared the application of our previously specified deep neural network with a newly specified convolutional neural network.  Instead of using the fashion_MNIST dataset, use the mnist dataset (the hand written letters) to train and compare your DNN and CNN output. Were you able to improve your model by adding the Conv2D and MaxPooling2D layers to your neural network?  Plot the convolutions graphically, include them in your response and describe them.  Edit the convolutions be changing the 32s to either 16 or 64 and describe what impact this had on accuracy and training time.  What happens if you add more convolution layers?



