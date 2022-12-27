# deep-learning-challenge
UCI Bootcamp: Deep Learning

## Overview ##
Alphabet Soup is a nonprofit venture capitalist foundation who is looking for ways to maximize their investments. The purpose of this project is to develop a neural network model for Alphabet Soup to classify successful applicants. 

## Results ##
### Data Preprocessing:###
- Target Variable: IS_SUCCESSFUL—Was the money used effectively
- Featured Variables: 
    - APPLICATION_TYPE—Alphabet Soup application type
    - AFFILIATION—Affiliated sector of industry
    - CLASSIFICATION—Government organization classification
    - USE_CASE—Use case for funding
    - ORGANIZATION—Organization type
    - STATUS—Active status
    - INCOME_AMT—Income classification
    - SPECIAL_CONSIDERATIONS—Special considerations for application
    - ASK_AMT—Funding amount requested
- The variables EIN and NAME were removed from the model as they are unique identifiers which would not be useful in predicting the success of applicants within our model.

### Compiling, Training, and Evaluating the Model: ###
- Four layers were used within this model with the initial layer using 35 neurons. The 2 hidden layers used 20 and 30 neurons. The initial and hidden layers are using ReLu as an activation function because it is the simplest model that fits most circumstances for deep learning. Therefore, it has a quick execution rate compared to other more complex models. The number of neurons used is 20 or higher as they produced higher levels of accuracy compared to the model with less than 20 neurons. The output layer used 1 neuron with the sigmoid activation function as we want to return one target variable (either 0 or 1, with 0 being unsuccessful and 1 being successful).
- The target model performance of 0.75 accuracy was not achieved as the highest model accuracy met was 0.721.
- The steps taken in an attempt to achieve the current model accuracy was:
- Adjusting the binning for the feature variables CLASSIFICATION and APPLICATION_TYPE. I attempted to increase the amount of data within the binning “Other”. For APPLICTION_TYPE, I tested whether including T10 into “Other” would improve the model’s accuracy. Nevertheless, including T10 into “Other” decreased the accuracy by 1%. CLASSIFICATION values with a frequency less than 2,000 and 1,000 were tested. However, 1,000 produced better accuracy results.
- Different activation models such as SeLu, Sigmoid, and Tanh were used. Nevertheless, the execution rate was longer and produced equivalent results.
- The amount of epochs tested were 25, 50, and 100. 100 epochs produced the same results as 50 epochs while 25 epochs produced slightly less accurate results compared to 50 epochs. Therefore 50 epochs was chosen within the final model.

## Summary ##
Overall, the neural network model developed resulted in a loss of 0.56 and an accuracy of 0.72. We have an average amount of accuracy which means we were able to predict the success of Alphabet Soup applicants approximately 72% of the time. Nevertheless, the loss of 0.56 indicates that when the model classified inaccurately, we were around 50% off. This makes sense as we only have two possible values for our target, 0 or 1.<br>
As the results using neural networks are average, other potential models could be tested to see if they could produce better results. I would recommend using Logistic Regression as the target variable is binary. Logistic regression is a simpler model which can help improve the execution rate. It is also used specifically for binary target variables and considers the weight of each feature variable in predicting the target. This may benefit Alphabet Soup as logistic regression models will give us insight on the relation between different features and the target variable.
