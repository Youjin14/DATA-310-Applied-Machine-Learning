## 1. What is TF Hub?  How did you use it when creating your script for “text classification of movie reviews”?

On the official TensorFlow website, TF Hub is defined as "a library for the publication, discovery, and consumption of reusable parts of machine learning models." (https://www.tensorflow.org/hub) In the script for text classification of movie reviews, TF Hub was used for transfer learning. For the example, TensorFlow Hub was used to call a pre-trained text embedding model to test the data. 


## 2. What are the optimizer and loss functions?  How good was your “text classification of movie reviews” model?

The loss function measures how accurate the model is during training. An optimizer function is how the model is updated based on the data it sees and its loss function. The text classification of movie reviews model returned a loss of 0.313, and an accuracy of 0.866. 

## 3. In “text classification with preprocessed text” you produced a graph of training and validation loss.  Add the graph to this response and provide a brief explanation. 

https://user-images.githubusercontent.com/67920289/87259182-669dee80-c477-11ea-8458-926be6bd4abe.png

The graph shows how as we process the model more the loss function decreases (which means the model is becoming more accurate). The training model may be more accurate with a lower loss over time in comparison to the validation loss. (https://www.kaggle.com/c/tgs-salt-identification-challenge/discussion/62261) Loss is calculated base on the train set, val_loss is calculated base on the validation set. The validation loss is the value of cost function for your cross-validation data and loss is the value of cost function for your training data. (https://datascience.stackexchange.com/questions/25267/keras-difference-beetween-val-loss-and-loss-during-training) 

## 4. Likewise do the same for the training and validation accuracy graph

https://user-images.githubusercontent.com/67920289/87259769-aa92f280-c47b-11ea-93f6-40b59aa8bd7b.png

The graph shows how as we process the model more (more epochs) the accuracy increases. The accuracy for the training data is higher than the validation set. I also believe that the training and validation accuracy graph is the inverse of the training and validation loss. (as increased loss = decreased accuracy). The accuracy keeps increasing because the model is finding better parameters.




