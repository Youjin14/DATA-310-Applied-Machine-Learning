## Question 1: 
In the video, First steps in computer vision, Laurence Maroney introduces us to the
Fashion MNIST data set and using it to train a neural network in order to teach a
computer “how to see.” One of the first steps towards this goal is splitting the data into
two groups, a set of training images and training labels and then also a set of test
images and test labels. Why is this done? What is the purpose of splitting the data into
a training set and a test set?

The purpose of splitting the data into training and testing groups is to create a model that is most accurate. The process takes
a portion of the overall data to train the neural network. Then we test the neural network on remaining data that it has never
processed/seen before. A different way of explaining the train/test split would be saying that we have the answers to an equation that is not known yet.
By training the network on a portion of the data, we are able to formulate a prediction of what the equation might be (training creates better links in the neural 
network from input to result where the the combination of all the links are like the equation). Then we apply that predicted equation to the remaining testing data to see ho accurate it is! If we used the training data to test the images and labels, the accuracy would be 100% correct because it is the same data used to create the "equation".

## Question 2: 
The fashion MNIST example has increased the number of layers in our neural network
from 1 in the past example, now to 3. The last two are .Dense layers that have
activation arguments using the relu and softmax functions. What is the purpose of each
of these functions. Also, why are there 10 neurons in the third and last layer in the
neural network.



