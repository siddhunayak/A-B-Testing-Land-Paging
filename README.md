

# A/B Testing for Landing Page Conversion

This project analyzes the results of an A/B test to determine if a new landing page design leads to a higher conversion rate compared to the old design.

---

## 📜 Dataset

The dataset used for this analysis is `ab_data.csv`, which contains the following columns:

* **user_id**: A unique identifier for each user.
* **timestamp**: The time at which the user session occurred.
* **group**: The group the user was assigned to ('control' or 'treatment').
* **landing_page**: The version of the landing page the user saw ('old_page' or 'new_page').
* **converted**: A binary indicator (1 for converted, 0 for not converted).

The experiment ran for approximately 22 days, from January 2nd, 2017, to January 24th, 2017.

---

## 🔬 Methodology

The analysis follows these key steps:

### 1. Data Exploration & Cleaning

* The notebook begins by loading the dataset and performing an initial exploration to understand its structure.
* It checks for any missing or duplicate values to ensure data quality.
* The `timestamp` column is converted to a datetime object for time-series analysis.
* It was noted that some users in the 'control' group were shown the 'new_page' and vice versa. These misaligned entries are kept in the dataset for the initial analysis.

### 2. Exploratory Data Analysis (EDA)

* **Daily Active Users**: The number of users in both the control and treatment groups were plotted over time to check for any significant variations or imbalances during the experiment's duration.
* **Daily Conversions**: The number of conversions for both groups was also plotted daily to observe trends.

### 3. Hypothesis Testing

The core of the analysis is a hypothesis test to compare the conversion rates of the two landing pages.

* **Null Hypothesis ($H_0$)**: There is **no difference** in the conversion rate between the old page (control) and the new page (treatment).
* **Alternative Hypothesis ($H_1$)**: There **is a difference** in the conversion rate between the old and new pages.

A **Z-test for proportions** was used to determine the statistical significance of the observed difference in conversion rates.

---

## 📊 Results

The analysis yielded the following key results:

* **Control Group (Old Page) Conversion Rate**: Approximately **12.04%**.
* **Treatment Group (New Page) Conversion Rate**: Approximately **11.89%**.

The Z-test resulted in a **p-value of 0.2161**.


---

## 🏁 Conclusion

Since the p-value (0.2161) is greater than the standard alpha level of 0.05, we **fail to reject the null hypothesis**.

This means there is **no statistically significant difference** in the conversion rates between the old and new landing pages. The new design did not perform better than the existing one. Therefore, the company can choose to either continue using the old page or implement the new page, as neither has a clear advantage in driving conversions.


