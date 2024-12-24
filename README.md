# DM Project 24.25 - [ABCDEats Inc. | Notebooks]

Work developed in the Data Mining project of the Master's in Data Science and Advanced Analytics at NOVA IMS.

> This project aims to explore and analyze customer data for **ABCDEats Inc.**, a food delivery service, collected over 3 months across 3 cities. The goal is to uncover insights into customer behavior, trends, and patterns that can help enhance marketing strategies, improve service quality, and drive revenue growth.

<br>

#### Group 37

  - André Silvestre, 20240502
  - Filipa Pereira, 20240509
  - Umeima Mahomed, 20240543
  
<br>

## **Notebooks Structure**

- [**EDA**](./DM2425_Part1_37.ipynb)
- **2nd Part**
  - [Data Preprocessing](./DM2425_Part2_37_01.ipynb)
    - (Repetir age_groups)
    - Outliers - Detetar e Tratar
    - Missing Values - Tratar
    - Scaling - **StandardScaler**
    - Encoding - **OneHotEncoder**
    - Refazer EDA (Simples)
    - PCA + Criar novas features
    - Correlation Matrix - Ver se há features redundantes 
    - (Escolher variáveis p/ diferentes perspetivas)
    - ... Save the data -> **`data_preprocessed.csv`** (Will be used in clustering notebooks)
  - [Hierarchical Clustering](./DM2425_Part2_37_02.ipynb)
  - [K-Means Clustering](./DM2425_Part2_37_03.ipynb)
  - [SOM - Self Organizing Maps (MiniSOM)](./DM2425_Part2_37_04.ipynb)
  - [Density Clustering](./DM2425_Part2_37_05.ipynb)
  - [Cluster Analysis](./DM2425_Part2_37_06.ipynb)