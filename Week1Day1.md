Question 1: Machine Learning is where programers feed data and the answers from the data into a program, and machine figure works to find out/predict the rules that result in the very answers from the inputed data.
On the otherhand, traditional programming requires the input of data and the rules, and the program will return the answers that are derived by applying the rules to the inputted data.

Question 2: After modifying Laurence Maroney’s code and running it twice, the two results were different from each other. Both answers were close to 22, but were off be a little bit. 

Question 3: After running this code:

import tensorflow as tf
import numpy as np
from tensorflow import keras
model = tf.keras.Sequential([keras.layers.Dense(units=1, input_shape=[1])])
model.compile(optimizer='sgd', loss='mean_squared_error')
xs = np.array([4.0, 3.0, 5.0, 4.0, 2.0, 3.0], dtype=float)
ys = np.array([399, 97, 347.5, 289, 250, 229], dtype=float)
model.fit(xs, ys, epochs=500)
print(model.predict([1.0,2.0,3.0,4.0,5.0]))

The results showed how the estimated prices for homes with different room numbers should be: 

| Room Number        | Predicted Price        |
| ------------- |:-------------:|
| 1     | $103.98981 |


1 Room = $103.98981
2 Rooms = 169.26509
3 Rooms = $234.54037
4 Rooms = $299.81567
5 Rooms = 365.09097

Therefore, the homes in Hudgins, Mathews, Mobjack, New Point Comfort present a good deal as their prices are lower than the estimated price.
Homes Church and Moon are not a good deal, as their prices are higher than the predicted housing prices. 





