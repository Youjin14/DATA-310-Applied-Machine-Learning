Question 1: Machine Learning is where programers feed data and the answers from the data into a program, and machine figure works to find out/predict the rules that result in the very answers from the inputed data.
On the otherhand, traditional programming requires the input of data and the rules, and the program will return the answers that are derived by applying the rules to the inputted data.

Question 2: After modifying Laurence Maroney’s code and running it twice, the two results were different from each other. Both answers were close to 22, but were off by a little bit. The reason for the variation is because the model's parameter's are randomly initialized giving different weights to the different data. In order to end at the same result every time, we must assign a fixed seed for the weights. In other words, the machine is creating a different model each time it is run. (source https://machinelearningmastery.com/randomness-in-machine-learning/)

Question 3:
After training a neural net model that estimates the relationship between room number and house price, the results showed how the estimated prices for homes with different room numbers should be: 

| Room Number        | Predicted Price (in thousands (USD))   | 
| ------------- |:-------------:|
| 1     | $103.98981 |
| 2     | $169.26509 |
| 3     | $234.54037 |
| 4     | $299.81567 |
| 5     | $365.09097 |
| 6     | $103.98981 |

Comparing the predicted to the actual prices of the six homes to the predicted prices based on room number, we find that 

| House Address | Room Number        | House Price      | Predicted Price (in thousands (USD))   | Price Difference |
| ------------- |:-------------:|:-------------:|:-------------:|-----:|
| Church St. | 4     | $399 |$299.81567 | -99.18433 |
| Holly Point St. | 3     | $97 | $234.54037 | +137.54037 |
| 760 New Point Comfort Hwy. | 5     | $347.5 | $365.09097 | +17.59097 |
| E River Rd. | 4     | $289 | $299.81567 | +10.81567 |
| Fitchetts Wharf Rd. | 2     | $250 | $169.26509 | -80.73491 |
| 4403 New Point Comfort Hwy. | 3     | $229 | $234.54037 | +5.54037 | 


Therefore, the homes on Holly Point St., 760 New Point Comfort Hwy., E River Rd., 4403 New Point Comfort Hwy. present a good deal as their prices are lower than the estimated price.
Homes on Church St. and Fitchetts Wharf Rd. are not a good deal, as their prices are higher than the predicted housing prices. 

I believe that the homes on Holly Point St. and Church St. may have skewed the model most because of how large the difference is from the predicted and actual home price.  





