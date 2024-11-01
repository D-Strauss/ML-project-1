# **AI Project – Predicting Psychiatric Diagnosis from EEG Resting State Data**

## **Problem:** 
Evaluating psychiatric diagnosis is a challenging, costly and time-consuming endeavor. 
Furthermore, objective biomarkers for psychiatric diagnostics is currently not exercised in practice. This AI project will attempt to predict six types of psychiatric diagnosis based on electroencephalography resting state data. 
The problem is a classification/clustering problem in its nature. I will be using supervised learning, deep learning and dimensionality reduction to investigate, interpret and predict my dataset.
Each psychiatric diagnosis will be treated as a separate object.

## **Dataset:** 
### *Description of dataset:* 
Dataset with a total of 1201 columns, containing power spectrum density measures (114 columns) and coherence metrics (1026 columns). 
The data does not contain a time-series which simplifies the analysis and the PSD and coherence metrics are already a aggregate measure in themselves. 
The quality of data is good but it contains 15 NaNs in a descriptive statistics column(which has minor importance for my analysis). I will have to consider how to deal with the NaNs in the optimal manner.
n = 945, 
### *labels* =  
Schizophrenia(1), Mood Disoder (2), Trauma and Stress (3), Addictive disorder (4), Obsessive Compulsive Disorder (5) , Healthy Control (6). 

## ***Features:***  
### *Descriptive statistics:* 
Sex, Age, Education, IQ
### *Main feature:* 
19 electrodes with 6 frequency bands each = 114 columns in total.
### *Secondary features:* 
171 coherence values over 6 frequency bands = 1026 columns in total. The secondary features will not be used if the analysis becomes to challenging. 

## ***Aggregate features*:** 
### *PSD*
- Regional aggregation of PSD across each frequency band. Regional, in the context, refers to a brain lobes.
- Regional aggregation of mean summed PSD, showing the overall spectral activation.
- Power ratios between different frequency bands.
- PSD-based connectivity - quantifies the correlation between electrode pair across frequency bands. Will be used as a backup aggregate feature if the coherence metrics becomes to exhaustive.
### *Coherence*
- Intra regional coherence - calculating the mean coherence of all electrode pair in the region.
- inter regional coherence - calculate region based coherence values to compare with other regions.
- Edge weights - from thresholded coherence values, for the GAN.
### *Connectivity/Network analysis*
- Degree and Strength - Metrics to evaluate connectivity between different electrodes
- Networks - Dividing the coherence metrics into regions to observe network connectivity.

## **Algorithms and analysis**
### *Random forest/Gradient boosting -* 
Will be used to evaluate feature importance. 
### *Graph Attention Networks* - 
The GAN allows dynamical learning of importance of connections in the dataset, this is crucial in my dataset as EEG data has a spatial dimension which may reveal valuable insight into my problem. 
The GAN will require hyperparameter tuning as it is highly sensitive to the choice of parameters.
### *Principle Component Analysis* - 
A dimensionality reduction algorithm; PCA can be used directly on the 19x6 grid which will preserve the spatial and frequency patternts that are contained within the matrix. 
The PCA will be used as a secondary comparison/evaluation of the other two algorithms and provide additional clustering capabilities.
### *Hypertuning*
Hypertuning - Hypertuning (with random search) will be performed for each model to improve optimal parameter selection.

## **Evaluation Metrics**
Accuracy, F1 score, Roc-AUC, confusion matrix.
