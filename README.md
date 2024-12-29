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


Okay, based on the provided graphs and numerical data, here's an analysis and description of each cluster, along with their distinguishing characteristics and potential marketing strategies summarized in a table.

**Analysis of Clusters:**

First, let's analyze the provided charts and the numerical data to understand the core features of each cluster.

**Cluster 0:** (13057 - 41.7% of total customers)

*   **Cuisine Preference:**  Relatively balanced cuisine preferences, but leans slightly more towards American, Italian, and street food/snacks. Lower preference for healthy options.
*   **Promotion Type:** Mostly buys without promotions (NO PROMO). They do engage with freebie promotions more than some clusters.
*   **Region:** Region data is somewhat balanced
*  **Payment Method:** Primarily uses CARD payments.
* **Time:** Orders on weekdays, and lunch and dinner orders are common.

*   **Numerical analysis:** Average values for all order-related metrics (chain count, order count, days between orders). Tendency to spend less overall.

**Cluster 1:** (11885 - 38% of total customers)

*   **Cuisine Preference:** Similar to cluster 0 in liking American and Italian but with slightly less focus on Street Food, and more on Asian.
*  **Promotion Type:** Buys without promotions most often, but also use delivery and discount more than some clusters
*   **Region:** Has moderate numbers in regions 2,4, and 8, but not as high as others.
* **Payment Method:** Prefers card payments, but less than cluster 0.
*  **Time:** Similar to Cluster 0 for weekdays and lunch and dinner orders.

*   **Numerical analysis:** Overall low values for all order-related metrics. Tendency to spend a little less overall compared to cluster 0.

**Cluster 2:** (2679 - 8.6% of total customers)

*   **Cuisine Preference:** Distinctly favors Asian cuisines, notably Italian and other cuisines that are not snacks.
*   **Promotion Type:** Has high use of no promo offers, but less frequent promotions compared to other clusters.
*   **Region:** High concentration in region 2.
*   **Payment Method:** Almost exclusively pays by card.
*  **Time:** Orders a little more often on the weekdays, and predominantly lunch and dinner.

*   **Numerical analysis:** High positive values for chain count, order count, total spending, total number of food types. This cluster is more active and spends more than the other clusters.

**Cluster 3:** (2115 - 6.8% of total customers)

*   **Cuisine Preference:** More balanced preferences, but leans towards Asian and American, as well as a small preference for healthy foods.
*   **Promotion Type:** High use of no promo and discount promotions.
*   **Region:** A high number in region 2 and a moderate number in 8.
*  **Payment Method:** Prefers card payments over others, but also makes use of digi payments.
*  **Time:** Higher order rate during the weekdays, and predominantly during lunch and dinner.

*  **Numerical analysis:** Moderate values for order related data, and a slight positive value for total spending, and number of food types.

**Cluster 4:** (1543 - 4.9% of total customers)

*   **Cuisine Preference:** Strong preference for OTHER cuisine, followed by American. Japanese and beverage spending is also present.
*   **Promotion Type:** Uses no promo or delivery options most often.
*   **Region:** This cluster is highly concentrated in region "U"
*   **Payment Method:** Almost exclusively pays by card.
*   **Time:** Higher order rate during late night and breakfast, but moderate numbers on other times.

*   **Numerical analysis:** Positive values for most metrics, notably high values for CUI_Total_Amount_Spent, and HR_LateNight_Breakfast_PC. This group stands out for its high spend and unique ordering time.

**Customer Profiles Table:**

| Cluster | Characteristics | Potential Marketing Strategy |
|---|---|---|
| **Cluster 0 (Balanced Base)** | - Balanced cuisine preferences (American, Italian, and street food)<br>- Buys without promotions often<br>- Balanced region demographics<br>- Predominantly uses card payments<br>- Orders primarily on weekdays during lunch and dinner. <br>- Average values for order metrics; moderate spend. | - Maintain current service levels; offer minor incentives.<br>- Loyalty program for small freebies and discounts.<br>- Targeted communication with deals on their common cuisines.   |
| **Cluster 1 (Budget Conscious)** | - American and Italian cuisine with more focus on Asian cuisine. <br>- More use of delivery and discount promotions. <br>- Moderate presence in multiple regions.<br>- Primarily uses card payments but uses digital and cash payments slightly more than others.<br>- Orders most often on weekdays during lunch and dinner. <br>- Lowest values for most order-related metrics; low overall spending. | - Emphasize value-focused deals and promotions.<br>- Delivery promotions and freebies.<br>- Introduce new affordable food options. |
| **Cluster 2 (Asian Cuisine Enthusiasts)** | -  Strong preference for Asian, Italian, and other non-snack cuisines. <br>- Buys without promotions often; less engagement with promotions.<br>- High concentration in region 2. <br>- Almost exclusively pays by card.<br>- Orders primarily during the weekdays, and for lunch and dinner.<br>- High order count, total spend, and number of food types; most active and high spenders. | - Introduce new and specialty Asian dishes. <br>- Focus on upselling experiences over discounts.<br>- Reward frequent customers with exclusive menu options. |
| **Cluster 3 (Balanced Discount Hunters)** | - Balanced preference across Asian and American, as well as some healthy options.<br>- Uses no promo and discount promotions often.<br>- High presence in region 2 and 8. <br>- High number of card payments, but also some digital payment. <br>- Weekday orders; predominantly lunch and dinner. <br>- Moderate values for order related metrics; moderate spend. | - Offer frequent and personalized discounts.<br>- Promote different cuisines weekly for variety.<br>- Enhance mobile app to encourage interaction. |
| **Cluster 4 (Late Night/Breakfast Spenders)** | - Strong preference for other cuisines, followed by American, Japanese, and beverages.<br>- Uses no promo or delivery options most often.<br>- Concentrated in region "U".<br>- Almost exclusively pays by card.<br>- Orders most during late night and breakfast.<br>- High spending overall, particularly during late night/breakfast; unique ordering times. | - Promote unique breakfast and late-night options.<br>- Engage with late night and breakfast specific promotions.<br>- Highlight convenience of the service in these hours. |



