# Stock Market Prediction and Forecasting for Netflix stock prices using Stacked LSTM
In this project, we will work with netflix stock prices which made into a data that has dated from Feb 2018 to Feb 2022. So, basically we'll use a combination of AI calculations to forecast this company's future stock price with LSTM.
We'll be using some libraries to work with 
* Tensorflow
* Keras
* Matplotlib
* Numpy
* Scikit-learn

# What is LSTM ? 
LSTM stands for long short-term memory networks, used in the field of Deep Learning. It is a variety of recurrent neural networks (RNNs) that are capable of learning long-term dependencies, especially in sequence prediction problems. LSTM has feedback connections, i.e., it is capable of processing the entire sequence of data, apart from single data points such as images. This finds application in speech recognition, machine translation, etc. LSTM is a special kind of RNN, which shows outstanding performance on a large variety of problems.

# Logic Behind LSTM
The central role of an LSTM model is held by a memory cell known as a ‘cell state’ that maintains its state over time. The cell state is the horizontal line that runs through the top of the below diagram. It can be visualized as a conveyor belt through which information just flows, unchanged. 

![image](https://user-images.githubusercontent.com/86511074/169572014-01fbd042-9d20-4e78-a2aa-a20428ca36c2.png)

Information can be added to or removed from the cell state in LSTM and is regulated by gates. These gates optionally let the information flow in and out of the cell. It contains a pointwise multiplication operation and a sigmoid neural net layer that assist the mechanism.

![image](https://user-images.githubusercontent.com/86511074/169572299-ad78d584-55be-4c05-9b30-aaf441010aa7.png)

The sigmoid layer gives out numbers between zero and one, where zero means ‘nothing should be let through,’ and one means ‘everything should be let through.’

# DESCRIPTION

Now coming into our project, lets have a timeline of how this works,
* Loading the Data
* Train and Test Split
* Data Preprocessing
* LSTM
* Prediction 
* Conclusion

**LOADING THE DATA :**
Netflix data is upto 04-02-2022. Let's take the close column for the stock prediction.

![image](https://user-images.githubusercontent.com/86511074/169573344-6186b0d0-16ec-4a2a-991d-b14ec833270c.png)

.
.
.
.

![image](https://user-images.githubusercontent.com/86511074/169573414-231327c6-4ab3-4c21-8266-fadaa3310d11.png)

We can plot the close value graph using pyplot
From 2018 - 2022

![image](https://user-images.githubusercontent.com/86511074/169573640-74b832ee-6574-436f-a456-1e5cdf7dd5a6.png)

Since LSTM is very sensitive we used MinMaxScaler to transform the values from 0 to 1. It can be seen in the notebook.

**TRAIN AND TEST SPLIT :**
Whenever training Timeseries data we should divide the data differently and we should train the data with the respective date. In time-series data the one data is dependant on other data.

The training size should be 65% of the total length of the data frame, the test size should be the difference between the length of the dataset and the training size. After writing the script on the notebook, the train and test data is ready.

**DATA PREPROCESSING :**
Now consider the time steps, if I want to predict the price of the stock in a day that how previous data should be considered. Now the timestep value will be 100. Let's split the data into X,Y. In the 0th iteration the first 100 elements goes as your first record and the 101 elements will be put up in the X. The 100 elements will be put up in the Y. You can see this clearly on the notebook.

**LSTM :**
LSTMs are widely used for sequence prediciton problems and have proven to be extremely effective. The reason they work so well is that LSTM can store past important information and forget the information that is not.

LSTM has three gates
  * **The input gate :** The input gate adds information to the cell state.
  * **The forget gate :** It removes the information that is no longer required by the model.
  * **The output gate :** Output gate at LSTM selects the information to be shown as output.

While implementing any LSTM, we should always reshape our X train in 3-D, add 1. The reason behind this is that the time step and the 1 is given to the LSTM. So after importing modules(tensorflow keras) for the stacked LSTM, we will be using a sequential model and add the layers of the LSTM. The first layer should be the time step in 1. So, now the final part will be fitting the X_train and Y_train.

![image](https://user-images.githubusercontent.com/86511074/169578248-a955fb11-7c5e-46fb-9d6a-2d24810f484c.png)

**PREDICTION :**
We need to predict both the X_train and X_test. If i want to see the RMS(root mean square) performance we need to do scaler inverse transform.

![image](https://user-images.githubusercontent.com/86511074/169577047-33b15884-73aa-4420-bc93-152bc947d531.png)

* Green indicates the Predicted Data
* Blue indicates the Complete Data
* Orange indicates the Train Data

If I consider the last date in the test data as of 04-02-2022, I want to predict the output for the next 30 days which is from 05-02-2022 to 03-03-2022. We need the previous 100 data for that I am taking the data and reshaping it.

So finally, you can predict the prices of Netflix stocks using this strategy.

![image](https://user-images.githubusercontent.com/86511074/169577753-8a6a021a-bd41-41aa-bafe-6f5ef27c9215.png)

**CONCLUSION :**
Various parameter of the LSTM model can be tweaked, such as the number of LSTM layers, the dropout value, and the number of epochs. Are the LSTM projections, however, precise enough to predict whether the stock price will rise or fall? Without the doubt.

![image](https://user-images.githubusercontent.com/86511074/169577736-f7663a71-728c-4d90-bd28-43192994abfe.png)



