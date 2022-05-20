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


