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
different.

Plot the probability density function of the resulting probability predictions
from the two models and use them to further illustrate your argument. Include the
ROC plot and interpret it with regard to the proportion of true to false positive rates,
as well as the area under the ROC curve. How does the measure of the AUC reflect
upon the predictive power of your model?

![Linear Classifier](https://user-images.githubusercontent.com/67920289/88472852-5f4dfa80-cee5-11ea-9cb4-9142bf5d82e2.png)

![Predicted Probabilities for Boosted Tree Model](https://user-images.githubusercontent.com/67920289/88472708-d5e9f880-cee3-11ea-9605-15a6e468ae02.png)

The two graphs are pretty similar to each other.


## B. Boosted Trees continued (with model understanding)
1. Upload your feature values contribution to predicted probability horizontal bar plot
as well as your violin plot. Interpret and discuss the two plots. Which features
appear to contribute the most to the predicted probability?
2. Upload at least 2 feature importance plots. Which features are the most important
in their contribution to your models predictive power?
3. Stretch goal: Modify the visualization formula. Plot your output and provide an
interpretation. Which estimator was more effective at reproducing the probability
model that was used to generate the instance of data that was synthetically
generated?
