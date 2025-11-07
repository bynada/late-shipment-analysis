# Late Shipment Analysis

This project analyzes shipping data to identify key factors contributing to late deliveries and builds a predictive model to estimate late shipment risk.  
The goal is to help improve delivery performance, customer satisfaction, and operational efficiency using data-driven insights.

---

## Dataset Overview
- **Source:** [Kaggle]([https://public.tableau.com/app/profile/nada.farhani/viz/LateShipmentAnalysis_17579374188130/Dashboard1?publish=yes](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis/data))

- **Total Records:** ~180,000+  
- **Target Variable:** `is_late` (1 = Late delivery, 0 = On time)  
- **Main Features:**
  - Days for shipment (scheduled)
  - Days for shipping (real)
  - Shipping Mode
  - Order Item Quantity
  - Order Profit per Order
  - Sales per Customer
  - Order to Shipment Time (engineered feature)

---

## Data Cleaning & Preparation
- Converted date columns to `datetime` objects  
- Filled missing customer information using mode and placeholders  
- Removed irrelevant columns (`Product Description`, `Order Zipcode`)  
- Created new features:
  - `shipping_delay` = actual – scheduled shipping days  
  - `is_late` = binary target variable  
  - `Order_to_Shipment_Time` = hours between order and shipping

---

## Exploratory Data Analysis (EDA)
- Visualized **shipment delays** by category, customer segment, and shipping mode  
- Found that **57%** of all shipments were late  
- Identified **Standard Class** shipments as the most common and frequently delayed category  
- Observed longer order-to-ship durations correlated with higher delay risk

---

## Predictive Modeling
- Model used: **Logistic Regression**  
- Input features scaled with **MinMaxScaler** and encoded with **OrdinalEncoder**  
- Achieved:
  - **Accuracy:** 97.2%  
  - **Precision:** 97%  
  - **Recall:** 98%  
  - **F1-score:** 98%

### Key Insights
- The most influential factors are:
  - **Order to Ship Time**
  - **Days for shipment (scheduled)**
  - **Shipping Mode**
- Logistic Regression achieved strong performance, suggesting the dataset is highly predictable with linear features.

---

## Next Steps
- Try **tree-based models** (Random Forest, XGBoost) to capture non-linear effects  
- Add features such as **region** and **order priority** for deeper business insights  
- Perform **cross-validation** and **feature importance analysis**  

---

## Interactive Dashboard

You can explore the **Late Shipment Analysis Dashboard** built in **Tableau** to visualize shipment performance, delivery trends, and late-shipment patterns interactively.

🔗 [View Dashboard on Tableau](https://public.tableau.com/app/profile/nada.farhani/viz/LateShipmentAnalysis_17579374188130/Dashboard1?publish=yes)

**Key Visuals:**
- Late shipment ratio
- Average delay by Status, shipping Mode and Product Category
- Regional shipment performance
- Quarterly trend of delay rates

---

## Tools & Libraries
- Python (Pandas, NumPy, Scikit-learn)
- Matplotlib, Seaborn, Plotly
- Google Colab, Tableau, GitHub

## 👩‍💻 Author
**Nada Farhani Rustiawan**  
[GitHub @bynada](https://github.com/bynada)  
