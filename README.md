# Neural_Network_Charity_Analysis

## Purpose
For this exercise we were tasked with creating neural network and have it work as a binary classifier. Our focus was on AlphabetSoup, a foundation that invests in various businesses and they wanted help with creating neural network that could help predict which applicants to their program were most likely to become successful with funding.

## Results
The target of the network, could also be defined as the question to answer you are trying to ask the model. For this project, as stated before, is trying to predict which applicants are more likely to be successful than the others. In the data, this was represented by the IS_SUCCESSFUL column.
![](https://github.com/Stkaran/Neural_Network_Charity_Analysis/blob/main/Resources/Target.png)

The features for the model are what would considered the independents variables. They are the factors that all contribute to an applicant's success.
![](https://github.com/Stkaran/Neural_Network_Charity_Analysis/blob/main/Resources/Features.png)

The table above initially had more columns in it. They were the EIN and NAME columns. These however, only identified each applicant from one another and would have no impact on determining success. Due to this, they were dropped during the data preprocessing step.
![](https://github.com/Stkaran/Neural_Network_Charity_Analysis/blob/main/Resources/Dropped.png)

For the first attempt at the model, there were two hidden layers that both used the relu activation function. The first layer had 80 nodes and the second layer had 30. Since we were trying to answer a yes or no question about success, the sigmoid function appeared to be the best choice for the output as it is ideal for binary classification. Although it was ran for 100 epochs, the model's accuracy stop increasing very early stopping at epoch 30 woth 0.5321 for its accuracy.

The goal for this model was 75% for accuracy and the model unfortunately did not reach this milestone. Rather than starting over, it was decided that we should attempt to try and optimize the model.

To start, we had already binned both the application_type and classification columns on the first go round. The column that stood out the most in this category though, was the asking amount for each application. Therefore, we attempted to bin this column as well into to two categories of 5000 and below and 5000+. The next change was adding a third hidden layer. Lastly, all of the nodes for each hidden layer was increased to reflect the addition of a new hidden layer. While we did try substituting the relu activation with tanh activation, it was ultimately switched back to relu as the tanh did not help increase accuracy. 

# Summary
In the end, while these changes got the model close to the 75% goal, we were unable to reach it with the model omly making it just above 74% accuracy. For this dataset, another that could be used effectively is the RandomForestClassifer. Like a nerual network, this ensemble learner is good at working with tabular data, but it will be able to train with the data much more quickly than a traditional neural network model without sacrificing any accuracy on predictions.