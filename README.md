# Linear Regression From Scratch: Optimization Analysis and Model Benchmarking

## 1. Introduction

Linear Regression is one of the most fundamental algorithms in machine learning, used to model the relationship between a dependent variable and one or more independent variables. This project focuses on implementing Linear Regression from scratch using gradient descent and analyzing its behavior through multiple experiments.

In addition to the scratch implementation, the model is compared with scikit-learn’s implementation and other advanced regression models such as Random Forest and XGBoost. The project further explores optimization techniques, convergence behavior, learning rate sensitivity, and the effect of feature scaling.

---

## 2. Objectives

* Implement Linear Regression from scratch using gradient descent
* Compare performance with scikit-learn’s implementation
* Analyze convergence behavior using loss curves
* Study the effect of different learning rates
* Evaluate the impact of feature scaling
* Compare Gradient Descent with the Normal Equation
* Benchmark against Random Forest and XGBoost models

---

## 3. Dataset

The dataset used is a Salary vs Experience dataset, where:

* Input Feature: Years of Experience
* Target Variable: Salary

The dataset is small and exhibits a near-linear relationship, making it suitable for analyzing optimization behavior and model performance.

---

## 4. Methodology

### 4.1 Linear Regression from Scratch

Linear Regression was implemented using gradient descent. The model iteratively updates parameters to minimize the loss function.

Prediction function:

ŷ = Xw + b

Loss function (Mean Squared Error):

L = (1/n) Σ (y − ŷ)²

Parameter updates:

* w = w − α ∂L/∂w
* b = b − α ∂L/∂b

where:

* α is the learning rate
* L is the loss function (MSE)

Implementation Details:

The model was trained using a learning rate of 0.02 and 1000 iterations, which provided stable and efficient convergence for the given dataset.

Performance (Unscaled Data):

* MAE: 6675.84
* MSE: 60,483,757
* R²: 0.9041

These results indicate that the model achieves a strong fit, explaining approximately 90.4% of the variance in the target variable.

Convergence Graph of model with a learning rate of 0.02:
<img width="804" height="566" alt="image" src="https://github.com/user-attachments/assets/59d07ae8-9660-45d4-9514-7d39bd5bb68d" />


---

### 4.2 Convergence Analysis

The loss was recorded at each iteration and plotted against the number of iterations.

**Observation:**

* Rapid decrease in loss during initial iterations
* Gradual flattening as the model approaches the minimum

This confirms correct and stable convergence of gradient descent.

---

### 4.3 Learning Rate Experiments

Different learning rates were tested:

| Learning Rate | Behavior | Convergence Speed | Final Performance |
| ------------- | -------- | ----------------- | ----------------- |
| 0.001         | Slow     | Slow              | Good but slow     |
| 0.005         | Stable   | Moderate          | Good              |
| 0.01          | Optimal  | Fast              | Good              |
| 0.02          | Stable   | Fast              | Selected Model    |


**Observation:**
* Learning rates in the range 0.01–0.02 provided the best balance between speed and stability
* Very small learning rates (0.001) resulted in slow convergence
* Slightly higher learning rates (0.02) maintained stability while improving convergence speed

 Graph displaying the rate of convergence:
<img width="761" height="565" alt="image" src="https://github.com/user-attachments/assets/d1b69b62-edc0-4f29-994d-76cfc58ce6dd" />


---

### 4.4 Effect of Feature Scaling

Feature scaling was applied using standardization, and experiments were conducted on both scaled and unscaled data.

**Observations:**

* Both scaled and unscaled models achieved **similar evaluation metrics (MSE, MAE, R²)** when predictions were converted back to the original scale
* The scaled version showed **smoother and more stable convergence behavior**
* Training with scaled data was **more numerically stable and slightly faster in convergence**
* The impact of scaling was limited due to the simplicity of the dataset

**Conclusion:**

Feature scaling primarily improves the **optimization process rather than final model accuracy**. Its importance increases for complex datasets with multiple features and varying scales.

---

### 4.5 Normal Equation

The Normal Equation provides a closed-form solution:

θ = (XᵀX)⁻¹Xᵀy

**Comparison:**

| Method           | MSE         | Time (s) |
| ---------------- | ----------- | -------- |
| Gradient Descent |~ 60,451,409 | 0.034    |
| Normal Equation  |~ 60,451,409 | 0.00013  |

**Observation:**

* Both methods achieve nearly identical accuracy
* The Normal Equation is significantly faster for small datasets
* It becomes computationally expensive for large datasets

---

### 4.6 Model Comparison

The following models were compared:

* Linear Regression (Scratch)
* Linear Regression (Scikit-learn)
* Random Forest
* XGBoost

| Model                     | MAE     | MSE        | R²     |
| ------------------------- | ------- | ---------- | ------ |
| Scratch Linear Regression | 6675.84 | 60,483,757 | 0.9041 |
| Scikit-learn Regression   | 6673.57 | 60,451,409 | 0.9042 |
| Random Forest             | 4581.09 | 28014613.46| 0.9620 |
| XGBoost                   | 6670.46 | 66664204.0 | 0.9097 |

**Observation:**

* Scratch implementation closely matches scikit-learn performance
* Tree-based models capture non-linear relationships more effectively
* Linear Regression performs well due to the linear nature of the dataset

---

### 4.7 Justification for Using Unscaled Data in Model Comparison

The comparison between Linear Regression, Random Forest, and XGBoost was performed using the **unscaled dataset**.

This is because:

* Tree-based models such as Random Forest and XGBoost are **not sensitive to feature scaling**
* Using unscaled data ensures a **fair and consistent comparison across all models**
* The dataset is simple and does not require scaling for effective performance

This demonstrates an understanding of when preprocessing techniques such as feature scaling are necessary, rather than applying them indiscriminately.

---

## 5. Results and Discussion

* Gradient descent converges efficiently to the optimal solution
* Learning rate significantly affects convergence speed and stability
* Feature scaling improves numerical stability but does not significantly impact accuracy for simple datasets
* The Normal Equation provides a fast alternative for small datasets
* Scratch implementation validates correctness by matching scikit-learn results

---

## 6. Conclusion

This project demonstrates a comprehensive understanding of Linear Regression, including implementation, optimization, and evaluation. The experiments highlight the importance of convergence analysis, learning rate tuning, and preprocessing techniques.

While Gradient Descent is scalable and flexible, the Normal Equation provides a faster alternative for smaller datasets. Model comparisons further illustrate the strengths and limitations of linear and tree-based approaches.

---

## 7. Future Work

* Apply the model to larger and more complex datasets
* Explore regularization techniques (Ridge, Lasso)
* Perform hyperparameter tuning for tree-based models
* Extend to multivariate regression problems

---
