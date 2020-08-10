
By 10PM on Sunday, August 9th, create a 1 to 2 page length GitHub website on your
repository that presents your poster and describes your applied machine learning project.
You are welcome to simply translate the contents of your poster to a webpage format, or
further illustrate your investigation with analysis. Story board formats are also welcome.
Please feel free to reflect on your investigation and elaborate on what an ideal outcome
would look like in your estimation. Provide a brief project proposal (minimum one
paragraph) of how you would proceed with your investigation given more time and
resources.

![DATA 310_ Poster](https://user-images.githubusercontent.com/67920289/89760518-9235e800-daba-11ea-9b86-65d9c2b9b3b9.jpg)

For my final project, I first proposed an Inventory Forecasting model. Unfortunately, when planning this model, I misread the dataset I hoped to use and looked for different datasets on Kaggle. I was unable to find a dataset that had all the features I wanted (item, the inventory amount of every item, sales of each item, time (so I could look at how holidays effect sales and match number of inventory as well). Instead, I hoped to approach this concept and look at how certain variables affect sales and apply the concepts of sales value prediction models to predict specific inventory needed by different businesses. For that reason I looked at different predictive models and data sets. 

The model useed was a Times Series Analysis. Times Series Analysis interprets a sequence of data points indexed in time order with equally spaced time intervals.
The natural ordering of the data makes a times series analysis unique to any other cross-sectional studies. The data set I looked at was the U.S. Census Bureau’s Advance Retail Sales Time Series Collection. The official data set compiled the production & business Activity of a multitude of different industries, including E-commerce, fashion, garden equipment, furniture and more! For my model, I focused on  the retail sales of Clothing and clothing accessory stores. On the poster, there is a graph of the monthly sales from January 1992 to October 2016, and we can see a few trends already! After unloading the data, we applied an Augmented Dickey Fuller test where we discovered that it is non-stationary. Stationary is when the mean, variance, and autocorrelation structure of the data does not change over time. The Stationality of the data is important because it allows us to predict future data by assuming that the data’s statistical properties will be the same in the future as they have been in the past! In order to make the series more stationary, we calculated percent change and applied differencing. Differencing can help stabilise the mean of a time series by removing changes in the level of a time series, and therefore eliminating (or reducing) trend and seasonality. After this process, the ADF Test revealed that the data is nearly non-stationary with a p-value close to 0 (P-value:  7.694323329577691e-05). We then used a Seasonal Autoregressive Integrated Moving Average, or SARIMA model to forecast the data. Autoregressive Integrated Moving Average, or ARIMA, is one of the most widely used forecasting methods for time series data forecasting. SARIMA is an extension to ARIMA that analyzes the trends and seasonality. After creating the model, the model returned a low mean absolute error: 0.023. With the forecast model we produced a graph that predicted future clothing retail sales based on past trends. After running the model we are able to predict that the clothing retail sales will reach $37,142,953,316 by 2021. 

I believe from this model we can apply sales forecasting to focus on many different areas! A few examples include looking at specific trends within an industry,
how location and the demographics of a population affects sales of items, the prices of competitors, and even predict how unofficial Holidays like Back-to-School can cause an increase in electronics and color pencils sales. 

There are many great benefits from applying a sales forecasting model. Economically, large corporations & smaller businesses can maximize revenue and minimize profit loss. They no longer have to rely on sales to get rid of products or throw them away. Additionally the transportation/manufacturing/production fees can be reduced. Environmentally, sales forecasting is a great method to reduce water, air, environmental pollution and destruction from harmful manufacturing/production practices. Additionally, this change in mindset against overproduction can be the first step in a change in business practices, which can lead to changes in consumer behavior and production methods (child-labor, water pollution, poor working conditions).




