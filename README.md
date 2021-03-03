Deep Learning Homework

I think there must have been a mistake made in the lstm_stock_predictor_fng train and test process because the Predicted graph in the last box was so flat, and the Predicted values were not even close to the Real values.

Which model has a lower loss?
Closing price training and testing with 20 epochs showed a lower loss than fear and greed training and testing.

Which model tracks the actual values better over time?
The closing price training and testing tracked the actual values better over time.

Which window size works best for the model?

I used the following for both models, and displayed them in a plot that was figsize=(10,10)

model = Sequential()
model.add(LSTM(
    units=15, return_sequences=True,
    input_shape=(X_train.shape[1], 1)))
model.add(Dropout(0.1))
model.add(LSTM(units=15, return_sequences=True))
model.add(Dropout(0.1))
model.add(LSTM(units=15))
model.add(Dropout(0.1))
model.add(Dense(1))
