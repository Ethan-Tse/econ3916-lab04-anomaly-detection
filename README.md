# econ3916-lab04-robust-statistics
ECON3916 LAB 03 - Robust Statistics
# Robust Statistics -- Automated Anomaly Detection

## Objective
I compared how different summary statistics and outlier-detection methods handle extreme values in California housing prices.

## Methodology
- Loaded the California Housing data from scikit-learn (20,640 observations).
- Computed the mean, median, trimmed mean, standard deviation, IQR and MAD for house values and compared how each one responds to the long right tail.
- Wrote Tukey Fences by hand (Q1 and Q3 plus or minus 1.5 times the IQR) to flag price outliers, and drew the fences on a histogram and a boxplot.
- Fit an Isolation Forest on the eight feature columns to flag unusual rows based on all features together.
- Compared the rows flagged by Tukey Fences with the rows flagged by the Isolation Forest.
- Replaced 5% of the prices with extreme values to see which summary statistics changed.

## Key Findings
- The mean sits above the median because the price distribution is skewed to the right.
- Tukey Fences and the Isolation Forest flag different observations. Tukey looks only at price, while the forest looks at every feature at once.
- After I corrupted 5% of the prices, the mean shifted by 67.13%, while the median shifted by only 3.56%.
