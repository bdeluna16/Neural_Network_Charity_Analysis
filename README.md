# Neural_Network_Charity_Analysis

## Overview

In this project we were tasked with creating a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. Our datasource was a csv file containing more than 34,000 organizations that had received funding from Alphabet Soup. With the data we preprocessed it for our neural network model, compiled, trained, and evaluated the model, and lastly we attempted to optimize the model in order to improve accuracy.

## Results

### Data Preprocessing

What variable(s) are considered the target(s) for your model?

*   If the company was successful

What variable(s) are considered to be the features for your model?

*   application type
*   affiliation
*   classification
*   use case
*   organization
*   income amount
*   special considerations

What variable(s) are neither targets nor features, and should be removed from the input data?

*   Although the we used the features mentioned above in our model some of these should have not been included in the testing:

    * affiliation
    * use case
    * organization
    * special considerations

### Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?

*   Chose to use 80 neurons in the first hidden layer and 30 neurons in the second hidden layer
*   Activiation function "relu" was used for both hidden layers and "sigmoid" was used for output layer

Were you able to achieve the target model performance?

*   My model performed with 69% accuracy which falls short of the target model performance goal of 75%

What steps did you take to try and increase model performance?

* Attempt 1:
    * Dropped EIN, NAME, SPECIAL CONSIDERATIONS, STATUS, ORGANIZATION, columns in order to reduce the noise
    * Used binning for the application types that placed all values under 10,000 into its own bin
    * Added a third hidden layer in the model and used activation function "tanh" for all 3 hidden layers
    
* Attempt 2:
    * Dropped ASK_AMT column along with the same columns in attempt 1
    * Reduced the the neurons in hidden layer 1 to 8 and reduced the neurons in hidden layer 2 to 5
    * Only used 2 hidden layers and used activation function "relu"

* Attempt 3:
    * Dropped same columns in attempt 1 & 2
    * Used binning for the application types that placed all values under 10,000 into its own bin
    * Used binning for the classification types that placed all values under 1,880 into its own bin
    * Used same model as in attempt 2

## Summary

Overall we were not able to achieve the target model performance goal of 75%. Our attempt at optimizing the model failed with our attempts achieving accuracy scores of 50%, 58%, and 60% respectively. One thing that I saw that could have attributed to the slight increase in accuracy over the models was the use of binning on the features that had very skewed data. For example, there were a high amount of "C1000" classification types and very little amounts of other classification types. Binning helped normalize the data which looks like contributed to the improvement of the model.

If we were to use another model to solve this classification problem I would reccomend using logistic regression. Since we know what our dependent variable is and what we are looking for, logistic regression could be used to predict the probability of an organization being successful if funded by Alphabet Soup.