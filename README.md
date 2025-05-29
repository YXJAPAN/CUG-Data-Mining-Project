# Customer Segmentation using K-Means Clustering

**Author:** [Changming Yao]
**Date:** May 29, 2025
**Course:** CS 422

---

#### Abstract
This project demonstrates the application of K-Means clustering, an unsupervised machine learning algorithm, to segment customers from the "Mall_Customers.csv" dataset. Based on their annual income and spending score, customers were grouped into five distinct segments. The analysis involved data loading, exploratory data analysis (EDA), determining the optimal number of clusters using the Elbow Method, model training, and interpretation of the resulting customer segments. Key findings reveal identifiable customer profiles such as "Target (High Value)," "Affluent Frugal," "Standard," "Young Enthusiasts," and "Careful / Economical." These segments provide valuable insights for developing targeted marketing strategies. Future work could involve incorporating more features, exploring other clustering algorithms, and applying quantitative evaluation metrics like the Silhouette Score.

---

#### Rationale
Understanding customer behavior is crucial for businesses to tailor their products, services, and marketing efforts effectively. Customer segmentation allows businesses to move away from a one-size-fits-all approach and engage with specific customer groups in a more personalized and impactful manner. By identifying distinct segments within their customer base, companies can optimize resource allocation, improve customer satisfaction, and ultimately enhance profitability. This project addresses the common business need to understand different customer archetypes within a mall setting based on easily obtainable metrics like income and spending patterns.

---

#### Research Question
How can mall customers be effectively segmented into distinct groups based on their annual income and spending score using K-Means clustering, and what are the defining characteristics and potential marketing implications of these segments?

---

#### Data Sources
The project utilizes the "Mall_Customers.csv" dataset. This dataset contains information about mall customers, including:
* `CustomerID`: A unique identifier for each customer.
* `Genre` (Gender): The gender of the customer (Male/Female).
* `Age`: The age of the customer.
* `Annual Income (k$)`: The annual income of the customer in thousands of dollars.
* `Spending Score (1-100)`: A score assigned by the mall based on customer spending behavior (higher score means higher spending).

The dataset consists of 200 customer records with no missing values.

---

#### Methodology
The project followed a standard data mining workflow:
1.  **Data Loading and Inspection:** The `Mall_Customers.csv` dataset was loaded using pandas. Initial inspection involved checking the shape, data types, and for missing values.
2.  **Exploratory Data Analysis (EDA):** Descriptive statistics were calculated, and distributions of key features (`Age`, `Annual Income (k$)`, `Spending Score (1-100)`) were visualized using histograms. A pairplot was generated to observe relationships, particularly between `Annual Income (k$)` and `Spending Score (1-100)`.
3.  **Feature Selection:** `Annual Income (k$)` and `Spending Score (1-100)` were selected as the primary features for K-Means clustering.
4.  **Determining Optimal Number of Clusters:** The Elbow Method was employed by calculating the Within-Cluster Sum of Squares (WCSS) for a range of cluster numbers (1 to 10). The "elbow" point on the WCSS plot indicated the optimal `k`.
5.  **Model Training:** A K-Means clustering model was trained using the optimal number of clusters (`k=5`), with `init='k-means++'`, `n_init=10`, and `random_state=42` for reproducibility.
6.  **Cluster Visualization and Interpretation:** The resulting clusters were visualized on a scatter plot of annual income versus spending score. The characteristics of each segment (average age, income, spending score, and count) were analyzed to define customer profiles.

---

#### Results
The K-Means clustering algorithm successfully segmented the 200 customers into 5 distinct groups based on their annual income and spending score. The characteristics of these segments are summarized below (based on `random_state=42`):

* **Segment 0: Standard / Average Customers**
    * Count: 81
    * Average Age: ~42.72 years
    * Average Annual Income: ~$55.30k
    * Average Spending Score: ~49.52
* **Segment 1: Target / High Value**
    * Count: 39
    * Average Age: ~32.69 years
    * Average Annual Income: ~$86.54k
    * Average Spending Score: ~82.13
* **Segment 2: Young Enthusiasts (Low Income, High Spend)**
    * Count: 22
    * Average Age: ~25.27 years
    * Average Annual Income: ~$25.73k
    * Average Spending Score: ~79.36
* **Segment 3: Affluent Frugal (High Income, Low Spend)**
    * Count: 35
    * Average Age: ~41.11 years
    * Average Annual Income: ~$88.20k
    * Average Spending Score: ~17.11
* **Segment 4: Careful / Economical (Low Income, Low Spend)**
    * Count: 23
    * Average Age: ~45.22 years
    * Average Annual Income: ~$26.30k
    * Average Spending Score: ~20.91

Visualizations (Elbow Method plot, cluster scatter plot, segment characteristics bar chart) effectively illustrated these findings.

---

#### Next steps
Based on the current findings, several next steps could enhance this project:
1.  **Incorporate Additional Features:** Include `Age` and `Genre` (after proper encoding and feature scaling) in the clustering process to potentially uncover more nuanced segments.
2.  **Explore Alternative Clustering Algorithms:** Implement and compare results from other algorithms like DBSCAN or Hierarchical Clustering, which might handle different cluster shapes or densities better.
3.  **Quantitative Cluster Evaluation:** Utilize metrics such as the Silhouette Score to provide a quantitative assessment of cluster quality and to further validate the choice of `k`.
4.  **Deeper Segment Profiling:** If more detailed data were available (e.g., purchase history, product categories preferred, frequency of visits), a more in-depth profiling of each segment could lead to even more specific marketing actions.
5.  **A/B Testing:** Design and implement A/B tests for marketing strategies tailored to the identified segments to measure their effectiveness.

---

#### Conclusion
This project successfully demonstrated the use of K-Means clustering for customer segmentation using the "Mall Customers" dataset. Five distinct customer segments were identified, each with unique characteristics regarding their annual income, spending score, and average age.

* **Positive Results:** The clusters are well-defined and provide actionable insights for targeted marketing. For example, "Target / High Value" customers (Segment 1) can be engaged with premium offers, while "Careful / Economical" customers (Segment 4) might respond better to discounts.
* **Recommendations:** Businesses can use these segments to personalize communication, promotions, and product recommendations, thereby improving customer engagement and potentially increasing sales.
* **Caveats/Cautions:** The segmentation is based on only two primary features. Adding more relevant features could refine the segments. The "Spending Score" is a pre-assigned metric; understanding its calculation could provide further context. The dataset size is relatively small, so findings might not generalize perfectly to a much larger customer base without further validation.

---

### Bibliography
* Dataset: "Mall_Customers.csv" (Source commonly attributed to various online repositories for practice datasets).
* Scikit-learn documentation for KMeans: [https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html)
    *(Add any other specific references or tools you used, e.g., for visualization libraries or theoretical concepts, in a consistent citation style like IEEE or ACM if required by your course).*

---

