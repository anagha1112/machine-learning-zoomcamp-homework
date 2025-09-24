# Car Fuel Efficiency Data Analysis

This project involves an exploratory data analysis of the Car Fuel Efficiency dataset. We use Python libraries like Pandas and NumPy to inspect the data, handle missing values, and perform matrix calculations to answer specific questions about the dataset's properties.

---

## Environment Setup

To run the analysis, you need a Python environment with the following libraries installed:
* NumPy
* Pandas
* Matplotlib
* Seaborn

The data for this project was downloaded using `wget`:
```bash
wget [https://raw.githubusercontent.com/alexeygrigorev/datasets/master/car_fuel_efficiency.csv](https://raw.githubusercontent.com/alexeygrigorev/datasets/master/car_fuel_efficiency.csv)

## Questions and Answers

Here are the solutions to the questions based on the analysis performed in the notebook.

### Q1. What's the version of Pandas that you installed?

The version of Pandas used in this analysis is 2.3.2.

```python
import pandas as pd
pd.__version__
# Output: '2.3.2'

```
### Q2. How many records are in the dataset?

The dataset contains 9704 records.

```python

df.shape[0]
# Output: 9704

```

### Q3. How many fuel types are presented in the dataset?

There are 2 unique fuel types in the dataset.

```python
df["fuel_type"].nunique()
# Output: 2

```
### Q4. How many columns in the dataset have missing values?

There are 4 columns with missing values. These are num_cylinders, horsepower, acceleration, and num_doors.

```python
df.isnull().sum()

```

### Q5. What's the maximum fuel efficiency of cars from Asia?

The maximum fuel efficiency for cars originating from Asia is approximately 23.76 mpg.

```python
asia_df = df[df["origin"]=="Asia"]
asia_df["fuel_efficiency_mpg"].max()
# Output: 23.759122836520497

```

### Q6. Has the median value of horsepower changed after filling missing values?

Yes, the median value of the horsepower column changed after filling the missing values.

Initial Median: 149.0

Fill Missing Values: The missing values were filled with the most frequent horsepower value, which was 152.0.

New Median: 152.0

The median value increased.

Correct Answer: Yes, it increased

### Q7. What's the sum of all the elements of the result w?

After performing the specified matrix operations (linear regression), the sum of all elements in the resulting vector w is approximately 0.5188.

```python
# X = First 7 'vehicle_weight' and 'model_year' values for cars from Asia
# y = np.array([1100, 1300, 800, 900, 1000, 1100, 1200])
XTX = X.T @ X
XTX_inv = np.linalg.inv(XTX)
w = XTX_inv @ X.T @ y
np.sum(w)
# Output: 0.5187709081074007

```