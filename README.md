# deep-learning-challenge

# Overview
This analysis took data from Applications for Funding from Alphabet Soup and cross-referenced whether that funding was effectively used or not.

# Results
## Preprocessing
* Features: Application Type, Affliation, Classification, Use Case, Organization, Income Amt, Ask Amt, Status, Special Considerations
* Target: Is Successful
* Removable Variables: EIN and Name (identifiers)
## Compiling, Training, Evaluating, Optimizing
Originally, I opted for two hidden layers and one output layer. The hidden layers were "ReLU" activation functions, and the output layer was a sigmoid function. The number of nodes and layers were sort of arbitrarily selected using previous examples from in-class notes/practice. In order to optimize the network, I attempted to increase the number of nodes in each layer (to increase the number of connections), to decrease the number of training epochs (in case there was overtraining), and to reintroduce seemingly inconsequentially columns of data (status, ask amount, and special considerations seemed to have too little or too much variation). After adding these columns back, I was able to achieve a training accuracy of 0.8159 on the last epoch at the cost of a nearly tripled training time. However, the test accuracy did not improve at all - to my surprise, it actually decreased.

# Conclusion
Other optimizations that could have helped the overall accuracy of the model:
* Better binning - either less collapsing or even more grouping
* Scaling - Certain features probably have more influence on whether funding was utilized successfully (or possibly, certain supposedly important features hold no merit)