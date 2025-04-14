# 🛍️ Customer Segmentation Analysis Using Machine Learning

This project focuses on segmenting retail customers based on their demographics, purchasing behavior, and promotional preferences. By identifying distinct customer segments, the goal is to help drive personalized marketing strategies, improve customer retention, and increase overall business revenue.

---

## 📂 Dataset Overview

- Source: Kaggle (simulated retail data)
- Total records: 3,900 customers
- Features: Age, Gender, Location, Purchase Amount, Category, Previous Purchases, Subscription Status, Promo/Discount usage, etc.

---

## 🧹 1. Data Understanding and Preprocessing

- Checked for and confirmed **no duplicates**
- Imputed missing values (`Purchase Amount`, `Review Rating`, `Previous Purchases`) using **median**
- Removed rows with `Purchase Amount = 0` **only** when **no discount or promo** was applied
- Detected and removed **3 outlier rows** in `Previous Purchases` using the IQR method
- Engineered new features:
  - `Is Promo Buyer` → customers who used a promo code or discount
  - `Age Group` → binned into '18–29', '30–50', and '51+'
- Applied **Label Encoding** to categorical features
- Applied **StandardScaler** to normalize numerical inputs before clustering

---

## 📊 2. Exploratory Data Analysis (EDA)

- **Demographics**: Majority of customers fall in age 30–50+; male customers dominate all age groups
- **Popular categories**: Clothing is the top category in both volume and repeat purchases
- **Size trends**: Most purchases are in Medium and Large sizes
- **Top locations**: Montana, Illinois, and Idaho have the highest total purchase volumes
- **Subscriptions**: Non-subscribers are more common, but spend similarly to subscribers
- **Seasonality**: Purchase volumes are consistent across seasons
- **Correlation**: Weak correlation among features; supports independent feature use for clustering

---

## 🤖 3. Clustering Techniques Used

### 🔹 KMeans Clustering
- Number of clusters: 4
- Features used: Age, Gender, Location, Category, Size, Previous Purchases, Purchase Amount, Is Promo Buyer
- StandardScaler used for normalization
- PCA applied to reduce to 2D for visual interpretation

### 🔹 DBSCAN Clustering
- `eps = 2.0`, `min_samples = 5`
- Found 3 meaningful clusters
- Detected **no noise points**
- Captured dense clusters without predefining cluster count

---

## 📌 4. Cluster Insights & Recommendations

The clustering revealed four distinct customer types:

- **Promo-driven shoppers**  
  Respond well to discounts; ideal for flash deals, personalized offers, and loyalty programs

- **Premium buyers**  
  Brand-loyal customers (mostly female) who value quality; best engaged through exclusivity and early access

- **Budget-conscious frequent shoppers**  
  Lower spend per order but highly engaged; suited for bundles, referral incentives, and affordable campaigns

- **Consistent non-promo spenders**  
  Steady, promotion-agnostic buyers; respond well to seasonal collections and personalized recommendations

These segments enable targeted marketing strategies that improve retention and drive growth.

---

## 📈 5. Conclusion

This project demonstrates how machine learning can uncover meaningful customer segments using behavioral and demographic data. Both KMeans and DBSCAN revealed actionable clusters that support:

- Targeted marketing and promotions  
- Loyalty program design  
- Geo-targeted campaigns  
- Inventory planning based on size/category demand

---

## 💡 Future Enhancements
- Incorporate **time-based features** (recency, frequency)
- Try advanced segmentation (e.g., Hierarchical Clustering, RFM analysis)
- Evaluate performance over time or by campaign success
