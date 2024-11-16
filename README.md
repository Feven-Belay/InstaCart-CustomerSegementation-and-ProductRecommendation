# Customer Segmentation and Product Recommendation System

## Overview
This project aims to analyze customer behavior and preferences based on historical transaction data and product information. It provides insights into shopping patterns, customer segmentation, and personalized product recommendations using clustering and association rule mining techniques.

---

## Objectives
1. **Customer Segmentation Based on Shopping Preferences**:
   - Analyze frequency of ordering and reordering.
   - Segment customers into behavioral clusters (e.g., loyal, casual, and mixed shoppers).

2. **Customer Segmentation Based on Product Preferences**:
   - Cluster products using product details (e.g., names, aisles, and departments).
   - Analyze and identify product preferences for each user.

3. **Product Recommendation**:
   - Generate personalized recommendations for customers using the Apriori algorithm and association rules.

---

## Data Sources
The project uses the following datasets:
- `orders.csv`: Contains order-level details (e.g., user IDs, order IDs, order timing).
- `order_products__prior.csv`: Contains product details for prior orders.
- `aisles.csv`, `departments.csv`, `products.csv`: Contain metadata for products, including aisles and departments.

---

## Methodology
### 1. **Customer Segmentation Based on Shopping Preferences**
   - **Feature Engineering**:
     - Group orders by user to calculate features like total orders, average days between orders, reorder ratio, etc.
   - **Sampling**:
     - Use a 10% random sample for efficient computation.
   - **Clustering**:
     - Standardize features using `StandardScaler`.
     - Apply the Elbow Method to determine the optimal number of clusters.
     - Cluster users using the KMeans algorithm.
   - **Insights**:
     - Each customer is assigned a segment (e.g., casual, loyal).
     - The segments help understand customer shopping behavior.

### 2. **Customer Segmentation Based on Product Preferences**
   - **Feature Engineering**:
     - Extract textual features from product names using `TfidfVectorizer`.
     - One-hot encode aisle and department IDs for categorical features.
     - Combine text and categorical features for clustering.
   - **Clustering**:
     - Apply KMeans clustering to group products into meaningful segments.
     - Link customer orders to product segments for user-specific insights.
   - **Insights**:
     - Identify product preferences for each customer segment.

### 3. **Product Recommendation System**
   - **Association Rule Mining**:
     - Convert transactional data into a basket format for Apriori algorithm.
     - Generate frequent itemsets and association rules with minimum support and confidence thresholds.
   - **Recommendation Generation**:
     - Identify products to recommend based on user purchase history and association rules.
     - Exclude products the user has already purchased.
   - **Personalization**:
     - Tailor recommendations to align with user preferences and past purchases.

---

## Tools and Libraries
- **Programming Language**: Python
- **Libraries**:
  - `pandas`, `numpy` for data manipulation.
  - `scikit-learn` for clustering and preprocessing.
  - `mlxtend` for association rule mining.
  - `matplotlib` for visualization.

---

## Outputs
1. **Customer Segments**:
   - Behavioral clusters with insights into shopping patterns.
   - Product preference clusters for better understanding of user interests.
2. **Recommendations**:
   - Personalized product recommendations for each user.

---

## Example
### Input:
- **User ID**: 1883
- **Last Purchased Products**:
  - Honeycrisp Apples
  - Banana
  - Raspberries
  - Sesame Street Organic Homestyle Mini Pancakes
  - Honey Lemon with Echinacea Cough Suppressant Throat Drops

### Output:
- **Recommended Products**:
  - Organic Strawberries
  - Organic Baby Spinach

---

## How to Run the Code
1. Clone this repository and navigate to the project directory.
2. Install required Python libraries:
   ```bash
   pip install pandas numpy scikit-learn mlxtend matplotlib
