## Best Practices for Handling Missing Values and Outliers

### Handling Missing Values

- **Why fill missing values?**
  - Machine learning models require complete data—missing values must be addressed before modeling.

- **Common Strategies:**
  1. **Remove rows or columns with missing data:**
     - **Pros:** Simple, quick, and eliminates uncertainty.
     - **Cons:** Risk of losing too much information or introducing bias if missingness is systematic or widespread.
  2. **Impute (fill in) missing values:**
     - Replace missing values with a statistic (mean, median, mode) or a value estimated by another method.
     - **Pros:** Retains all rows and columns.
     - **Cons:** Introduces some uncertainty, as the imputed value is only an estimate.
  3. **Mask missing values as their own category:**
     - Create a new category to represent missingness, useful for categorical data.
     - **Pros:** Missingness can sometimes be informative (e.g., if skipped questions signal a particular behavior).
     - **Cons:** Assumes all missing values are similar and meaningful.

**Tip:**  
Decide the approach based on your dataset’s size, the importance of the missing data, and the context of the analysis.

---

### Handling Outliers

- **Outliers** are values that are very different from most observations.
- They can skew statistics and affect model predictions, but sometimes provide critical information about rare events or errors.

**How to detect outliers:**
- **Visual methods:**  
  - Histograms, boxplots, density plots
- **Statistical methods:**  
  - Use the Interquartile Range (IQR) to define bounds (see previous section)
  - Analyze residuals (differences between observed and predicted values)

**Best Practice:**  
- Always investigate outliers before removing them. Outliers can be errors, but they can also represent important real-world phenomena (e.g., rare spikes in sales or unusual patient responses).

---

**Summary Table:**

| Challenge         | Pros                           | Cons                        |
|-------------------|-------------------------------|-----------------------------|
| Remove rows/cols  | Simple, no guesswork           | Lose data, risk bias        |
| Impute values     | Keep data, simple to automate  | Adds uncertainty            |
| Mask missingness  | Can capture informative signal | Assumes missingness is info |
| Remove outliers   | Reduces distortion             | May lose important cases    |
| Investigate outliers | May reveal new patterns     | More work, needs context    |

**Bottom line:**  
There is no one-size-fits-all rule—choose your method based on the data and the business/scientific question!
