## A. Convolutional horses and humans
1. Describe the ImageDataGenerator() command and its associated argument. 
What objects and arguments do you need to specify in order to flow from the directory to
the generated object? What is the significance of specifying the target_size = as it
relates to your source images of varying sizes? What considerations might you
reference when programming the class mode = argument? How difference exists
when applying the ImageDataGenerator() and .flow_from_directory() commands
to the training and test datasets?

The ImageDataGenerator() is a function that will auto label images based on the directory name. The argument to resize the image is a normalization method where each channel is divided by 255 to be in the [0, 1] range in the example. To flow from the directory to the generated image we need a source directory, to resize the image, the batch size for the training or validation generator, and binary labels. The importance of specifying the target_size to the source images of varying classes is because it is not guaranteed that all the images will be the same size. When programming the class mode, it is important to keep in mind how many classes you have. Because the example only had two classes, the argument was set to be binary. When applying the ImageDataGenerator() and .flow_from_directory() commands to the training and test datasets, it is very similar. The only difference is that for the testing set we create a validation generator and point it at the validation directory. 


2. Describe the model architecture of the horses and humans CNN as you have
specified it. Did you modify the number of filters in your Conv2D layers? 
How do
image sizes decrease as they are passed from each of your Conv2D layers to your
MaxPooling2D layer and on to the next iteration? Finally, which activation function
have you selected for your output layer? What is the significance of this argument’s
function within the context of your CNN’s prediction of whether an image is a horse
or a human? What functions have you used in the arguments of your model
compiler?

The model architecture of the horses and humans CNN has convolutional layers and a flatten layer to feed the results into the densely connected layers. In the densely connected layers, both relu and sigmoid arguments are used. The relu function is to make sure that if an output of a neuron is less than 0, set it to 0. Softmax is in the last layer so that the output of our network will be a single scalar between 0 and 1, making sure that the probability that the current image is class 1. 

We did modify the number of filters in the Conv2d layers. 


## B. Regression
1. Using the auto-mpg dataset (auto-mpg.data), upload the image where you used the
seaborn library to pairwise plot the four variables specified in your model. Describe
how you could use this plot to investigate the co-relationship amongst each of your
variables. Are you able to identify interactions amongst variables with this plot?
What does the diagonal access represent? Explain what this function is describing
with regarding to each of the variables.

![](https://user-images.githubusercontent.com/67920289/87844096-b883b180-c887-11ea-96dd-89ebd59daa79.png)

Using the graphs, we can see the differences in how accurate two variables are to each other. Referring to the linear regression of the scatter plots, we can use these plots to analyze how much impact one variable has on another. The diagonal access (I assume that diagonal access means diag_kind) determines the kind of plot for the diagonal subplot. After looking it up, I believe diag_kind="kde" means to change bar plots into line graphs. (https://etav.github.io/python/pairs_plot_python_seaborn.html) 


2. After running model.fit() on the auto-mpg.data data object, you returned the
hist.tail() from the dataset where the training loss, MAE & MSE were recorded as
well as those same variables for the validating dataset. 
What interpretation can you
offer when considering these last 5 observations from the model output? Does the
model continue to improve even during each of these last 5 steps? Can you include
a plot to illustrate your answer? Stretch goal: include and describe the final plot that
illustrates the trend of true values to predicted values as overlayed upon the
histogram of prediction error. 

My interpretation of the last 5 observations from the model output is that the loss fluctuates a little bit, but ultimately decreases to reach a loss score of 2.487. The validation loss decreases overall as well, but it is much higher than the loss at 9.370. The difference implies that the model is overfit. The Mean Absolute Error and the Mean Square Error score but both decrease showing how the model is becoming more accurate. 

![](https://user-images.githubusercontent.com/67920289/87844752-7ca01a80-c88e-11ea-9e4d-33b8726f7aeb.png)

![](https://user-images.githubusercontent.com/67920289/87844759-94779e80-c88e-11ea-9dce-c605f5b05db3.png)


## C. Overfit and underfit
1. What was the significance of comparing the 4 different sized models (tiny, small,
medium, large)? Can you include a plot to illustrate your answer?

Because the simplist way to avoid overfitting is to start with a small model, the different sizes show how big the size of the model impacts the accuracy of the model. (This is due to the small number of parameters which allow for each parameter to have influence over the model.) By testing different model sizes we can find the appropriate model size (TF: "it's best to start with relatively few layers and parameters, then begin increasing the size of the layers or adding new layers until you see diminishing returns on the validation loss."). 

![](https://user-images.githubusercontent.com/67920289/87844815-3ac3a400-c88f-11ea-9689-425c26af7cfb.png)
