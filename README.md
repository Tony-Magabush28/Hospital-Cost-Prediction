## 🏥 Hospital Cost Analysis using Machine Learning

This project utilizes machine learning techniques and statistical analysis to analyze hospital costs based on various patient-related and hospital-specific features. It demonstrates the use of regression models, data preprocessing, and visualization techniques for predictive modeling.

---

 📌 **Project Goals**
- Predict hospital costs using patient information.
- Explore relationships between **Age**, **Length of Stay**, **Satisfaction**, and **Cost**.
- Compare regression models for performance.
- Visualize insights from the dataset.

---

## 📂 **Dataset Description**
The dataset contains patient information with the following features:
- **Age:** Age of the patient.
- **Length_of_Stay:** Duration of stay in the hospital (in days).
- **Satisfaction:** Patient satisfaction rating (scale).
- **Cost:** Hospital cost for the patient (target variable).

---

## 🛠️ **Libraries Used**
- **NumPy**
- **Pandas**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**

---

## 🔄 **Model Pipeline**
1. **Data Loading & Exploration:** Read the CSV dataset and check for missing values.
2. **Descriptive Statistics:** Calculate Mean, Median, Mode, Variance, Standard Deviation, and Percentiles of hospital costs.
3. **Data Visualization:**
   - Histogram of hospital costs.
   - Correlation heatmap to observe feature relationships.
4. **Regression Models:**
   - **Simple Linear Regression:** Predicting Cost based on Length of Stay.
   - **Polynomial Regression (Degree 3):** Capturing non-linear patterns between Length of Stay and Cost.
   - **Multiple Linear Regression:** Using Age, Length of Stay, and Satisfaction together to predict Cost.
5. **Feature Scaling:** Standardize the Length of Stay feature.
6. **Model Evaluation:** Evaluate models using **R² Score**, **MAE**, **MSE**, and **RMSE**.
7. **Residual Analysis:** Visualize model residuals to check for errors and biases.

---

## 📊 **Visualizations**
### Histogram of Hospital Costs
![Histogram of Hospital Costs](plots/hhc.png)

### Correlation Heatmap
![Correlation Heatmap](plots/ch.png)

### Regression Models
#### Linear Regression (Length of Stay vs Cost)
![Linear Regression Plot](plots/lr.png)

#### Polynomial Regression (Degree 3)
![Polynomial Regression Plot](plots/pr.png)

### Residual Plots
#### Linear Regression Residuals
![Residuals - Linear Regression](plots/rlr.png)

#### Polynomial Regression Residuals
![Residuals - Polynomial Regression](plots/rpr.png)

#### Multiple Regression Residuals
![Residuals - Multiple Regression](plots/rmr.png)

---

## 📈 **Results Table **
## 📊 Descriptive Statistical Analysis

### ✅ Central Tendency Measures (Hospital Cost)
| Metric       | Value (₵) |
|--------------|-----------|
| **Mean**     | 8,367.48  |
| **Median**   | 6,000.00  |
| **Mode**     | 3,000.00  |

**Insight:**  
- The **mean cost** (₵8,367.48) is **higher than the median** (₵6,000), suggesting a **right-skewed distribution** where some high-cost patients are pulling the average up.
- The **mode** is ₵3,000, indicating that the most frequent hospital cost is relatively low compared to the average.

---

### ✅ Spread & Variability (Hospital Cost)
| Metric                | Value (₵) |
|-----------------------|-----------|
| **Variance**          | 60,248,503.92 |
| **Standard Deviation**| 7,761.99  |

**Insight:**  
- The **standard deviation** is quite large, meaning hospital costs vary significantly from patient to patient.
- A high variance indicates a wide range of hospital bills, confirming the skewed nature of the data.

---

### ✅ Percentile Distribution
| Percentile | Cost (₵) |
|------------|----------|
| **10th**   | 500      |
| **30th**   | 2,000    |
| **50th** *(Median)* | 6,000 |
| **70th**   | 12,000   |
| **90th**   | 20,000   |

