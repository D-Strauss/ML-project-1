# **AI Project – Predicting Schizophrenia from EEG Resting State Data**

**Problem:** Evaluating psychiatric diagnosis is a challenging, costly and time-consuming endeavor. There are currently no well defined objective EEG biomarkers for the diagnosis of schizophrenia. This AI project will attempt to predict schizophrenia from healthy control  based on electroencephalography resting state data. This may aid in future diagnosis of schizophrenia based on EEG characteristics. I will be using supervised learning, unsupervised, deep learning and dimensionality reduction to investigate, interpret and predict my dataset. 

**Dataset:** 

*Description of the dataset:* The dataset is power spectrum density (an aggregate of electrical activity that has been recorded in the brain). a subset of the dataset was used, featuring a total of 116 columns featuring 19 electrodes and 6 frequency bands.  ** 
*****n* = 212, Schizophrenia(117), Healthy Control(95)

*labels* Schizophrenia(1), Healthy Control (0). 
***Features*:**  
*Main feature:* 19 electrodes with 6 frequency bands each = 114 columns in total.
***Aggregate features/Feature selection*:** 

- Regional (brain lobes) aggregation of mean summed PSD, showing the overall spectral activation.
- Power ratios of amplitude between different frequency bands for each electrode.
- Power ratios of amplitude between different frequency band and brain lobe

**Algorithms and analysis**

*Random forest/Gradient boosting -*   To evaluate feature importance. 

Multilayer Perceptron - Deep learning model to analyze both aggregate feature and the full dataset.

*Principle Component Analysis* - Will be used for dimensionality reduction.

*Hypertuning -* Hypertuning (with random search) will be performed to improve optimal parameter space.

*K-means clustering -* To observe if the patterns discerned by the MLP can identify the groups effectively.

*Logistic regression* **-** To get a reference from the random forest model and understand better the relationship between the feature and target. Furthermore logistic regression is less prone to overfitting which was observed in the Random forest.

**Evaluation Metrics**

Accuracy, F1 score, Roc-AUC, confusion matrix. 

**!Important! 
You will need the dataset which is uploaded in the repository.**
