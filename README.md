# **Online Retail Customer Segmentation**

This repository contains an end-to-end project for customer segmentation using transactional data from a UK-based online retail store. The primary goal is to identify distinct customer groups based on their purchasing behavior. This is achieved by implementing RFM (Recency, Frequency, Monetary) analysis and then applying the K-Means clustering algorithm to uncover actionable customer segments for targeted marketing campaigns.

---

## **Project Workflow** ⚙️

The entire analysis is documented in the `online-retail-data-clustering.ipynb` Jupyter notebook. The key steps are:

1.  **Data Exploration and Cleaning**: The raw dataset is first explored to understand its structure and identify inconsistencies. The cleaning process involves:
    * Removing cancelled orders and non-product transactions (e.g., postage).
    * Dropping records with missing `Customer ID`s.
    * Filtering out entries with negative quantities or zero prices.

2.  **Feature Engineering with RFM Analysis**: The cleaned transactional data is transformed into a customer-centric view by calculating three key metrics for each customer:
    * **Recency (R)**: How recently a customer made a purchase (days since the last transaction).
    * **Frequency (F)**: How often a customer makes a purchase (total number of unique invoices).
    * **Monetary Value (M)**: How much money a customer spends (total sales value).

3.  **Data Scaling**: The RFM features are scaled using `StandardScaler` to ensure they are on a comparable scale, which is crucial for distance-based algorithms like K-Means.

4.  **K-Means Clustering**:
    * The **Elbow Method** and **Silhouette Score** are used to determine the optimal number of clusters (`k`). For this dataset, `k=3` was chosen as the most appropriate number of segments.
    * The K-Means algorithm is then applied to the scaled RFM data to group customers into three distinct clusters.

5.  **Visualization and Interpretation**: The resulting clusters are visualized using 3D scatter plots and combined bar/line charts to analyze the characteristics of each customer segment based on their average RFM values. This allows for the creation of customer personas (e.g., "High-Value Loyal Customers," "Recent but Low-Spending Customers," etc.).

---

## **Dataset** 🗂️

The project uses a single dataset which is a transnational data set that contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.

* **Source**: [UCI Machine Learning Repository: Online Retail Data Set](https://archive.ics.uci.edu/ml/datasets/online+retail)

---

## **How to Run** ▶️

To replicate this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/customer-segmentation.git](https://github.com/your-username/customer-segmentation.git)
    cd customer-segmentation
    ```

2.  **Install the required libraries:**
    ```bash
    pip install -r requirements.txt
    ```
    *(The `requirements.txt` file should contain the following):*
    ```
    pandas
    matplotlib
    seaborn
    scikit-learn
    jupyter
    openpyxl
    ```

3.  **Launch Jupyter Notebook and open `online-retail-data-clustering.ipynb`:**
    ```bash
    jupyter notebook
    ```
    Run all the cells in the notebook to see the entire workflow from data cleaning to cluster visualization.

---

## **Results** 📈

The analysis successfully segments customers into three distinct clusters, each with different purchasing behaviors. The final visualizations in the notebook provide a clear interpretation of these segments, offering valuable insights that can be used to develop targeted marketing strategies, improve customer retention, and personalize the customer experience.