Okay, here's the table with improved column titles, designed for a more professional presentation, along with the populated data from your analysis:

**Customer Segment Analysis and Marketing Strategies**

| **Segment Label** | **Segment Profile & Key Traits** | **Recommended Marketing Approach** |
|---|---|---|
| **Cluster 0: The Balanced Base** (41.7%) | - Broad cuisine preferences (American, Italian, Street Food), low on healthy.<br>- Primarily buys without promotions, some engagement with freebies.<br>- Balanced across regions; uses card payments.<br>- Weekday orders during lunch and dinner; moderate average spend. | - Maintain current offerings; introduce minor, consistent loyalty rewards.<br>- Target promotions for popular cuisines and combo deals.<br>- Monitor trends and maintain current service level. |
| **Cluster 1: The Value Seekers** (38%) | - Similar to Cluster 0, with more Asian preference, less Street Food.<br>- Utilizes delivery and discount promos.<br>- Moderate presence in multiple regions, card payments.<br>- Orders on weekdays for lunch and dinner; low spending on average. | - Focus on value-driven deals, free delivery, and discount combos.<br>- Introduce budget-friendly food options and promotions.<br>- Optimize communications with promotional codes and limited-time offers.|
| **Cluster 2: The Asian Food Connoisseurs** (8.6%) | - Distinct preference for Asian, Italian, and other non-snack options.<br>- Less engaged with promotions; High concentration in Region 2, card payments.<br>- Predominantly weekday lunch and dinner orders; high activity & spend.<br>- High order count, spending, & number of food types. | - Expand menu with new, unique Asian dishes; introduce specialty items.<br>- Emphasize premium dining experience over discounts; offer personalized service.<br>- Exclusive menu sneak peeks, early-access to new cuisine options.|
| **Cluster 3: The Discount Savvy** (6.8%) | - Balanced preferences, with slight leans towards Asian, American, and healthy.<br>- Uses discount and no promo offers; Region 2 and 8 are common, card & digi payments.<br>- Weekday orders during lunch and dinner; moderate order values and spend. | - Offer regular, targeted, and personalized discount promotions; create varied offers.<br>- Weekly cuisine spotlights and rotating meal deals.<br>- Incentivize mobile app interaction; gamify user experience for discounts.|
| **Cluster 4: The Night Owls** (4.9%) | - Unique preference for "other" cuisine, followed by American, Japanese, & beverages. <br>- Uses delivery/no promo offers; concentrated in Region "U"; card payments.<br>- Primarily orders late night & breakfast; highest spending in this time slot.<br>- High overall spend, notable at late-night/breakfast hours; unique order times. | - Highlight breakfast and late-night specific food items and offerings.<br>- Run specific promotions to promote late-night and breakfast services.<br>- Emphasize convenience during late-night and breakfast ordering. |

**Key Improvements in this version:**

*   **Clear Column Titles:**
    *   "Segment Label" :  Clear and concise way to refer to each segment.
    *   "Segment Profile & Key Traits":  More descriptive and all encompassing of the key characteristics.
    *   "Recommended Marketing Approach": More action-oriented and focused on marketing strategies.
*   **Concise Descriptions:**  The cluster descriptions are summarized for easier scanning and understanding, using bullet points for better readability.
*   **Percentage Added:** The percentage of customers in each cluster was included for a quick reference and is included in the segment title
*   **Action-Oriented Strategies:** Marketing strategy descriptions are phrased in terms of actions to take.

This table is now more suitable for a business presentation or a work document, providing a clear and actionable overview of each customer segment and the strategies to engage them effectively.


**Notes:**

*   The segmentation is based on the attributes available in the provided data.
*   Marketing strategies are examples and can be refined based on further analysis and business goals.
*   Customer engagement and feedback should be used to further iterate and customize these profiles and strategies.


