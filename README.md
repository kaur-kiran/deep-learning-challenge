## Overview 
Using funding from Alphabet Soup, this project intends to create a binary classifier that can forecast applicants' chances of success. In order to train and evaluate the model's performance, the project will make use of the features found in the provided dataset. The goal is to improve the model to a level of accuracy that is more than 75%.greater
## Results
#### Data Preprocessing
The model seeks to forecast applicants' success in receiving money. This is demonstrated by the dataset's 'IS_SUCCESSFUL' column, which represents the model's target variable. The columns with the exception of the target variable and irrelevant variables like "EIN" and "names" are the feature variables. The non-relevant variables that are neither targets nor features will be removed from the dataset to prevent potential noise that can confuse the model. The features capture relevant information about the data and can be utilized to forecast the target variables.  names,
In the 'APPLICATION_TYPE' and 'CLASSIFICATION' columns, I introduced binning and bucketing for uncommon occurrences during preprocessing. Using the one-hot encoding method, I then converted category data into numeric data. I divided the data into sets specifically for features, targets, training, and testing. Finally, I scaled the data to guarantee that the distribution of the data was uniform. 
#### Compiling, Training, and Evaluating the Model
Model 1: I chose to add 3 layers in my initial model: an input layer with 80 neurons, a second layer with 30 neurons, and an output layer with one neuron. I made this decision to make sure that there would be about 2-3 times as many neurons in the model as there were input features. In this instance, 43 input features remained after 2 unnecessary ones were eliminated. Since the objective was binary classification, I used the'relu' activation function for the first and second layers and the'sigmoid' activation function for the output layer. Beginning with 100 training iterations, I was able to get an accuracy score of roughly 74% for the training data and 72.9% for the testing data. Then there were no obvious signs of either overfitting or underfitting.the relu2–3three
**Optimization attempts**
1.In an effort to boost generalization, I added two dropout layers with a rate of 0.5 to the model's architecture and changed the activation function in the input and hidden layers to "tanh." This was done in an effort to improve the model's performance. As a result, I received accuracy ratings of 74.1% for my training set and 72.9% for my testing set.1. In
2. I used hyperparameter tuning for the second effort at optimization. During this procedure, Keras discovered the ideal hyperparameters, which comprise 41 neurons for the first layer, the 'tanh' activation function, and 13, 5, and 4 units for the succeeding layers. As a consequence, the model received a score of 73.3% for accuracy.
3. In the preprocessing stage of my final optimization attempt, I binged the 'ASK AMT' column and deleted the 'STATUS' column. In the 'ASK_AMT' column,there were two bins: one for sums up to $5,000 and the other for all other sums. This choice was made in response to a histogram analysis that revealed an imbalance in the dataset that was seen. With a dropout rate of 0.5 and a 'tanh' activation function, I kept the two dropout layers. I used the early halting function with a patience of 5 and monitored the 'val_accuracy' metric to find the ideal number of epochs. Using this method, I discovered that training the model for 8 epochs produced the best outcomes. I made these improvements to my last optimization attempt, which resulted in an accuracy score of roughly 73%.


## Summary
I wouldn't recommend any of the aforementioned models since I was unable to get the desired accuracy of 75%. With more time, I would investigate different strategies, such as adding the Random Forest Classifier and testing with various preprocessing adjustments. I think that tweaking the dropout layers, experimenting with other activation functions, and altering the number of layers and neurons could all help to improve the model and reach the target accuracy of 75%.
