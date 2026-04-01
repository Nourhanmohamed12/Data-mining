Cafe Sales Analytics & Demand Forecasting
Comprehensive analytics pipeline for cafe transaction data (2012-2015) combining EDA ,clustering, association rules, sequential patterns, price elasticity, and predictive modeling.

Features

Analysis Type       Methods             Key Results

Clustering           DBSCAN              40 clusters** (4020 noise points)

Association Rule     Apriori + Lift      Weekend → School Break (Lift=1.05)

Sequential Patterns  PrefixSpan         1253 patterns** (min support=2)

Price Elasticity     OLS Regression     2.19** (elastic demand)

Demand Forecasting   Box-Cox + OLS      R²=0.72** (significant predictors)

Classification       Logistic Regression  87.45% accuracy

📊 Datasets

Dataset        Records        Key Features

DateInfo       1,349          Holidays, weekends, temperature

Transactions   5,404          Price, quantity, sell_id

SellMeta       11             Items: BURGER, COFFEE, COKE, LEMONADE

Merged         10,840         Complete cafe dataset

🚀 Quick Start

Prerequisites

pip install pandas numpy matplotlib seaborn scikit-learn mlxtend prefixspan statsmodels
Run Analysis
jupyter notebook cafe_analytics.ipynb
# or
python cafe_analysis.py

🛠️ Analytics Pipeline


1. Data Loading → 2. Cleaning → 3. Merging → 4. EDA → 5. Advanced Analytics → 6. Modeling
1. Data Quality


✅ DateInfo: 1,249/1,349 clean (92.7%)
✅ Transactions: 5,404/5,404 clean (100%)
✅ SellMeta: 11/11 clean (100%)
✅ No duplicates across datasets
✅ Date parsing completed

2. Key Insights
Correlation Matrix Highlights


🔥 PRICE ↔ SELL_ID: -0.76 (negative)
✅ YEAR ↔ TEMPERATURE: +0.08 (seasonal)
⚠️  YEAR ↔ WEEKEND: ~0 (independent)
Price Elasticity


Elastic Demand: 2.19
1% ↑ Price → 2.19% ↓ Quantity
DBSCAN Clustering

Clusters: 40
Noise: 4020 (37%)
Largest: Cluster 3 (900 records)
Association Rules (Lift > 1)


Weekend → School Break (Lift=1.05)
School Break → Weekend (Lift=1.05)
Sequential Patterns


1253 frequent sequences (support ≥ 2)
Top: [New Year, BURGER], [11.26, COFFEE]
3. Predictive Modeling
Demand Forecasting (OLS)


R²: 0.72 (Full Model) / 0.72 (Reduced)
Key Predictors (p<0.05):
- PRICE_T: -0.287 (β)
- IS_WEEKEND: -1.602 (β) 
- IS_OUTDOOR: -0.964 (β)
Sell Category Classification


Logistic Regression: 87.45% Accuracy
Confusion Matrix visualized

📈 Visualizations


1. Correlation Heatmap (coolwarm)
2. Violin Plots (Price/Quantity by SELL_ID)
3. Bubble Chart (Price vs Quantity)
4. Box-Cox Transformation (outlier removal)
5. OLS Partial Regression Plots
6. Sigmoid Curve (Logistic)
7. Confusion Matrix Heatmap
8. 
🔬 Transformations Applied


1. Box-Cox: QUANTITY, PRICE, TEMPERATURE
2. Z-Score: Numerical scaling
3. One-Hot: HOLIDAY, categorical vars
4. Label Encoding: YEAR, ITEM_NAME
5. 
 Key Results Summary

Metric                  Value            Interpretation

R² (Demand Model)       0.72             Strong fit

Price Elasticity        2.19             Elastic

Classification Acc.     87.45%           Excellent

Clusters Found          40               High granularity

Rules (Lift>1)          5+               Actionable insights

Business Insights


Weekdays > Weekends (β=-1.60)
Indoor > Outdoor sales (β=-0.96)
New Year effect (β=-1.71)
Price sensitive customers
Optimize 1070 (BURGER) separately

Sample Outputs

Price Elasticity: 2.1856
DBSCAN Clusters: 40
Logistic Accuracy: 87.45%
OLS R²: 0.720

Customization

# DBSCAN parameters
eps = 0.5
min_samples = 50

# Apriori parameters  
min_support = 0.01
min_lift = 1.0

# Box-Cox lambda (auto-fitted)
📁 File Structure


├── DateInfo.csv              # Calendar data
├── Cafe-Transaction-Store.csv # Sales transactions
├── Cafe-Sell-Meta-Data.csv   # Item metadata
├── cafe_analytics.ipynb      # Main analysis
└── README.md                # This file

👩‍💻 Author

Nourhan Mohammed
Computer Science Student | Data Enthusiast

