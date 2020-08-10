For the dataset, I decided to use a basic Deep Neural Network and a more complex Convolutional Neural Network. Both are sequential keras models because it was recommended by Professor Frazier and it is a good model for is appropriate for a plain stack of layers where each layer has exactly one input tensor and one output tensor.

The DNN comprised of four total layers, Flatten() and three Dense() layers of 128, 64, and 1. I also set the activation function to relu because the model would take less time to train and run (due to negative numbers being set to zero). I then applied RMSProp because I believed it would help the learning rate and decrease the loss. The loss was set to Mean Square Error to measure how good the prediction model did at predicting the expected outcome. MSE would be good for the regression model and also because the it would penalize larger outliers (which is good because we are assuming the targets are noramally distributed).
For the convolutional neural network, the model had many more layers, totalling 10. There were 3 sets of Conv2D and MaxPooling2D layers starting from 16, 32, then 64. Then there is a layer to flatter the data. Lastly, there are three Dense() layers similar to the CNN. I applied the same functions for similar reasons as the DNN. I used a relu activation, RMSProp as the optimizer, and MSE to measure the loss.

I first unloaded the images and then separated them into testing and training groups. The training group had a total of 2999 images and the testing group had 199. For the DNN model, there was a total of 10 epochs with a batch size of 32. I thought these numbers would return results quicker.The CNN model only had 5 epochs with a batch size of 100 because it took longer to run the model.

Unfortunately, I was unable to record the results before my laptop restarted. However, for the CNN model the mse and loss were both very high. The first epoch showed the loss and mse to be in the hundreds of thousands but by the tenth epoch, it was in the lower (ten) thousands. I believe if I ran the model with more epochs, the loss and mse would be much lower. For the DNN model, I was unable to receive any results after my laptop restarted for the second time after running the first epoch (it took around 30 minutes for the first epoch to run). 

This is how I set the code:
import os
import zipfile
import tensorflow as tf
import glob
import pandas as pd
import numpy as np
from numpy import genfromtxt
from io import StringIO
import re
from matplotlib.pyplot import imshow
from tensorflow.keras.optimizers import RMSprop
import keras_preprocessing
from keras.preprocessing import image
import PIL
from PIL import Image

raw_files = glob.glob('/Users/youjinlee/PycharmProjects/Week1Day2/raw_images/*.jpeg')
raw_files.sort(key=lambda f: int(re.sub('\D', '', f)))
images = np.array([np.array(Image.open(raw_images)) for raw_images in raw_files])
labels = genfromtxt('/Users/youjinlee/Desktop/labels.csv', delimiter=',')

train_imgs = images[0:2999]
train_labs = labels[1:3000, 1]

test_imgs = images[3000:3199]
test_labs = labels[3001:3200, 1]

​
len(train_imgs)
len(train_labs)
​
len(test_imgs)
len(test_labs)

# DNN
model = tf.keras.models.Sequential([
  tf.keras.layers.Flatten(),
  tf.keras.layers.Dense(128, activation = tf.nn.relu),
  tf.keras.layers.Dense(64, activation = tf.nn.relu),
  tf.keras.layers.Dense(1)])
model.compile(optimizer=RMSprop(lr=0.001), loss='mse', metrics=['mae','mse'])
model.fit(train_imgs, train_labs, epochs=10, steps_per_epoch=93, batch_size=32)
test_loss = model.evaluate(test_imgs, test_labs)

print('\nTest accuracy:', test_loss)

# CNN
model = tf.keras.models.Sequential([
  tf.keras.layers.Conv2D(16, (3, 3), activation=tf.nn.relu, input_shape=(480, 480, 3)),
  tf.keras.layers.MaxPooling2D(2, 2),
  tf.keras.layers.Conv2D(32, (3, 3), activation=tf.nn.relu),
  tf.keras.layers.MaxPooling2D(2, 2),
  tf.keras.layers.Conv2D(64, (3, 3), activation=tf.nn.relu),
  tf.keras.layers.MaxPooling2D(2, 2),
  tf.keras.layers.Flatten(),
  tf.keras.layers.Dense(128, activation=tf.nn.relu),
  tf.keras.layers.Dense(64, activation=tf.nn.relu),
  tf.keras.layers.Dense(1)])
model.compile(optimizer=RMSprop(lr=0.001), loss='mse', metrics=['mae','mse'])
model.fit(train_imgs,train_labs,batch_size=100,epochs= 5, steps_per_epoch = 90)
test_loss, test_acc = model.evaluate(test_imgs, test_labs, verbose = 2)

print('\nTest accuracy:', test_acc)

from tensorflow.keras.preprocessing import image
img = image.load_img('\\Users\\Jack\\PycharmProjects\\Project3\\Accra1\\88.jpeg', target_size=(480, 480))
x = image.img_to_array(img)
x = np.expand_dims(x, axis=0)
val_img = np.vstack([x])
val_img = val_img / 255.0
print(model.predict(val_img))
imshow(np.asarray(train_imgs[310]))
train_labs[310]

(I am running my DNN currently! Thank you!)
