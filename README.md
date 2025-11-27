# 📊 **A/B TESTING PROJECT — LANDING PAGE CONVERSION ANALYSIS**

## 📝 Overview
This project analyzes whether a **new landing page** improves user conversion compared to the **old page** using a full A/B testing workflow including:

* Data cleaning & preprocessing
* Merging datasets
* Exploratory Data Analysis (EDA)
* Statistical Hypothesis Testing (Z-Test)
* Insights & recommendations

## 🎯 Business Problem
The company wants to increase user conversions by launching a **new landing page**.
Management wants to know:

> **Does the new landing page convert users better than the old page?**

## 🎯 Objective
* Compare conversion rates between **control (old_page)** and **treatment (new_page)**.
* Validate results with statistical testing (One-Tailed Z-Test).
* Provide a **data-driven recommendation** on adopting the new page.

## 📂 Dataset Description
### **📌 1. A/B TESTING DATASET (`ab_data.csv`)**

| Column           | Description                                  |
| ---------------- | -------------------------------------------- |
| **user_id**      | Unique identifier for each user              |
| **timestamp**    | Time of the page visit                       |
| **group**        | control / treatment                          |
| **landing_page** | old_page / new_page                          |
| **converted**    | 1 = user converted, 0 = user did not convert |

### **📌 2. COUNTRY DATASET (`countries.csv`)**
| Column      | Description                 |
| ----------- | --------------------------- |
| **user_id** | Same user_id as A/B dataset |
| **country** | Country the user belongs to |

## 🧹 Data Cleaning Pipeline
### ✔ Steps Performed
* Converted `timestamp` column into **datetime** format.
* Removed invalid combinations:
  * control → **new_page**
  * treatment → **old_page**
* Removed duplicates (if any).
* Checked missing values.
* Merged datasets on `user_id`.
* Final dataset size after cleaning: **294,479 rows**.

## 📊 Exploratory Data Analysis (EDA)
### Visuals Created:
* Conversion Rate Comparison Bar Chart
* Group-Wise Conversion Visualization
* Time-Series Conversion Trend
* Country vs Group Conversion Heatmap
* Distribution of Users Across Groups

## 📐 Hypothesis Testing — Z Test
### **Hypotheses**
#### **Null Hypothesis (H₀):**
Conversion_new ≤ Conversion_old
#### **Alternative Hypothesis (H₁):**
Conversion_new > Conversion_old

### **Test Used**
* **One-Tailed Z-Test** for proportions
* Significance Level: **α = 0.05**

### **Decision Rule**
* **If p-value < 0.05** → Reject H₀ → New page performs better
* **If p-value ≥ 0.05** → Fail to reject H₀ → No significant improvement

## 🧪 Statistical Results (Replace with your output)
| Metric                     | Value                                          |
| -------------------------- | -----------------------------------------------|
| Conversion Rate — Old Page | 0.1203863045004612                             |
| Conversion Rate — New Page | 0.11880724790277405                            |
| Z-Score                    | -1.3116075339133115                            |
| p-Value                    | 0.18965258971881804                            |
| Final Decision             | Fail to Reject the Null Hypothesis             |

## 📈 Visualizations Included
| Chart                        | Description                                           |
| ---------------------------- | ----------------------------------------------------- |
| Conversion Bar Chart         | Compare conversion values between control & treatment |
| Heatmap                      | Country-wise conversion → control vs treatment        |
| Time Trend Plot              | Conversion behavior over time                         |
| Group Distribution Chart     | User distribution across groups                       |
| Conversion Funnel (Optional) | View conversion drop-offs                             |

## 🛠 Tech Stack
| Tool / Library           | Purpose                      |
| ------------------------ | ---------------------------- |
| **Python**               | Primary analysis             |
| **Pandas**               | Data cleaning & manipulation |
| **NumPy**                | Numerical operations         |
| **Matplotlib / Seaborn** | Visualizations               |
| **Statsmodels / Scipy**  | Z-Test & statistics          |
| **Jupyter Notebook**     | Development environment      |

## 🏁 Conclusion
This project helps determine whether the new landing page should be launched based on **statistical evidence** rather than assumptions.
The Z-Test provides a clear, unbiased recommendation for business decision-making.
