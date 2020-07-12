## Question 1: 
In the video, First steps in computer vision, Laurence Maroney introduces us to the
Fashion MNIST data set and using it to train a neural network in order to teach a
computer “how to see.” One of the first steps towards this goal is splitting the data into
two groups, a set of training images and training labels and then also a set of test
images and test labels. Why is this done? What is the purpose of splitting the data into
a training set and a test set?

The purpose of splitting the data into training and testing groups is to create a most accurate model. The process takes a portion of the overall data to train the neural network. Then we test the neural network on remaining data that it has never processed/seen before. A different way of explaining the train/test split would be saying that we have the answers to an equation that is not known yet. By training the network on a portion of the data, we can formulate a prediction of what the equation might be (training creates better links in the neural network from input to result where the combination of all the links is like the equation). Then we apply that predicted equation to the remaining testing data to see how accurate it is! If we used the training data to test the images and labels, the accuracy would be 100% correct because it is the same data used to create the "equation".

## Question 2: 
The fashion MNIST example has increased the number of layers in our neural network
from 1 in the past example, now to 3. The last two are .Dense layers that have
activation arguments using the relu and softmax functions. What is the purpose of each
of these functions. Also, why are there 10 neurons in the third and last layer in the
neural network.

The first layer of the neural network (Flatten) is used to translate the 28 x 28 data into a one-dimensional array that can be processed by the next layer. The two dense layers adda a layer of neurons. The purpose of the relu function is to make sure that if an output of a neuron is less than 0, set it to 0. This is because negative results can skew results downstream, canceling out positive outputs. Softmax is commonly seen in the last layer of the neural network if there are multiple categories. This is because when the final layer returns different probabilities for each class, Softmax will assign the highest probability to one, making it easier to find that class. The reason why there are 10 neurons in the last layer of the neural network is that there are 10 categories to assign each image. The 10 categories are different items of clothing. The job of each of the 10 neurons is to calculate the probability that a piece of clothing is for that particular class.

## Question 3:
In the past example we used the optimizer and loss function, while in this one we are
using the function adam in the optimizer argument and sparse_categoricalcrossentropy for the loss argument. How do the optimizer and loss functions operate
to produce model parameters (estimates) within the model.compile() function?

We compile an optimizer and loss function to build the model. The loss function measures the guessed answers against the known correct answers and measures how well or how badly it did. The loss function argument determines the quantity that a model should seek to minimize during training. It then uses the optimizer function to make another guess. The optimizer argument Adam implements the Adam algorithm to make another guess. "Adam optimization is a stochastic gradient descent method that is based on adaptive estimation of first-order and second-order moments" (https://keras.io/api/optimizers/). The loss argument, sparse_categoricalcrossentropy, is used because we want to provide labels as integers. An loss and optimizer function is needed to tweak the parameters used to calculate the probability of the class of an image.

(https://www.tensorflow.org/api_docs/python/tf/keras/losses/sparse_categorical_crossentropy,
https://keras.io/api/losses/probabilistic_losses/#sparsecategoricalcrossentropy-class)

## Question 4:
Using the mnist drawings dataset (the dataset with the hand written numbers with
corresponding labels) answer the following questions.
1. What is the shape of the images training set (how many and the dimension of
each)?
2. What is the length of the labels training set?
3. What is the shape of the images test set?
4. Estimate a probability model and apply it to the test set in order to produce the
array of probabilities that a randomly selected image is each of the possible numeric
outcomes (look towards the end of the basic image classification exercises for how
to do this — you can apply the same method applied to the Fashion MNIST dataset
but now apply it to the hand written letters MNIST dataset).
5. Use np.argmax() with your predictions object to return the numeral with the highest
probability from the test labels dataset.
6. Produce the following plot for your randomly selected image from the test dataset

After finding the number drawing dataset from this website, https://www.tensorflow.org/api_docs/python/tf/keras/datasets/mnist, I ran a similar code to the fashion mnist. I was unable to run it in Pycharm, but I was able to run it in Google CoLab. 
- There were a total of 60,000 training images. I was unable to find the dimensions directly, however, from the website http://yann.lecun.com/exdb/mnist/, I was able to find out that the dimensions are 28x28.
- The length of the labels training set is 60,000.
- The shape of the images test set is 10,000 training images and the same 28 x 28 dimensions.
- The probability model returned a 0.9778 accuracy in the results.
- The numeral with the highest probability from the test labels dataset was 7.
- 

- 
