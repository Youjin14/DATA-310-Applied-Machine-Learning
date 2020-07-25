## Question 1:
Write a Problem Statement. Introduce your topic, quantify its significance, and describe
the problem as a process. Identify and quantify significant obstacles to solving your
problem. Demonstrate why your topic is important, and why the obstacles associated
with your topic are significant both globally as well as within the context of your
selected application. Describe and analyze the complex nature of the process you are
investigating, including the system, the environment, agents and networks. Describe
and analyze scope, scale and hierarchy of processes and sub-processes. Describe and
analyze factors that contribute to quantified obstacles. Describe and analyze process
oriented causes-effect relationships.

Hello! I am still considering which topic I would like to further study. I am currently contemplating Dermatology and skin cancer/cancerous moles or acne.

## Question 2:
Describe your implementation of the cats & dogs exercise. How did you setup the data?
1. Which optimizer have you selected, and how might it compare to other possible
choices? (have a look at this site - https://towardsdatascience.com/understandingrmsprop-faster-neural-network-learning-62e116fcf29a)

The optimizer is RMSProp. RMSProp is an algorithm to help optimize the neural network. RMSProp compares to other optimization networks in that it is optimal for large data sets and large learning rates. On the other hand, Rprop tries to resolve the problem that gradients may vary widely in magnitudes. RProp looks at the sign of the gradient and adjusts so the weights are the same. Adagrad adds element-wise scaling of the gradient-based on the historical sum of squares in each dimension (we keep a running sum of squared gradients), and then adapt the learning rate by dividing it by that sum.RMSProp is great in how small the gradients do not matter. RMSprop scales the learning rate so the algorithms go through saddle points faster than most. (saddle point - A point of a function or surface which is a stationary point but not an extremum) 

2. Describe your selected loss function and it’s implementation. How is it effectively
penalizing bad predictions? (have a look at this site - https://
towardsdatascience.com/understanding-binary-cross-entropy-log-loss-a-visualexplanation-a3ac6025181a)

The loss function for this model is binary_crossentropy. Binary cross entropy is used for binary classifications and looks at the predicted probability associated with the true class of a point. We penalize bad predictions by taking the negative log of the probability (returns positive value). Cross entropy is a measure of the uncertainty associated with two distribution. (q(y) and p(y))

3. What is the purpose of the metric= argument in your model.compile() function? (look
here - https://keras.io/api/metrics/)

The purpose of the metric argument is to judge the performance of your model. (Similar to loss function but not used during training the model) Depending on the model used, we can look at the accuracy of a model, probabilities within a model, and different regression and classification measures.  

4. Plot the accuracy and loss results for both the training and test datasets. Include
these in your response. Assess the model and describe how good you think it
performed.

Accuracy Results:

![](https://user-images.githubusercontent.com/67920289/88448761-fd22c600-ce0e-11ea-9e09-6fb23236a46a.png)

Loss Results: 

![](https://user-images.githubusercontent.com/67920289/88448775-19266780-ce0f-11ea-8f76-e77718fd1c5f.png)

(red - training; blue - validation)

The graph shows a steady increase in accuracy and a decrease in loss when training the data. However, the validation model may have spiked up and down, the overall results reveal how the model did not match up to the accuracy of the training model but did have pretty good results (end accuracy of 0.8047 and loss of 0.5516). 

5. Use the model to predict 3 dog images and 3 cat images. Upload you images and
the prediction. How did your model perform in practice? Do you have any ideas of
how to improve the model’s performance?

![](https://user-images.githubusercontent.com/67920289/88448884-3445a700-ce10-11ea-804c-2ff9f726717d.jpg)

Result: cat1.jpg is a dog

![](https://user-images.githubusercontent.com/67920289/88448893-56d7c000-ce10-11ea-9534-6f690aef56c5.jpg)

Result: cat2.jpg is a cat

![](https://user-images.githubusercontent.com/67920289/88448899-6e16ad80-ce10-11ea-90f6-f387bdf6327d.jpg)

Result: cat3.jpg is a cat

![](https://user-images.githubusercontent.com/67920289/88449224-1af22a00-ce13-11ea-8fda-502d99ddfb7a.jpg)
This is a picture of my dog, Libby!

Result: IMG_5866.jpg is a dog

![](https://user-images.githubusercontent.com/67920289/88449006-702d3c00-ce11-11ea-9f61-b23bc7b23928.jpg) 

Result: dog2.jpg is a dog

![](https://user-images.githubusercontent.com/67920289/88449072-fd709080-ce11-11ea-8a87-d2240dabd6c9.jpg)

Result: dog3.jpg is a dog

A method of improving the model would be augmenting the images. For example, flipping the image, turning it upside down, to the side, and etc. This could help the model learn more features that would help differentiate between cat and dog rather than relying on the 2-D training images. 





