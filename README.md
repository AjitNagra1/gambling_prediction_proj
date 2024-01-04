## The impact of socio-economic factors on gambling behaviour in England

Aim: To predict gambling activity (whether someone is likely to pursue or participate in gambling activities or not) based on socio-economic factors to help provide support to at-risk groups. Socio-economic factors include: gender, ethnicity, income group, educational level, region, alcohol consumption, mental health and smoking status.

Dataset: Originally found data that showed % of weekly spending on gambling based on region, gender, age, however this was insufficient for machine learning (as this data was aggregated, not enough individual training samples). Hence we submitted a request to the NHS to access Health Survey for England 2018 (individual, anonymous census data from households with all the socio economic factors and gambling)

Method: 
- Identify sources of data, use aggregated data for exploratory data analysis to plot gambling by income group, age, region etc
- Use survey data for machine learning: had over 1,600 features from which we extracted only the features relevant to us (socio economic factors and gambling)
- Income data drastically reduced the data size from 7000 to around 600, hence this socio-economic factor was removed
- We had to select which features in the original dataset best matched our socio-economic variables (individuals belief of self-worth was chosen as an indicator for mental health)
- There were also multiple gambling metrics we could choose from for our gambling feature, we went with the variable ’Whether spent any money on gambling activity in the last 12 months’ as this was binary that had an even number of data samples for both 1 (yes) and 2 (no), making it an ideal output class for our training algorithm
- There are also other features for gambling we could choose from (’Whether a problem gambler’) however in the whole data-set (with 10,250 training samples) only 33 were classified as problem gamblers hence it is not a suitable split. This output feature class imbalance (where the two classes in the data-set are not balanced) will lead to one class having significantly more data points than the other making the model biased towards the majority class
- MLP Classifier, XGB Classifier, SVM Classifier ML techniques were chosen
- Average across all 4: 60% accuracy
- A comparison of the feature importance of the available models shows that alcohol consumption, age group and smoking status are relatively more important in predicting gambling behaviour

Improvements/Conclusions
- It was agreed prior to the model to focus on the socio-economic factors chosen above (as research had indicated these affected gambling behaviours)
- However, when performing feature importance across all 1,600 features in the survey and how strongly they were correlated with gambling, other features were more better suited to the model than the features we chose (such as gender which is not a good predicator of gambling behaviour)
- The feature ’felt capable of making decisions’ ranked highly. For future studies, a feature selection score should be assigned with all variables involved in the data-set to identify strongly correlated variables that relate to gambling
