# A-B-Testing-case-Study
A/B Testing case study on Advertisements Conversion Rate

# Marketing A/B Testing Dataset

## 📌 About the Dataset
Marketing companies aim to run **successful advertising campaigns**, but the market is complex, with multiple factors influencing campaign effectiveness. To optimize decision-making, companies conduct **A/B tests**, a randomized experimentation process where different versions of a variable (e.g., web pages, banners, ad placements) are tested against each other to identify which yields the best results.

### 🎯 Objectives
This dataset helps answer two critical business questions:
1. **Would the campaign be successful?**
2. **If the campaign was successful, how much of that success could be attributed to the ads?**

To evaluate this, a control group is shown **Public Service Announcements (PSA)** instead of advertisements, and their engagement is compared against the experimental group exposed to ads.

## 📊 Data Description
This dataset consists of various features that help analyze the performance of the A/B test.

### 🔹 **Data Dictionary**
| Column Name   | Description  |
|--------------|-------------|
| `Index`       | Row index |
| `user_id`     | Unique identifier for each user |
| `test_group`  | Group classification (`ad`: saw the advertisement, `psa`: saw the PSA) |
| `converted`   | Conversion status (`True`: user made a purchase, `False`: no purchase) |
| `total_ads`   | Total number of ads seen by the user |
| `most_ads_day`| Day of the week when the user saw the most ads |
| `most_ads_hour` | Hour of the day when the user saw the most ads |

## 🧪 A/B Testing Process
- Users were randomly assigned to one of two groups:
  - **Ad Group (Experimental):** Users exposed to advertisements.
  - **PSA Group (Control):** Users who saw Public Service Announcements instead of ads.
- By comparing conversion rates across both groups, we determine the **effectiveness of the ads** and analyze whether the difference is statistically significant.

## 📊 Analysis Plan
To evaluate the impact of ads, we follow this structured analysis plan:

1. **Exploratory Data Analysis (EDA):**
   - Check for missing values and duplicates.
   - Visualize data distributions (e.g., conversion rates, ad exposure trends).
   - Identify engagement trends across different days and hours.

2. **Statistical Hypothesis Testing:**
   - **Chi-Square Test:** Determine if there is a significant association between test groups and conversion rates.
   - **Shapiro-Wilk Test:** Check if `total_ads` follows a normal distribution.
   - **Levene’s Test:** Verify the equality of variances in `total_ads` across groups.
   - **Mann-Whitney U-Test:** Compare `total_ads` between converted and non-converted users.

3. **Results Interpretation:**
   - Identify whether ads significantly impact conversions.
   - Analyze which days and hours lead to the highest engagement.
   - Provide actionable insights for optimizing future marketing campaigns.

## 📈 Potential Use Cases
This dataset is ideal for:
✅ **A/B Testing Analysis** – Understanding how ads impact user behavior.
✅ **Marketing Analytics** – Evaluating the effectiveness of digital marketing strategies.
✅ **Statistical Hypothesis Testing** – Running significance tests (e.g., Chi-Square, Mann-Whitney U) to determine if ads lead to higher conversions.
✅ **Machine Learning Applications** – Predicting conversion rates based on ad exposure patterns.

## 🔗 How to Use the Dataset
- Load the dataset using `pandas`:
  ```python
  import pandas as pd
  df = pd.read_csv('marketing_AB.csv')
  df.head()
  ```
- Perform **Exploratory Data Analysis (EDA)**:
  ```python
  import matplotlib.pyplot as plt
  import seaborn as sns
  sns.countplot(x='test_group', hue='converted', data=df)
  plt.show()
  ```
- Conduct **Statistical Analysis** to check for significance:
  ```python
  from scipy.stats import chi2_contingency
  contingency_table = pd.crosstab(df['test_group'], df['converted'])
  chi2, p, _, _ = chi2_contingency(contingency_table)
  print(f'Chi-Square Test p-value: {p}')
  ```

## 🏆 Key Insights
- This dataset provides insights into **customer behavior, ad performance, and statistical significance of marketing strategies**.
- It allows businesses to make **data-driven decisions** to optimize advertising spend and maximize conversions.

---
📢 **If you find this dataset useful, feel free to use it for your analysis and share your insights!** 🚀
