# Improving Ensemble Learning-based Intrusion Detection System with SMOTE
Author:Fan Li<br/>
Last update:26/11/2022<br/>
<br/>
This repository contains the code for the project "Intrusion Detection System Using Ensemble Learning". The code and Intrusion Detection System (IDS) can be used in anomaly-based cyber attack detection application.<br/>
</br>
It proposed intrusion detection system by implementing many ensemble learning algorithms including random forest, XGBoost, LightGBM, CatBoost, etc.<br/>
## Abstract
Due to the imbalanced training samples, anomaly-based intrusion detection system (IDS) has to face many problems such as low detection accuracy, high false alarm rate and insufficient application value, especially in multi-classification task. This paper proposed variety of methods to improve the effect of the intrusion detection system based on machine learning. Synthetic minority over-sampling technique (SMOTE), generated new samples by K-nearest neighbor interpolation of minority, was used to alleviate the problem of sample imbalance and improve the model effect. Combination methods was used to improve the effect of model and achieve the multi-classification of intrusion traffic. The experimental results show that the improving ensemble learning-based IDS with SMOTE has improved in several metrics. It is 98.5% in Macro Average Accuracy, 93.8% in Macro Average Precision, 98.5% in Macro Average Recall, 95.8% in Macro Average F1Score and 99.2% in Macro Average AUC. CIC-IDS2017 public dataset provided by the Canadian Institute for Cybersecurity (CIC) was used in this research.
<br/>
## EXPERIMENTS AND RESULT
### 1. Top Hardware
|Model|vCPU|Core Num.|CPU|RAM|
|--|--|--|--|--|
|c7.3xlarge.4|12v|4|Intel Ice Lake 3.0GHz|48GB|
### 2. Software Version
|package|numpy|pandas|seaborn|matplotlib|sklearn|imblearn|re|pip|xgboost|lightgbm|catboost|
|--|--|--|--|--|--|--|--|--|--|--|--|
|version|1.23.2|1.4.3|0.12.0|3.5.3|1.1.2|0.9.1|2.2.1|22.1.2|1.6.2|3.3.2|1.1.1|  
### 3. Result
