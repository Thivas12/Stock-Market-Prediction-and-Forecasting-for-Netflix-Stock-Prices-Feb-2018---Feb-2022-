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



