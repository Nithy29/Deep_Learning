# LSTM Stock Predictor

![deep-learning.jpg](Images/deep-learning.jpg)

Due to the volatility of cryptocurrency speculation, investors will often try to incorporate sentiment from social media and news articles to help guide their trading strategies. One such indicator is the [Crypto Fear and Greed Index (FNG)](https://alternative.me/crypto/fear-and-greed-index/) which attempts to use a variety of data sources to produce a daily FNG value for cryptocurrency. I have been asked to help build and evaluate deep learning models using both the FNG values and simple closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

In this assignment, I will use deep learning recurrent neural networks to model bitcoin closing prices. One model will use the FNG indicators to predict the closing price while the second model will use a window of closing prices to predict the nth closing price.

I have completed the following tasks:

1. Prepare the data for training and testing
2. Build and train custom LSTM RNNs
3. Evaluate the performance of each model

- - -

### Files

[Closing Prices Starter Notebook](Starter_Code/lstm_stock_predictor_closing.ipynb) 

[FNG Starter Notebook](Starter_Code/lstm_stock_predictor_fng.ipynb)

- - -

## Instructions

### Data preparation for training and testing:

- FNG Model - Example of Split, Scaled and Reshaped Data

- Close Model - Example of Split, Scaled and Reshaped Data




### Building and training of custom LSTM RNNs:

There are two notebook and I used same custom LSTM RNN architecture in each notebook. 
  >  notebook - [Closing Prices Starter Notebook](Starter_Code/lstm_stock_predictor_closing.ipynb) is fitted with closing prices and
  >  notebook - [FNG Starter Notebook](Starter_Code/lstm_stock_predictor_fng.ipynb) is fitted with FNG index values
    
Both models use the same parameters and training steps so that both models can be compared to each other accurately.



### Evaluation of the performance of each model

Finally, I use the testing data to evaluate each model and compare the performance.


## Summary

I, initially trained both models with the window size and epochs parameters set at 10 and 10 respectively. Then, I experimented with both parameters having windows size range from 10 to 55 and the epoch size range from 10 to 50. But epochs 50 with window size 10 gave better results.  Then I used the same configuration for both model - Closing Price and FNG model.


##### **Which model has a lower loss?**
    
    The Closing Prices model had much lower loss value than that of the FNG model. 
    Closing Prices loss - 0.0040
    FNG Model loss - 0.0479

What's interesting is that Closing Prices model trained relatively well with the loss falling from 0.0577 for epoch=1 to 0.0040 for epoch=50. But FNG model could not even train at all. FNG model inital loass was .0465 and it kept the loss almost same which is .0479 from epoch 1 through epoch 50. Bassically the starting loss is equal to ending loss.



##### **Which model tracks the actual values better over time?**

    The Closing Prices model is much better in tracking the prices over time where as the FNG Model showed no correlation between predicted prices and actual prices.


##### **Which window size works best for the model?**

    Increasing the window size from the initial value of 10 to 15 or decreasing it to 5 produced smaller a loss whereas increase to 50 produced larger loos. So, in the end, I kept the window size at 10 with epoch size of 50.
    

- - -

### Resources

[Keras Sequential Model Guide](https://keras.io/getting-started/sequential-model-guide/)

[Illustrated Guide to LSTMs](https://towardsdatascience.com/illustrated-guide-to-lstms-and-gru-s-a-step-by-step-explanation-44e9eb85bf21)

[Stanford's RNN Cheatsheet](https://stanford.edu/~shervine/teaching/cs-230/cheatsheet-recurrent-neural-networks)

- - -

