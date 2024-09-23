# Customer Segmentation Clustering Analysis

This repository contains a Jupyter Notebook that performs customer segmentation using clustering algorithms on an online retail dataset. The goal of this analysis is to group customers based on their purchasing behavior, enabling targeted marketing strategies for each customer segment.

## Project Overview

The notebook follows these main steps:

1. **Data Loading**: Load the dataset (`online_retail_II.xlsx`), which contains purchase records of an online retail store.
2. **Data Preprocessing**: Clean and preprocess the data, including handling invalid or special stock codes, and filtering out unnecessary entries.
3. **Clustering**: Apply KMeans clustering to group customers based on key attributes such as purchase frequency, monetary value, and recency.
4. **Cluster Analysis**: Analyze the resulting clusters and provide actionable insights for each customer segment.

## Dataset

The dataset used for this analysis is the **Online Retail II** dataset, which includes the following fields:

- **InvoiceNo**: Invoice number for each transaction.
- **StockCode**: Unique product identifier.
- **Description**: Description of the product.
- **Quantity**: Number of products purchased.
- **InvoiceDate**: Date of the transaction.
- **UnitPrice**: Price of a single product.
- **CustomerID**: Unique identifier for the customer.
- **Country**: Country of the customer.

### Notes on Data Cleaning:

Certain stock codes were identified as non-informative or invalid and were excluded from the analysis:

- Codes like `DCGS`, `D`, `DOT`, `M`, etc., were excluded due to their special meanings (e.g., postage, manual transactions, discounts).
- Special attention was paid to codes such as `PADS` and `SP1002`, which were analyzed further.

## Methodology

1. **Data Scaling**: The data is normalized using `StandardScaler` to ensure that all features contribute equally to the clustering algorithm.
2. **KMeans Clustering**: The KMeans algorithm is applied to segment customers into distinct groups.
3. **Silhouette Score**: This metric is used to evaluate the quality of the clustering and determine the optimal number of clusters.
4. **Customer Segmentation**: The clusters are analyzed and labeled based on customer behavior:
   - **Cluster 0 ("Retain")**: Customers who purchase infrequently but are high-value buyers.
   - **Cluster 1 ("Re-Engage")**: Customers who used to buy frequently but have reduced their activity.
   - **Cluster 2 ("Nurture")**: Customers who are moderately engaged and show potential for upselling.
   - **Cluster 3 ("Reward")**: Highly valuable and frequent buyers, the most loyal customers.
   - **Cluster -1 (Monetary Outliers) PAMPER**: High spenders but not necessarily frequent buyers. Their purchases are large but infrequent.
   - **Cluster -2 (Frequency Outliers) UPSELL**: Frequent buyers who spend less per purchase. These customers are consistently engaged but might benefit from upselling opportunities.
   - **Cluster -3 (Monetary & Frequency Outliers) DELIGHT**: The most valuable outliers, with extreme spending and frequent purchases. They are likely your top-tier customers who require special attention.

## Cluster Distribution with Average Feature Values

![Cluster Distribution with Average Feature Values](./images/Cluster%20Distribution%20with%20Average%20Feature%20Values.png)
