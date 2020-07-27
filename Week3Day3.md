## A. Boosted Trees
1. What is a one-hot-encoded column and why might it be needed when transforming
a feature? Are the source values continuous or discrete?

A one-hot-encoded column encodes a categorical column/features to a one-code numeric array (0 & 1s). One-hot-encoding is needed to feed categorical data into the estimator. Additionally, converting information into numbers will help the network learn the importance of certain features and the network will be more adept at analizing the variables. 

Majority of the source values are despcriptive, such as gender of passenger (sex), siblings and partners aboard (n_siblings_spouses), Ffre passenger paid (fare), passenger's class on ship (class), which deck passenger was on (deck), which town passenger embarked from (embark_town), if the passenger was alone (alone). However, the numerical data is a mix of continuous and discrete data. Age is continuous (year, month, day, hour, ...) and fare is discrete ($7.50).

2. What is a dense feature? For example, if you execute example = dict(dftrain) and
then tf.keras.layers.DenseFeatures(your_features)(your_object).numpy(), how
has the content of your data frame been transformed? Why might this be useful?

A dense feature is a layer that produces a dense Tensor based on given feature_columns. At the first layer of the model, this column oriented data should be converted to a single Tensor. This layer can be called multiple times with different features. (https://www.tensorflow.org/api_docs/python/tf/keras/layers/DenseFeatures) Ultimately, the dense feature signals the presense or absense of data (for example: 0 = no data; 1 = data). 

The content of the data has changed in that the categorical feature column is now an array. (I am still not 100% sure about this.)

3. Provide a histogram of the probabilities for the logistic regression as well as your
boosted tree model. How do you interpret the two different models? Are their
predictions essentially the same or is there some area where they are noticeable
different. Plot the probability density function of the resulting probability predictions
from the two models and use them to further illustrate your argument. Include the
ROC plot and interpret it with regard to the proportion of true to false positive rates,
as well as the area under the ROC curve. How does the measure of the AUC reflect
upon the predictive power of your model?

![Linear Classifier](https://user-images.githubusercontent.com/67920289/88472852-5f4dfa80-cee5-11ea-9cb4-9142bf5d82e2.png)

![Predicted Probabilities for Boosted Tree Model](https://user-images.githubusercontent.com/67920289/88472708-d5e9f880-cee3-11ea-9605-15a6e468ae02.png)

The two graphs are pretty similar to each other. Both linear and boosted tree model are skewed right. However, a linear model would not be as accurate as the boosted trees due to how decision trees divide boundaries

![BT](https://user-images.githubusercontent.com/67920289/88507008-61798d00-cfa9-11ea-9fea-82097349d9d0.png)

The ROC plot show how accurate the predicted probabilities of different classes are. It would be ideal if the plot had a consistant true positive rate of 1.0. However, the ROC plot shows how the model was doing pretty well until it reached a false positive rate of 0.2 and the true positive rate slowed down. The area under the curve (AUC) is not a perfect 1.0, but I believe it is considerably higher than 0.0. This means that the model's predictions will be accurate most of the time. 

(https://stackabuse.com/understanding-roc-curves-with-python/,
https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc)

## B. Boosted Trees continued (with model understanding)
1. Upload your feature values contribution to predicted probability horizontal bar plot
as well as your violin plot. Interpret and discuss the two plots. Which features
appear to contribute the most to the predicted probability?

![Feature Value](https://user-images.githubusercontent.com/67920289/88507253-fe3c2a80-cfa9-11ea-94a8-8abdd5b956a8.png)

![Feature Value Violin](https://user-images.githubusercontent.com/67920289/88507284-1ad86280-cfaa-11ea-81c5-fd24bb5b4ce6.png)

For the predicted probabilities bar plot, the larger magnitude contributions have a larger impact on the model's prediction. Negative contributions indicate the feature value for this given example reduced the model's prediction, while positive values contribute an increase in the prediction. (TF Hub) The violin plot reveals the value of the predicted probability of the contribution of a variable of a specific example as well as the range. The two graphs show how sex, age, and class contributes the most to predicted probability for example 182. 

2. Upload at least 2 feature importance plots. Which features are the most important
in their contribution to your models predictive power?

![GFI](https://user-images.githubusercontent.com/67920289/88507780-32641b00-cfab-11ea-8b22-ac2ccf5a9960.png)

![PFI](https://user-images.githubusercontent.com/67920289/88507820-46a81800-cfab-11ea-88fe-cc868590d28f.png)

The two graphs agree that sex contributes greatly to the model's predictive power. The second most contributive feature differs based on the graph. This is because the two graphs measure different things. Fare has the second-largest difference in loss, while class had a greater evaluating model performance. 

Note: Gain-based feature importances measure the loss change when splitting on a particular feature, while permutation feature importances are computed by evaluating model performance on the evaluation set by shuffling each feature one-by-one and attributing the change in model performance to the shuffled feature.(TF Hub)


