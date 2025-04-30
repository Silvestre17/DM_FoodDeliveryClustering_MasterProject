# 🍕 Data Mining Project - ABCDEats Inc. Customer Segmentation 📦

### **👥 Group 37 Members**

-   André Silvestre, 20240502
-   Filipa Pereira, 20240509
-   Umeima Mahomed, 20240543

---

## **📝 Description**

This repository documents the **Data Mining** project undertaken for the Master's in Data Science and Advanced Analytics at NOVA Information Management School (NOVA IMS). The project focuses on ***ABCDEats Inc.***, a fictional food delivery service. We analyze customer data collected over 3 months from 3 cities to develop a data-driven segmentation strategy, enabling ABCDEats to tailor its marketing and services effectively.

<br>

## **✨ Objective**

The primary objectives of this project are to:

1.  Conduct an **Exploratory Data Analysis (EDA)** to understand customer behaviors, trends, and patterns.
2.  **Preprocess** the data, handling inconsistencies, missing values, outliers, and perform feature engineering/selection.
3.  Apply and evaluate various **Clustering Algorithms** (*Hierarchical*, *K-Means*, *SOM*, *Density-based*) from different perspectives (***Overall***, ***Value-based***, ***Behavior-based***).
4.  Develop a **Final Customer Segmentation** solution by comparing and potentially merging results from different approaches.
5.  **Profile** the resulting customer segments, highlighting their key characteristics.
6.  Suggest actionable **Business Applications** and marketing strategies for each segment.
7.  (Optional) Develop an interactive **Web Application** for exploring the EDA and segmentation results.

<br>

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

3.  **Data Preparation:** 🛠️
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

4.  **Modeling:** 🧠
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

5.  **Evaluation:** ✅
    *   Determined optimal cluster numbers using Elbow method (Inertia/SSE), Silhouette analysis, R² metric (for HC), AIC/BIC (for GMM), and visual inspection (dendrograms).
    *   Compared performance across algorithms and perspectives based on R² and silhouette scores.
    *   Selected best-performing methods for each perspective (SOM+K-Means overall, K-Means value, SOM+K-Means behavior).
    *   Manually merged the 'Value' (k=3) and 'Behavior' (k=4) solutions based on centroid analysis to create a final, more robust 5-cluster solution.
    *   Visualized cluster separation using t-SNE and UMAP.

6.  **Deployment:** 🚀
    *   **Profiling:** Characterized the final 5 clusters using descriptive statistics, bar plots, and heatmaps.
    *   **Business Applications:** Defined marketing strategies tailored to each segment.
    *   **(Optional) Interactive Dashboard:** Developed a web application using Streamlit and Plotly for dynamic exploration of EDA and segmentation results. [Access the App Here!](https://dm-project-abcdeats-group37.streamlit.app/)
         * ➡️ **Dashboard App Repository:** [Silvestre17/DM_Dashboard](https://github.com/Silvestre17/DM_Dashboard_Group37) ⬅️

    <p align="center">
      <a href="https://www.streamlit.io/"><img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit" /></a>
      <a href="https://www.plotly.com/"><img src="https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white" alt="Plotly" /></a>
    </p>

<br>

## **🛠️ Libraries Used**

*   **Core:** `Python`
*   **Data Manipulation:** `pandas`, `numpy`
*   **Visualization:** `matplotlib`, `seaborn`, `plotly`
*   **Machine Learning:** `scikit-learn` (for preprocessing, PCA, K-Means, HC, MeanShift, DBSCAN, GMM, evaluation metrics), `MiniSom` (for SOM)
*   **Web Application:** `streamlit`, `pandas-datareader` (potentially used within Streamlit context)

<br>

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
