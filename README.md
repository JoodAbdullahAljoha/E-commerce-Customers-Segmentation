# E-commerce-Customers-Segmentation

## Project Overview
This project aims to segment customers based on their transactional behaviors and demographic features using unsupervised machine learning techniques. The goal is to identify customer groups that share similar behaviors and use these segments to develop strategies for offering coupons to improve customer loyalty and satisfaction.

---

## Dataset

The dataset consists of five interrelated tables, containing crucial information about customers, transactions, branches, and merchants. The tables are as follows:

### 1. Customers Table
- `customer_id`: Unique identifier for each customer.
- `join_date`: The date the customer joined.
- `city_id`: ID representing the customer's city.
- `gender_id`: ID representing the customer's gender.

### 2. Genders Table
- `gender_id`: Unique identifier for each gender.
- `gender_name`: Name of the gender (e.g., male, female).

### 3. Cities Table
- `city_id`: Unique identifier for each city.
- `city_name`: Name of the city.

### 4. Transactions Table
- `transaction_id`: Unique identifier for each coupon transaction.
- `customer_id`: ID of the customer who performed the transaction.
- `transaction_date`: The date the coupon was claimed.
- `transaction_status`: Status of the coupon (e.g., claimed, burnt).
- `coupon_name`: The name of the coupon.
- `burn_date`: The date the coupon was burnt.
- `branch_id`: ID of the branch where the coupon was burnt.

### 5. Branches Table
- `branch_id`: Unique identifier for each branch.
- `merchant_id`: ID of the merchant who owns the branch.

### 6. Merchants Table
- `merchant_id`: Unique identifier for each merchant.
- `merchant_name`: Name of the merchant.

---

## Project Steps

### 1. Data Preprocessing
- **Load and merge the dataset** from the five interrelated tables.
- **Clean the data** by handling missing values, converting categorical features (e.g., gender_name, city_name) to numerical values using encoding techniques like one-hot encoding.
- **Create relevant features for segmentation**, such as:
  - number of unique merchants.
  - number of transactions for each customer.
  - number of unique branches
  - Transaction status (claimed, burnt).
  - Customer demographic data (gender, city).

---
## 2. Model Development

Train an unsupervised machine learning model for customer segmentation. Techniques used:

- **K-Means Clustering**: A popular algorithm for segmentation into K groups based on customer behavior.
- **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)**: Useful for detecting clusters of varying shapes.
- **Hierarchical Clustering**: A method for creating a tree-like structure to represent customer segments.

---

## 4. Model Evaluation

Use appropriate evaluation metrics to assess the clustering performance:

- **Silhouette Score**: Measures how similar an object is to its own cluster compared to other clusters.


---

## 5. Segment Analysis

After applying clustering algorithms, we obtained **4 distinct customer segments** based on their transaction and branch interaction behaviors.

#### 1. Cluster 1: High Transaction Count, High Unique Branches
- **Characteristics**: Customers have made many transactions and interacted with many unique branches.
- **Recommendation**: Offer VIP coupons, exclusive discounts, or loyalty rewards to maintain and increase engagement.

#### 2. Cluster 2: High Transaction Count, Low Unique Branches
- **Characteristics**: Frequent shoppers but primarily visit a few branches.
- **Recommendation**: Offer branch-specific discounts or deals for other branches to encourage exploring new locations.

#### 3. Cluster 3: Low Transaction Count, High Unique Branches
- **Characteristics**: Customers have interacted with many branches but made fewer transactions.
- **Recommendation**: Target with promotions like "Spend More, Save More" to boost transaction frequency.

#### 4. Cluster 4: Low Transaction Count, Low Unique Branches
- **Characteristics**: Customers have shown minimal engagement with both transactions and branches.
- **Recommendation**: Offer welcome-back or re-engagement discounts to entice them back and encourage transactions.

---

## Requirements

This project requires the following Python libraries:

- **Pandas**: For data manipulation and preprocessing.
- **NumPy**: For numerical operations.
- **Scikit-learn**: For clustering algorithms (K-Means, DBSCAN, Hierarchical Clustering) and evaluation metrics.
- **Matplotlib / Seaborn**: For visualizing clusters and analysis results.
- **Scipy**: For hierarchical clustering and distance calculations.