**Insight:**  
- **50% of patients** pay **₵6,000 or less** for hospital care.
- However, **10% of patients** pay **₵20,000 or more**, highlighting a significant difference between typical and high-end costs.
- This reinforces the **right-skewed distribution** observed earlier.

---

### ✅ Key Takeaway:
> The hospital cost dataset is highly skewed, with extremely high-cost cases driving up the mean.  
The majority of patients pay modest amounts, but a small group incurs very high expenses, indicating potential outliers or critical cases needing special attention.

---

✅ Summary:
Overall, the dataset exhibits high variability and right-skewness, meaning that while most patients incur moderate costs, a few high-cost cases significantly affect the overall average. These insights were critical in guiding model selection and evaluation for the cost prediction task.

---

## 📈 Linear Regression Evaluation (Cost vs Length of Stay)

| Metric          | Value      |
|-----------------|------------|
| **R² Score**    | 0.013      |
| **MAE**         | ₵6,545.85  |
| **MSE**         | 58,027,386.04 |
| **RMSE**        | ₵7,617.57  |
| **Intercept**   | ₵6,954.86  |
| **Slope**       | 41.81      |

### ✅ Interpretation:
- The **R² score** of 0.013 indicates that the model explains only about **1.3%** of the variance in hospital costs based on Length of Stay alone. This suggests a **weak linear relationship** between the two variables.
- The **Mean Absolute Error (MAE)** of ₵6,545.85 means that on average, the model's predictions deviate from the actual costs by about ₵6,546.
- **Root Mean Squared Error (RMSE)** is also quite high, showing that prediction errors can be significant in magnitude.
- The **positive slope (41.81)** indicates that as Length of Stay increases by one unit, the hospital cost tends to increase by around ₵41.81, but the effect size is relatively small.

### ✅ Key Insight:
Although longer hospital stays tend to increase costs, the relationship here is **weak and possibly non-linear or influenced by other factors** (e.g., treatment type, severity, insurance coverage). This finding justifies trying **more complex models** (such as Polynomial Regression or Multiple Regression).

---

## 🔗 Correlation Analysis (Length of Stay vs Cost)
- **Correlation Coefficient (r):** **0.1142**

### ✅ Insight:
There is a **weak positive correlation** between Length of Stay and Hospital Cost.  
This suggests that while longer stays generally increase costs, the relationship is **not strong**, implying that **other variables** (like type of treatment or patient condition) may also be significant contributors to cost.

---

## 📈 Polynomial Regression (Degree 3) Evaluation

| Metric          | Value     |
|-----------------|-----------|
| **R² Score**    | 0.032     |
| **MAE**         | ₵6,430.64 |
| **MSE**         | 56,965,152.10 |
| **RMSE**        | ₵7,547.53 |
| **Intercept**   | ₵2,706.43 |
| **Coefficients**| [0, 653.23, -20.67, 0.19] |

### ✅ Interpretation:
- The **R² score** of **0.032** shows a slight improvement over the simple linear regression, explaining about **3.2%** of the cost variance.
- The **MAE** and **RMSE** are slightly lower than those from the linear model, indicating marginally better predictive accuracy.
- The coefficients suggest a **non-linear relationship** between Length of Stay and Cost:
  - The linear term has a large positive coefficient (₵653.23).
  - The negative quadratic term (-20.67) and positive cubic term (0.19) show that the relationship bends as the Length of Stay increases.

### ✅ Key Insight:
While polynomial regression (degree 3) slightly improves predictions over simple linear regression, the overall explanatory power remains weak. This suggests that **Length of Stay alone is insufficient to accurately predict hospital costs**, and additional features should be explored.

---

## ⚙️ Feature Scaling
I applied **standardization** on the `Length_of_Stay` feature using **StandardScaler** to normalize its scale:

| Sample Scaled Values (Length of Stay) |
|--------------------------------------|
| -1.67, -1.77, -1.87, -1.57, -1.41 |

