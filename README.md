# Neural Network Charity Analysis
## Overview
The purpose of this analysis is to determine where to make investments by making a prediction on if it will be successful by using a neural network model.
## Results
### Data Preprocess
The data set is divided into three main categories, variables for target - a binary dependent variable that will define if a previous investment was successful, variables for features - independent variables that will be used in the model, and variables that will be removed. This are variables that do not provide additional value to the model
#### Variables for target
- Is_Successful
#### Variables for features
The categorical variables will be broken out with each unique value into its own column. This allows for a binary classification for each value in the model. Two attributes, Application_Type and Classification, have values with a value count below a specific threshold grouped together in a value of 'Other'. This helps prevent over-fitting as well as mitigate the memory constraints when building the model
- Application_Type
- Affiliation
- Classification
- Use_Case
- Organization
- Status
- Income_Amt
- Special_Considerations
- Ask_Amt
#### Variables removed 
- EIN
- Name
### Compiling, Training, and Evaluating Model
**Model: "sequential"**
_________________________________________________________________
 Layer (type)      |          Output Shape      |        Param #   
|---|---|---|
 dense (Dense) |               (None, 80)  | 3520                                                                   
 dense_1 (Dense)     |        (None, 30)           |     2430      
 dense_2 (Dense)  |           (None, 1)        |         31        
                                                                 

Total params: 5,981
Trainable params: 5,981
Non-trainable params: 0
_________________________________________________________________
- Layers
	- 1st layer has 80 nodes and uses the relu activation function
	- 2nd layer has 30 nodes and uses the relu activation function
	- Ouput layer uses the sigmoid activation function as this will provide us the desired "yes or no" output for the "Is Successful" variable

- Target performance achieved
	- Target (75%) was not achieved with this initial model, reaching 72.5%. 
- Steps Taken to optimize
	- Three main steps were taken to optimize the model. The first was to bring the variable "Name" back into the model. This variable was not unique to each record and provides value in the model. The second change was to increase the number of nodes in the second layer from 30 to 40. The third was to add a third hidden layer to the model that has 20 nodes and uses the activation function selu.
	This resulted in accuracy of 75.4%, above our target percentage.
## Summary
After optimizing our model, we were able to build a neural network model that will reach our target of 75% success rate when determining where the foundation should invest. This will allow the foundation to be more successful with targeted investments.