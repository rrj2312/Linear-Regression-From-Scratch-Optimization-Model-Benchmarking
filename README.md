# Linear Regression From Scratch: Optimization & Model Benchmarking

## Overview

This project implements **Linear Regression from scratch using Gradient Descent** and performs a detailed analysis of optimization behavior and model performance.

It also compares:

* Scratch implementation vs **scikit-learn**
* Linear models vs **Random Forest** and **XGBoost**
* **Scaled vs unscaled data**
* **Gradient Descent vs Normal Equation**

---

## 🎯 Key Highlights

* 📉 Implemented Linear Regression from scratch
* 📊 Visualized convergence using loss curves
* ⚙️ Analyzed impact of learning rates
* 🔍 Compared scaled vs unscaled data
* ⚡ Benchmarked Gradient Descent vs Normal Equation
* 🌲 Compared with Random Forest and XGBoost

---

## 📂 Dataset

* **Feature:** Years of Experience
* **Target:** Salary

The dataset is small and nearly linear, making it ideal for studying optimization behavior.

---

## Methodology

### Linear Regression (From Scratch)

* Loss Function: **Mean Squared Error (MSE)**
* Optimization: **Gradient Descent**

Update rules:

```
w = w − α ∂L/∂w
b = b − α ∂L/∂b
```

* Learning Rate: **0.02**
* Iterations: **1000**

---

## Results (Unscaled Data)

Convergence Graph for the model with a learning rate of 0.02:
<img width="747" height="570" alt="image" src="https://github.com/user-attachments/assets/07ecebdc-9a7f-4ce2-b439-82b579d8eb78" />


| Metric | Value      |
| ------ | ---------- |
| MAE    | 6675.84    |
| MSE    | 60,483,757 |
| R²     | 0.9041     |

The model explains **~90.4% of the variance**, indicating a strong fit.

---

## Convergence Analysis

* Sharp loss decrease in early iterations
* Smooth flattening near convergence

✔ Confirms correct implementation of gradient descent

---

## Learning Rate Experiments

| Learning Rate | Behavior    | Speed    | Status     |
| ------------- | ----------- | -------- | ---------- |
| 0.001         | Very stable | Slow     | X         
| 0.005         | Stable      | Moderate | ✔         |
| 0.01          | Optimal     | Fast     | ✔         |
| 0.02          | Stable      | Fast     | Selected   |

**0.02 chosen** for best balance between speed and stability

Graph representing the rate of convergence for the learning rate 0.005, 0.001 and 0.01:
<img width="761" height="565" alt="image" src="https://github.com/user-attachments/assets/ca7b8bdf-f54e-4116-a83f-5df0fbacd43a" />


---

## Feature Scaling Analysis

* Scaled and unscaled models achieved **similar accuracy**
* Scaling improved:

  * convergence smoothness
  * numerical stability
* Impact was limited due to simple dataset

Scaling helps **optimization**, not final accuracy

---

## Normal Equation vs Gradient Descent

| Method           | MSE  | Time (s) |
| ---------------- | ---- | -------- |
| Gradient Descent | ~60M | 0.034    |
| Normal Equation  | ~60M | 0.00013  |

### Insight

* Same accuracy 
* Normal Equation is **much faster** (small data)
* Not scalable for large datasets

---

## Model Comparison

| Model                     | MAE     | MSE        | R²     |
| ------------------------- | ------- | ---------- | ------ |
| Scratch Linear Regression | 6675.84 | 60,483,757 | 0.9041 |
| Scikit-learn Regression   | 6673.57 | 60,451,409 | 0.9042 |
| Random Forest             | 4581.09 | 28,014,613 | 0.9620 |
| XGBoost                   | 6670.46 | 66,664,204 | 0.9097 |

### Insights

* Scratch ≈ Scikit-learn → implementation is correct 
* Random Forest performs best → captures non-linearity
* Linear Regression works well due to linear dataset

---

## Why Unscaled Data for Model Comparison?

* Tree-based models (**Random Forest, XGBoost**) do not require scaling
* Ensures **fair comparison across all models**
* Dataset simplicity makes scaling unnecessary

Demonstrates understanding of when preprocessing is needed

---

## Key Takeaways

* Gradient Descent converges reliably
* Learning rate strongly affects performance
* Scaling improves optimization, not accuracy
* Normal Equation is efficient for small datasets
* Scratch implementation matches library results

---

## Future Improvements

* Test on larger, multi-feature datasets
* Add Regularization (Ridge, Lasso)
* Perform hyperparameter tuning
* Extend to multivariate regression

---

## Full Report

For detailed explanations and methodology, refer to the full report included in this repository.

---

## ⭐ If you found this useful

Consider giving a ⭐ to the repo!
