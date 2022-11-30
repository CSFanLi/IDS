# Improving Intrusion Detection System Using Ensemble Methods and Over-Sampling Technique
Author:Fan Li<br/>
Last update:26/11/2022<br/>
<br/>
This repository contains the code for the project "Intrusion Detection System Using Ensemble Learning". The code and Intrusion Detection System (IDS) can be used in anomaly-based cyber attack detection application.<br/>
</br>
It proposed intrusion detection system by implementing many ensemble learning algorithms including random forest, XGBoost, LightGBM, CatBoost, etc.<br/>
# Abstract
Due to the imbalanced training samples, anomaly-based intrusion detection system (IDS) has to face many problems such as low detection accuracy, high false alarm rate and insufficient application value, especially in multi-classification task. This paper proposed variety of methods to improve the effect of the intrusion detection system based on machine learning. Synthetic minority over-sampling technique (SMOTE), generated new samples by K-nearest neighbor interpolation of minority, was used to alleviate the problem of sample imbalance and improve the model effect. Combination methods was used to improve the effect of model and achieve the multi-classification of intrusion traffic. The experimental results show that the improving ensemble learning-based IDS with SMOTE has improved in several metrics. It is 98.5% in Macro Average Accuracy, 93.8% in Macro Average Precision, 98.5% in Macro Average Recall, 95.8% in Macro Average F1Score and 99.2% in Macro Average AUC. CIC-IDS2017 public dataset provided by the Canadian Institute for Cybersecurity (CIC) was used in this research.
<br/>
# Dataset
CICIDS2017 dataset provided by Canadian Institute for Cybersecurity(CIC) in University of New Brunswick(UNB) contains benign and the most up-to-date common attacks, which resembles the true real-world data. https://www.unb.ca/cic/datasets/ids-2017.html<br/>
<br/>
The CICIDS2017 dataset consists of labeled network flows, including full packet payloads in pcap format, the corresponding profiles and the labeled flows (GeneratedLabelledFlows.zip) and CSV files for machine and deep learning purpose (MachineLearningCSV.zip) are publicly available for researchers.<br/>
## 1. Dataset Source
### Date
- Monday, July 3, 2017
- Tuesday, July 4, 2017
- Wednesday, July 5, 2017
- Thursday, July 6, 2017
- Friday, July 7, 2017
### CSV FILE
| Filename | Size | Description |
| -------- | ---- | ----------- |
| Monday-WorkingHours.pcap_ISCX.csv | 158,603 KB | Benign(Normal human activities) |
| Tuesday-WorkingHours.pcap_ISCX.csv | 131,914 KB | Benign, Brute Force(FTP-Patator, SSH-Patator) |
| Wednesday-workingHours.pcap_ISCX.csv | 219,890 KB | Begin, DoS / DDoS, Heartbleed |
| Thursday-WorkingHours-Morning-WebAttacks.pcap_ISCX.csv | 50,804 KB | Benign, Web Attack(Brute Force, XSS, Sql Injection) |
| Thursday-WorkingHours-Afternoon-Infilteration.pcap_ISCX.csv | 81,155 KB | Benign, Infiltration |
| Friday-WorkingHours-Morning.pcap_ISCX.csv | 56,950 KB | Benign, Botnet |
| Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv | 75,317 KB | Benign, DDos  |
| Friday-WorkingHours-Afternoon-PortScan.pcap_ISCX.csv | 75,104 KB | Benign, PortScan |
## 2. Data Analysis
### Reading CSV
```python
import pandas as pd
data=pd.read_csv("...")
data.shape
(2830743, 79)
```
### Label Value Counts
```python
target_count=data[' Label'].value_counts()
target_count
BENIGN                        2273097
DoS Hulk                       231073
PortScan                       158930
DDoS                           128027
DoS GoldenEye                   10293
FTP-Patator                      7938
SSH-Patator                      5897
DoS slowloris                    5796
DoS Slowhttptest                 5499
Bot                              1966
Web Attack � Brute Force         1507
Web Attack � XSS                  652
Infiltration                       36
Web Attack � Sql Injection         21
Heartbleed                         11
Name:  Label, dtype: int64
```
![15categories](https://raw.githubusercontent.com/CSFanLi/IDS/main/images/15categories.png)![8categories](https://raw.githubusercontent.com/CSFanLi/IDS/main/images/8categories.png)
The dataset is characterised by a very different distribution of examples among the classes. The condition of multiple imbalanced classes is more restrictive when the aim of the final system is to obtain the most accurate precision for each of the comceptes of the problem.

# EXPERIMENTS AND RESULT
## 1. Top Hardware
|Model|vCPU|Core Num.|CPU|RAM|
|--|--|--|--|--|
|c7.3xlarge.4|12v|4|Intel Ice Lake 3.0GHz|48GB|
## 2. Software Version
|package|numpy|pandas|seaborn|matplotlib|sklearn|imblearn|re|pip|xgboost|lightgbm|catboost|
|--|--|--|--|--|--|--|--|--|--|--|--|
|version|1.23.2|1.4.3|0.12.0|3.5.3|1.1.2|0.9.1|2.2.1|22.1.2|1.6.2|3.3.2|1.1.1|  
## 3. Result
|Model| Precision|	Recall|	F1score|	AUC|
|--|--|--|--|--|
|RF|	0.968|	0.910|	0.934|	0.954|
|RF(SMOTE)|	0.954|	0.956|	0.950|	0.977|
|Xgboost|	0.979|	0.959|	0.968|	0.979|
|Xgboot(SMOTE)|	0.927|	0.989|	0.952|	0.994|
|LightGBM|	0.465|	0.457|	0.461|	0.726|
|LightGBM(SMOTE)|	0.586|	0.968|	0.638|	0.983|
|CatBoost|	0.983|	0.933|	0.955|	0.966|
|CatBoost(SMOTE)|	0.911|	0.983|	0.936|	0.994|
|Stacking(Xgboost+LR)|	0.981|	0.932|	0.964|	0.974|
|Proposed Method| 0.932|	0.989|	0.955|	0.994|
