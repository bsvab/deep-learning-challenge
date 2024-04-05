# Module 21 Challenge

## <p style="color:#CC6600">Background / Scenario</p> 

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With the use of machine learning and neural networks, the features in the provided dataset will be used to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization.
<br>

## <p style="color:#CC6600">Neural Network Model Report</p> 

### <p style="color:gray">OVERVIEW</p> 
Alphabet Soup aims to improve the efficiency of its funding selection process by leveraging machine learning and neural networks. The goal of this analysis is to develop a binary classifier that predicts the success of funding applicants based on the provided features.
<br>

### <p style="color:gray">RESULTS</p> 
- <ins>Data Preprocessing</ins>: 
    - What variable(s) are the target(s) for your model?
        - The `IS_SUCCESSFUL` column is the target for the model. This column defines the outcome of past funded applicants.
    - What variable(s) are the features for your model?
        - The relevant feature columns includes: `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, and `ASK_AMT`.
    - What variable(s) should be removed from the input data because they are neither targets nor features?
        - `EIN` and `NAME` are removed from the input data as they do not have the potential to affect the outcome.
- <ins>Compiling, Training, & Evaluating The Model</ins>:
    - How many neurons, layers, and activation functions did you select for your neural network model, and why?
        - The selected hyperparameters are identified in the below table:
            | Layer # | # of Neurons | Activation Function |
            | ------- | ------------ | ------------------- |
            | 1       | 6            | sigmoid             |
            | 2       | 10           | sigmoid             |
            | 3       | 6            | sigmoid             |
            | 4       | 6            | sigmoid             |
            | output  | 1            | sigmoid             |
        - After 9 iterations of adjustments, these represent the combination of hyperparameters that exhibited the best performance. After utilizing kerastuner and running through several initial iterations, it was clear that the sigmoid activation function performed the best. The quantity of layers and neurons varied more with their impact on the accuracy.
    - Were you able to achieve the target model performance?
        - The target model performance of 75% accuracy was unable to be achieved after 9 iterations of modifications to the model. The maximum accuracy achieved out of all iterations was 73%.
    - What steps did you take in your attempts to increase model performance?
        - I utilized 3 iterations of running kerastuner to see what hyperparameters it suggested along with 6 additional manual edits of the quantity of neurons, quantity of layers, and selections of activation functions.
        - The results of each iteration are shown in the below table. Iteration #6 was the final model chosen, and whose hyperparameters are included with the first question above.
            | Iteration # | Accuracy | Loss   | Adjusted Via |
            | ----------- | -------- | ------ | ------------ |
            | 0           | 0.7298   | 0.5589 | N/A          |
            | 1a          | 0.7280   | 0.5523 | kerastuner   |
            | 2           | 0.7298   | 0.5589 | kerastuner   |
            | 3           | 0.7297   | 0.5731 | kerastuner   |
            | 4           | 0.7291   | 0.5541 | manual       |
            | 5           | 0.7298   | 0.5556 | manual       |
            | 6           | 0.7303   | 0.5526 | manual       |
            | 7           | 0.7289   | 0.5685 | manual       |
            | 8           | 0.7259   | 0.5545 | manual       |
            | 9           | 0.7268   | 0.5515 | manual       |
<!-- <br> -->

### <p style="color:gray">SUMMARY</p> 

<!-- Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation. -->

<!-- The deep learning model demonstrated moderate predictive performance but fell short of the target accuracy. To enhance model performance, a different approach could involve exploring more complex neural network architectures, such as convolutional neural networks (CNNs) or recurrent neural networks (RNNs). These models can capture intricate patterns and dependencies within the data, potentially leading to improved predictive accuracy for this classification problem. Further exploration is needed. -->

<!-- The classification problem arises from the need to assess the likelihood of success for funding applicants based on historical data. Despite moderate predictive performance achieved by the developed neural network model, there remains room for improvement to meet the desired accuracy threshold. To enhance model performance, exploring alternative classification algorithms, feature engineering techniques, or gathering additional relevant data could be considered. These approaches may provide deeper insights into the factors influencing funding success and lead to more accurate predictions, thereby optimizing Alphabet Soup's funding selection process. -->

The classification problem arises from the need to assess the likelihood of success for funding applicants based on historical data. Despite moderate predictive performance achieved by the developed neural network model, there remains room for improvement to meet the desired accuracy threshold. To enhance model performance, exploring alternative classification algorithms, feature engineering techniques, or gathering additional relevant data could be considered. For instance, employing a Random Forest classifier might provide better interpretability and handle non-linear relationships more effectively, especially when dealing with categorical variables like `APPLICATION_TYPE`, `AFFILIATION`, and `CLASSIFICATION` among others. <!-- Additionally, ensemble methods such as Gradient Boosting Machines (GBM) could be explored to leverage the strengths of multiple weak learners and potentially enhance predictive accuracy. -->
<br>

## <p style="color:#CC6600">References</p>

IRS. Tax Exempt Organization Search Bulk Data Downloads. https://www.irs.gov/
<br>
<br>
<br>
![UTlogo](images/utaustin-mccombs.png)      <img src="images/edx-logo-elm.svg" width="200" height="80"> 