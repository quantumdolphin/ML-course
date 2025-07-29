### Example: Visualizing Missing Values with `missingno`

You can easily create all three types of plots using the following code:

```python
import missingno as msno
import matplotlib.pyplot as plt

# Visualize missing values as a bar chart
msno.bar(df)
plt.show()

# Visualize missing values as a matrix (more granular)
msno.matrix(df)
plt.show()

# Visualize a heatmap (shows correlation of missingness between columns)
msno.heatmap(df)
plt.show()
