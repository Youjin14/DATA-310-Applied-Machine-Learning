## A. Premade estimators
1. How did you split the labels from the training set? What was the name of the labels
dataset?

The labels from the training set was split from the testing data by referencing separate files. After a pandas data set was created, the training set labels were named 'SepalLength', 'SepalWidth', 'PetalLength', 'PetalWidth'. (Discluded Species becuause that is what we are testing for)

2. List 5 different estimators from tf.estimator and include the base command as you would write it in a script (for example this script used the tf.estimator.DNNClassifier() function from the API).

5 estimators from tf.estimator:
  1) Baseline
  2) Boosted Trees 
  3) DNN 
  4) Linear
  5) DNN Linear Combined
  
(From the TF Hub example:)
classifier = tf.estimator.DNNClassifier(
    feature_columns=my_feature_columns,
    # Two hidden layers of 30 and 10 nodes respectively.
    hidden_units=[30, 10],
    # The model must choose between 3 classes.
    n_classes=3)
  
3. What are the purposes input functions and defining feature columns?

The purpose of the input functions is to return a dataset object with a two-element tuple containing the labels and features. The purpose of defining feature columns is to help describe how the model should use raw input data from the features dictionary. When you build an Estimator model, you pass it a list of feature columns that describes each of the features you want the model to use.

4. Describe the command classifier.train() in detail. What is the classifier and how did
you define it? Which nested function (and how have you defined it) are you applying
to the training and test detests?

The command, classifier.train(), trains the model by the Estimator's train method. The classifier in the TF Hub example was set as DNNClassifier, therefore, the model will train based on how DNNClassifier was written for it to be trained. The DNNClassifier command builds a feedforward multilayer neural network that is trained with a set of labeled data in order to perform classification on similar, unlabeled data. (https://www.mapleprimes.com/maplesoftblog/209354-A-Beginners-Guide-To-Using-The-DNN) The input_fn function is calling on lambda to capture the arguments while providing an input function that takes no arguments, as expected by the Estimator. The steps argument tells the method to stop training after a number of training steps (set to 5000 in the TF Hub example).  

5. Redefine your classifier using the DNNLinearCombinedClassifier() as well as the
LinearClassifier(). Retrain your model and compare the results using the three
different estimators you instantiated. Rank the three estimators in terms of their
performance.

The DNN Classifier had a test set accuracy of 0.833.

The DNNLinearCombinedClassifier had a test set accuracy of 0.533.

The LinearClassifier had a test set accuracy of 0.967.

I would rank the estimators as LinearClassifier first, DNNClassifier secind, and last DNNLinearCombinedClassifier based on their accuracy results.

## B. Build a Linear Model
1. Using the dftrain dataset, upload an image where you used the seaborn library to
produce a sns.pairplot(). Also include a histogram of age using the training set and
compare it to the seaborn plot for that same feature (variable). What interpretation
can you provide of the data based on this plot?

![](https://user-images.githubusercontent.com/67920289/88450211-42e58b80-ce1b-11ea-9b1a-e4ad3470adb5.png)

![](https://user-images.githubusercontent.com/67920289/88450122-a6bb8480-ce1a-11ea-8471-40330d5d3e1a.png)

From the graphs, we can see how majority of the passengers were 20-30 years old. Age did not play a large part in the fare or parch if the passenger, but there is a slight correlation where younger passengers had more siblings or spouses. 

2. What is the difference between a categorial column and a dense feature?

They differ in that DenseFeatures only accepts dense tensors, to inspect a categorical column we need to transform that to a indicator column first.

3. Describe the feature columns that have been input to your LinearClassifier(). How
would you assess the result from your initial output? What is the purpose of adding
a cross featured column? Did your attempt to capture the interaction between age
and gender and incorporate it into your model improve performance? Include and
interpret your predicted probabilities and ROC curve plots.

The feature columns were dervived from the categorical and numeric columns already provided from the dataset. Feature columns describe how the model should convert each feature. The results from the initial output returns many statistics revealing the training accuracy, average loss, and more. The purpose of adding a cross featured column allows the model to learn differences between different feature combinations. The model's accuracy decreased when adding the combination feature between age and gender and incorporating it into the model. 

Feature Column:

![](https://user-images.githubusercontent.com/67920289/88450601-24cd5a80-ce1e-11ea-9211-8581354a8e1f.png)
![](https://user-images.githubusercontent.com/67920289/88450596-167f3e80-ce1e-11ea-9c5e-10f989cffb9f.png)

Derived Feature Column:

![](https://user-images.githubusercontent.com/67920289/88450629-52b29f00-ce1e-11ea-8e08-0ca5175452b4.png)
![](https://user-images.githubusercontent.com/67920289/88450639-5ba37080-ce1e-11ea-9376-2d48b49e6104.png)

The graphs do not have many noticable differences. However, both show similar characteristics in which the frequency is high when the predicted probabilities is low at the beginning of the graph. Also, the receiver operating characteristic graph shows an increase in true positive rates with an increase in false positive rates.




