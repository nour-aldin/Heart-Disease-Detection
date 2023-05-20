# Heart-Disease-Detection
## IDEA
Heart disease is the leading cause of death globally, and its prevalence is
increasing rapidly. Early detection and prevention of heart disease are crucial for
reducing mortality rates and improving the quality of life for patients. We suggest a big data project that aims to develop a predictive model for the early
detection of heart disease.

## Data preprocessing
- Every categorical class changed to numerical.
  - change columns that contain values of Yes / No with 0 / 1.
  - change sex column that contain Male / Female with 1 / 0.
  - convert Age Category, Race, Diabetic and GenHealth columns with increasing values.
- Check If non-values exist and delete it.

## Extracting insights from data
 - Male have slightly more diabetes the female.
 - Female are smoking less than Male.
 - BMI average is between 20 and 40 and there are many outliers.
 - Between 5 and 8 hours sleep time there are outliers.
 ### **You can find more details and the plots here** https://github.com/nour-aldin/BigData-Project/blob/main/Documents/FinalDoc2.pdf
 
 ## Modeling
  - For all models we used: we did RandomOversampler to balance the classes.
  - We used Naive Bayes , SVM and logistic regression from MLlib in PySpark.
  - Then we used map-reduce functions to implement Naive Bayes:
  - We calculated the prior probabilities of the features and the classes we have.
    - The map phase was used to generate key-value pair <feature, 1>
    - The reduce phase was used to aggregate the number of each attribute value.
  - We calculated the conditional probabilities of each feature given each class.
    - The map phase was used to generate key-value pair <(feature, class), 1>
    - The reduce phase was used to aggregate.
    - Then another map phase was done to calculate the conditional probabilities by dividing the totalCount of the (featureValue, class) by the totalCount of the       class.