### ✅ Insight:
- The scaled values now have a **mean of 0** and **unit variance**.
- Feature scaling is essential before applying certain algorithms or combining features with different scales in regression models.
- Though scaling doesn’t affect the performance of **Linear Regression**, it ensures consistency, especially when extending models later.

---

## 📊 Multiple Linear Regression (with Age, Length of Stay, Satisfaction)

| Metric          | Value     |
|-----------------|-----------|
| **R² Score**    | 0.235     |
| **MAE**         | ₵5,514.30 |
| **MSE**         | 45,014,485.66 |
| **RMSE**        | ₵6,709.28 |
| **Intercept**   | ₵27,543.76 |
| **Coefficients**| {'Age': -42.83, 'Length_of_Stay': 564.10, 'Satisfaction': -4,637.46} |

### ✅ Interpretation:
- **R² Score** of **0.235** shows a clear improvement over both linear and polynomial models — about **23.5%** of the variance in hospital costs is explained by this model.
- **MAE** and **RMSE** are also lower than previous models, indicating improved prediction accuracy.
- **Coefficients Interpretation:**
  - **Age:** A very slight negative impact on cost (-₵42.83 per year); not highly impactful here.
  - **Length of Stay:** Strong positive impact; each additional day in hospital adds about **₵564.10** to the predicted cost.
  - **Satisfaction:** Strong negative impact; higher satisfaction correlates with **lower hospital costs** (₵4,637.46 decrease per satisfaction unit — possibly indicating healthier, faster recoveries or lower resource use among satisfied patients).

### ✅ Key Insight:
This model performs significantly better, indicating that **hospital costs depend on multiple factors** rather than just Length of Stay alone. It highlights the importance of incorporating **multiple features** in predictive models for more realistic results.

---

## 📊 Model Comparison Summary

| Model             | R² Score | MAE          | RMSE        |
|------------------|----------|--------------|-------------|
| **Linear**       | 0.013    | ₵6,545.85    | ₵7,617.57   |
| **Polynomial (3)**| 0.032    | ₵6,430.64    | ₵7,547.53   |
| **Multiple**     | 0.235    | ₵5,514.30    | ₵6,709.28   |

---

### ✅ Insight:
1. **Linear Regression**:
   - Very low predictive power (**R² = 0.013**) with high prediction errors (MAE & RMSE).
   - Indicates that **Length of Stay alone** is not sufficient to predict hospital cost effectively.

2. **Polynomial Regression (Degree 3)**:
   - Slightly better than linear regression (**R² = 0.032**) with small improvements in MAE and RMSE.
   - Captures minor non-linear patterns, but is still poor at explaining the variance.

3. **Multiple Regression**:
   - **Best-performing model** among the three with **R² = 0.235**, explaining about **23.5%** of the variance in hospital costs.
   - Shows lower errors, confirming that **multiple features** (Age, Length of Stay, Satisfaction) improve predictions.

---

### ✅ Key Takeaway:
> The analysis shows that **including multiple variables** provides significantly better cost predictions than models based on a single feature like Length of Stay.  
However, even the best model explains only around **23.5%** of the cost variance, suggesting that additional factors may be influencing hospital costs (e.g., diagnosis type, insurance, treatments).

---

## 💼 **Author**
**Anthony Sergo**

- GitHub: https://github.com/Tony-Magabush28
- LinkedIn: www.linkedin.com/in/anthony-sergo1 
- Email: anthonysergo9@gmail.com
- Portfolio: https://my-flask-portfolio.onrender.com/


🔗 [Connect with me on LinkedIn](https://www.linkedin.com/in/anthony-sergo1)  
💬 Feel free to explore, star ⭐, or fork 🍴 this repository!

---

## 🚀 **How to Run This Project**
```bash
1. Clone this repo
2. Install dependencies: pip install -r requirements.txt
3. Run the notebook or script
# Hospital-Cost-Prediction
