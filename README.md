<p align="center">
   <a href="https://dm-project-abcdeats-group37.streamlit.app/">
        <img src="https://github.com/Silvestre17/DM_Dashboard_Group37/blob/main/static/ABCDEats_Banner.png" alt="ABCDEats Banner" width="800">
    </a>
</p>

# 🍕 ABCDEats Inc: A Data Mining Approach to Customer Segmentation 📦

<p align="center">
    <!-- Project Links -->
    <a href="https://github.com/Silvestre17/DM_FoodDeliveryClustering_MasterProject"><img src="https://img.shields.io/badge/Project_Repo-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Repo"></a>
    <a href="https://dm-project-abcdeats-group37.streamlit.app/"><img src="https://img.shields.io/badge/Live_Dashboard-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Live Dashboard"></a>
    <a href="https://github.com/Silvestre17/DM_Dashboard_Group37"><img src="https://img.shields.io/badge/Dashboard_Code-100000?style=for-the-badge&logo=github&logoColor=white" alt="Dashboard Code Repo"></a>
</p>

## **📝 Description**

This repository documents a comprehensive **Data Mining** project focused on ***ABCDEats Inc.***, a fictional food delivery service. We analyze a rich dataset of customer transactions and behaviors to develop a data-driven segmentation strategy. The goal is to empower ABCDEats to move beyond a one-size-fits-all approach and tailor its marketing, promotions, and service offerings to distinct customer profiles.

## **✨ Objective**

The primary objectives of this project are to:

1.  Conduct an **Exploratory Data Analysis (EDA)** to understand customer behaviors, trends, and patterns.
2.  **Preprocess** the data, handling inconsistencies, missing values, outliers, and perform feature engineering/selection.
3.  Apply and evaluate various **Clustering Algorithms** (*Hierarchical*, *K-Means*, *SOM*, *Density-based*) from different perspectives (***Overall***, ***Value-based***, ***Behavior-based***).
4.  Develop a **Final Customer Segmentation** solution by comparing and potentially merging results from different approaches.
5.  **Profile** the resulting customer segments, highlighting their key characteristics.
6.  Suggest actionable **Business Applications** and marketing strategies for each segment.
7.  (Optional) Develop an interactive **Web Application** for exploring the EDA and segmentation results.

## 🎓 Project Context

