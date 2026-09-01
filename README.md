# Student Performance Prediction using Multiple Linear Regression

## 📌 Project Overview

This project uses **Multiple Linear Regression** to predict a student's **Performance Index** based on study habits, previous academic performance, extracurricular participation, sleep, and practice-question activity.

The project was completed using Python, Pandas, NumPy, and Scikit-learn.

## 🎯 Objective

The main objective is to build a regression model that can estimate a student's Performance Index from multiple input features.

## 📊 Dataset

The dataset contains the following variables:

| Feature | Description |
|---|---|
| Hours Studied | Number of hours spent studying |
| Previous Scores | Student's previous academic score |
| Extracurricular Activities | Whether the student participates in extracurricular activities |
| Sleep Hours | Number of hours of sleep |
| Sample Question Papers Practiced | Number of sample question papers practiced |
| Performance Index | Target variable representing student performance |

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Jupyter Notebook

## 🔍 Project Workflow

1. Import required Python libraries
2. Load the `Student_Performance.csv` dataset
3. Perform initial data exploration using `head()`
4. Check missing values using `isna().sum()`
5. Check data types using `dtypes`
6. Convert the target `Performance Index` to integer
7. Separate features (`X`) and target (`y`)
8. Encode the categorical `Extracurricular Activities` column using `pd.get_dummies()`
9. Split the dataset into training and testing sets using an 80/20 split
10. Train a `LinearRegression` model
11. Generate predictions on the test data
12. Compare actual and predicted Performance Index values
13. Evaluate the model using MSE, MAE, RMSE, and R² Score

## 🤖 Machine Learning Model

### Multiple Linear Regression

The project uses:

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()
model.fit(x_train, y_train)
```

Multiple Linear Regression is suitable here because the target variable, **Performance Index**, is continuous and the prediction uses multiple independent variables.

## 🔄 Categorical Data Encoding

The `Extracurricular Activities` column contains categorical values such as `Yes` and `No`.

It was converted into a numerical representation using:

```python
x = pd.get_dummies(
    x,
    columns=["Extracurricular Activities"],
    drop_first=True
)
```

## 📈 Model Evaluation

The model was evaluated using four regression metrics:

| Metric | Result |
|---|---:|
| MSE | 4.1024 |
| MAE | 1.6141 |
| RMSE | 2.0254 |
| R² Score | 0.9887 |

### Interpretation

- **MAE = 1.6141**: On average, the model's prediction differs from the actual Performance Index by approximately 1.61 points.
- **RMSE = 2.0254**: The typical prediction error, with larger errors receiving more weight, is approximately 2.03 points.
- **R² = 0.9887**: The model explains approximately 98.87% of the variation in the Performance Index on the test data.

These results indicate that the model performed very well on the available test set.

## 📋 Prediction Example

The notebook creates a comparison between actual and predicted values:

```python
comparison = pd.DataFrame({
    "Actual Performance Index": y_test,
    "Predicted Performance Index": y_pred
})
```

Example predictions from the notebook include:

| Actual | Predicted |
|---:|---:|
| 72 | 71.3793 |
| 34 | 34.5928 |
| 42 | 43.3039 |
| 56 | 58.1229 |
| 46 | 46.6699 |

## 📁 Project Structure

```text
student-performance-multiple-linear-regression/
│
├── Student Performance Prediction Report.ipynb
├── Student_Performance.csv
└── README.md
```

> Keep the CSV file in the same directory as the notebook if you want to run the notebook without changing the file path.

## 💡 Key Takeaways

- Multiple student-related factors can be used to predict the Performance Index.
- Categorical variables need to be encoded before being passed to a scikit-learn regression model.
- The model achieved a high R² score of **0.9887** on the test set.
- MAE and RMSE provide an intuitive view of prediction error in Performance Index points.
- Model performance should be validated on appropriate unseen data before being used for real-world decision-making.

## 🚀 How to Run

1. Clone or download this repository.
2. Make sure Python and Jupyter Notebook are installed.
3. Install the required libraries:

```bash
pip install pandas numpy scikit-learn jupyter
```

4. Keep `Student_Performance.csv` in the project directory.
5. Open the notebook:

```bash
jupyter notebook
```

6. Run the notebook cells from top to bottom.

## 👤 Author

**Mohit Batheja**

---

