# Overview

Reported here is a brief analysis of a deep learning model's capabilities of predicting applicants most likely to produce successful outcomes should they receive funding from the Alphabet Soup foundation based on past data of organizations previously funded by Alphabet Soup. The main goal of this model is to achieve a predictive accuracy of 75%.

# Results Using bulleted lists and images to support your answers, address the following questions:

## Data Preprocessing

The funding outcome model aims to predict if a potential candidate for funding is successful or not.

The model uses a wide variety of information on the candidate from past data which includes application type, affiliation with other companies, government organization classification, purpose of funding, organization type, current status based on activity, current income, the presence of special considerations, the requested funds, and outcome after receiving funds (successful or unsuccessful). In particular, the application types and classifications were binned based on the frequency any distinct values showed up, since there were several values which were seldom identified and grouped into an "Other" category. The bins created by these two categories were also adjusted in amount to optimize the model's predictive accuracy.

The only information irrelevant to the model are any identification markers of the organization which include EIN and Name. These should be independent of the outcome after receiving funds.

## Compiling, Training, and Evaluating the Model

In the first run with the model, there were two hidden layers: the first with 80 neurons and the second with 30 neurons both ran on the ReLU activation function, and one output layer ran on the sigmoid function. 100 epochs were made for each model's training runs. This model produced a prediction accuracy of 72.46%.

The second run with the model increased the number of application type bins from 9 to 11 and the number of classification bins from 6 to 12. The modified model had a prediction accuracy of 72.84%.

Another run with the model altered the activation functions of the two hidden layers from ReLU to Leaky ReLU, while retaining the increase in number of bins. This modification to the model led to a decrease in predictive accuracy to 72.63%.

The last run recorded with this model reverted the changes to the activation functions, kept the bin increases, modified the first hidden layer's neuron amount to 90 neurons, and added a third hidden layer of 10 neurons also ran on the ReLU activation function. The model ran a predictive accuracy of 72.55%.

The loss recorded for each run from first to last was .5616, .5567, .5552, .5604

# Summary

If we chose a model based on the runs conducted, the model in the second run would by my recommendation based solely on having the highest predictive accuracy. In the model's current state, it has yet to achieve the ideal predictive accuracy of 75%, so further tests would need to optimize the model further. One notable observation while running this model is the high amount of loss in data. Only the increase in bins managed to reduce the loss to a considerable degree. For subsequent runs, I would like to process the data further to remove information inconsistently recorded for past data such as income classification, special considerations, and active status. I would also consider the effects of removing the bins for "Other" since an increase in the number of bins led to a reduction of loss. In particular, I would like to pay attention to how I could reduce the amount of loss observed in each of the model's runs.

Rather than conducting another deep learning model, a supervised learning model could also facilitate the Alphabet Soup's goal to predict potential beneficiaries that will become successful with their funding. It can utilize similar data as this deep learning model while also having the ability to distinguish beneficiaries that will make the most out of funding coming from Alphabet Soup. 