This project was developed for the **Data Mining** course as part of the **[Master's in Data Science and Advanced Analytics](https://www.novaims.unl.pt/en/education/programs/postgraduate-programs-and-master-degree-programs/master-degree-program-in-data-science-and-advanced-analytics-with-a-specialization-in-data-science/)** program at **NOVA IMS**. The work was completed during the **1st Semester** of the 2024/2025 academic year.


## 🛠️ Technologies & Libraries

The project was implemented entirely in **Python**, leveraging a powerful stack of libraries for data science, machine learning, and web deployment.

<p align="center">
    <a href="https://www.python.org/">
        <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
    </a>
    <a href="https://jupyter.org/">
        <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter Notebook" />
    </a>
    <a href="https://pandas.pydata.org/">
        <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
    </a>
    <a href="https://numpy.org/">
        <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
    </a>
    <a href="https://www.Scikit-Learn.org/">
        <img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn" />
    </a>
    <a href="https://github.com/JustGlowing/minisom"><img src="https://img.shields.io/badge/MiniSom-4CAF50?style=for-the-badge" alt="MiniSom"/></a>
    <br>
    <a href="https://www.streamlit.io/"><img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit" /></a>
    <a href="https://www.plotly.com/"><img src="https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white" alt="Plotly" /></a>
    <a href="https://www.matplotlib.org/"><img src="https://img.shields.io/badge/Matplotlib-D3D3D3?style=for-the-badge&logo=matplotlib&logoColor=black" alt="Matplotlib" /></a>
    <a href="https://www.seaborn.pydata.org/"><img src="https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=seaborn&logoColor=white" alt="Seaborn" /></a>
</p>

## **🗺️ Project Workflow (CRISP-DM)**

The project strictly followed the **CRISP-DM (Cross-Industry Standard Process for Data Mining)** methodology. The overall workflow is visualized below:

<img src="./DMProjectFlowchart.png" alt="Project Workflow" width="900" height="auto" style="display: block; margin: auto;">

*(Diagram summarizing the key phases and steps of the project)*

<br>

## **🏗️ Project Structure (CRISP-DM Phases)**

1.  **Business Understanding:** 💡
    *   Defined the core business problem: Need for effective customer segmentation for ***ABCDEats Inc.*** to personalize marketing and services.
    *   Established project objectives aligned with business goals (improve customer satisfaction, retention, revenue).

2.  **Data Understanding:** 🔍
    *   Explored the initial dataset (31,888 customers, 56 features).
    *   Identified data types, distributions (skewness, kurtosis), and initial relationships (pair plots).
    *   Detected missing values (`customer_age`, `first_order`, `HR_0`), duplicates, and inconsistencies (`'-'` in `customer_region`, `last_promo`; illogical `vendor/product/order_counts`).

    <p align="center">
      <a href="https://pandas.pydata.org/"><img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" /></a>
      <a href="https://www.numpy.org/"><img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" /></a>
      <a href="https://www.matplotlib.org/"><img src="https://img.shields.io/badge/Matplotlib-D3D3D3?style=for-the-badge&logo=matplotlib&logoColor=white" alt="Matplotlib" /></a>
      <a href="https://www.seaborn.pydata.org/"><img src="https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=seaborn&logoColor=white" alt="Seaborn" /></a>
    </p>

3.  **Data Preparation & Feature Engineering 🛠️**
    *   **Cleaning:** Handled duplicates (removed 13), treated inconsistencies (removed 18 illogical rows, reinterpreted '-').
    *   **Missing Value Imputation:** Used deterministic logic (`first_order`, `HR_0`) and `KNNImputer` (`customer_age`).
    *   **Feature Engineering:** Created new features (e.g., `order_count`, `days_between_orders`, `customer_region_buckets`, `last_promo_bin`, CUI totals/averages/most spent, PCA components). Discarded less informative engineered features (e.g., CUI proportions).
    *   **Outlier Handling:** Applied a mixed strategy (modified IQR and manual removal based on boxplots/domain knowledge), retaining 98.61% of data.
    *   **Variable Selection:** Used Spearman correlation (threshold 0.8) to identify and remove redundant features (`vendor_count`, `product_count`, `days_between_orders`, `customer_age`, `customer_age_group`).
    *   **Feature Scaling:** Applied `StandardScaler` to numerical features for distance-based algorithms.
    *   **Dimensionality Reduction:** Used `PCA` separately on CUI and HR feature groups to reduce noise/redundancy while preserving variance (kept 7 CUI PCs, 4 HR PCs). Original DOW variables were retained.

    <p align="center">
      <a href="https://pandas.pydata.org/"><img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" /></a>
      <a href="https://www.Scikit-Learn.org/"><img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn" /></a>
    </p>

4.  **Modeling: Multi-Perspective Clustering 🧠**
    *   Applied multiple clustering algorithms:
        *   Hierarchical Clustering (HC - Agglomerative, Ward linkage)
        *   K-Means
        *   Self-Organizing Maps (SOM - using `MiniSom`) + HC/K-Means
        *   Density-Based: Mean Shift, DBSCAN, Gaussian Mixture Models (GMM)
    *   Performed clustering on 'Overall', 'Value-based', and 'Behavior-based' feature subsets.

    <p align="center">
      <a href="https://www.Scikit-Learn.org/"><img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn" /></a>
      <a href="https://github.com/JustGlowing/minisom"><img src="https://img.shields.io/badge/MiniSom-4CAF50?style=for-the-badge" alt="MiniSom"/></a>
    </p>

5.  **Evaluation & Final Segmentation ✅**
    *   Determined optimal cluster numbers using Elbow method (Inertia/SSE), Silhouette analysis, R² metric (for HC), AIC/BIC (for GMM), and visual inspection (dendrograms).
    *   Compared performance across algorithms and perspectives based on R² and silhouette scores.
    *   Selected best-performing methods for each perspective (SOM+K-Means overall, K-Means value, SOM+K-Means behavior).
    *   Manually merged the 'Value' (k=3) and 'Behavior' (k=4) solutions based on centroid analysis to create a final, more robust 5-cluster solution.
    *   Visualized cluster separation using t-SNE and UMAP.

6.  **Deployment 🚀**
    *   **Profiling:** Characterized the final 5 clusters using descriptive statistics, bar plots, and heatmaps.
    *   **Business Applications:** Defined marketing strategies tailored to each segment.
    *   **(Optional) Interactive Dashboard:** Developed a web application using Streamlit and Plotly for dynamic exploration of EDA and segmentation results. [Access the App Here!](https://dm-project-abcdeats-group37.streamlit.app/)
         * ➡️ **Dashboard App Repository:** [Silvestre17/DM_Dashboard](https://github.com/Silvestre17/DM_Dashboard_Group37) ⬅️

    <p align="center">
      <a href="https://www.streamlit.io/"><img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit" /></a>
      <a href="https://www.plotly.com/"><img src="https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white" alt="Plotly" /></a>
    </p>

## **📈 Results - Final Customer Segments**

Based on the merged clustering solution (Value K-Means + Behavior SOM+K-Means), five distinct customer segments were identified:

| Segment ID | Segment Name             | Key Characteristics                                                                                                                                                                                                | Recommended Marketing Approach                                                                                                                               |
| :--------- | :----------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **0**      | **The Mainstream Base**  | - Largest group (41.74%).<br>- Average spending & behavior, similar to overall dataset.<br>- Moderate to low engagement.<br>- Prefers Asian & American cuisines.<br>- Balanced across regions; uses card payments.           | - Offer tiered loyalty (discounts/perks for higher spending/frequency).<br>- Target promotions for American/Asian cuisines & combo deals.                      |
| **1**      | **The Promo Pursuers**   | - Second largest (38.00%), low engagement (lowest order count).<br>- Low total spend, but high average spend per order.<br>- Likely motivated by delivery promotions.<br>- Slight preference for evening orders & Noodles/Chinese/Chicken. | - Offer free delivery for orders above a certain value.<br>- Implement points-based rewards program redeemable for discounts/free delivery.                   |
| **2**      | **The Convenience Seekers** | - Concentrated in Region 2 (8.56%).<br>- High order frequency (lunch/dinner).<br>- Prefers Chicken, Chinese, Noodles, Other; less Asian/Street Food.<br>- Moderate spenders, but significant volume.                  | - Focus on premium dining experience (personalized service), especially in Region 2.<br>- Offer exclusive menu previews/early access.<br>- Loyalty program rewarding spend per order & frequency. |
| **3**      | **The Balanced Spenders** | - Located mostly in Region 2 & 4 (6.76%).<br>- Similar activity times to Cluster 2 (lunch/dinner) but lower frequency/spend.<br>- Prefers Italian & Other cuisines; less keen on Street Food/Snacks/Asian.           | - Highlight Italian/Other cuisines in promotions (exclusive deals).<br>- Target lunch/dinner promotions.<br>- Offer discount combos for higher spend.            |
| **4**      | **The Late-Night Enthusiasts** | - Highest spenders (absolute & average) (4.93%).<br>- Predominantly in Region 8.<br>- Strong preference for Asian, Snack, Street Food.<br>- Orders primarily late night & early breakfast.<br>- Less preference for Italian/Other. | - Highlight breakfast & late-night specific items/offerings.<br>- Introduce city-specific promotions (Region 8).<br>- Offer special discounts/VIP access for high spenders. |

<br>


### **👥 Group 37 Members**

-   André Silvestre, 20240502
-   Filipa Pereira, 20240509
-   Umeima Mahomed, 20240543
