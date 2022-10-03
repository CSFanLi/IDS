# Intrusion Detection System Using Machine Learning On CIC-IDS2017
Author:Fan Li<br/>
Last update:02/10/2022<br/>
<br/>
This repository contains the code for the project "Intrusion Detection System Using Machine Learning". The code and Intrusion Detection System (IDS) can be used in anomaly-based cyber attack detection application.<br/>
</br>
It proposed intrusion detection system by implementing many machine learning algorithms including random forest, XGBoost, LightGBM, CatBoost,etc.<br/>
# Abstract
# Dataset
CICIDS2017 dataset provided by Canadian Institute for Cybersecurity(CIC) and University of New Brunswick(UNB) contains benign and the most up-to-date common attacks, which resembles the true real-world data. https://www.unb.ca/cic/datasets/ids-2017.html<br/>
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
![15categories](https://raw.githubusercontent.com/CSFanLi/IDS/main/images/15categories.png)
<br/>
![8categories](https://raw.githubusercontent.com/CSFanLi/IDS/main/images/8categories.png)
# peprocessing
# Training Model
# Result
