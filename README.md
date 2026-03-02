## House Price Regression

This project builds a regression pipeline to estimate house prices from structured property features.
Focus: model stability, proper preprocessing, and controlled bias–variance tradeoff.

---

**Challenges Addressed**

- Right-skewed target variable  
- High dimensionality after one-hot encoding  
- Multicollinearity between correlated features  
- Risk of overfitting with plain Linear Regression  

---

**Approach**

- Log-transformed `SalePrice` to stabilize variance  
- Compared Linear Regression, Ridge (L2), and Lasso (L1)  
- Built a clean `Pipeline` with:
  - Median imputation (numeric)
  - Constant imputation (categorical)
  - Standard scaling (numeric)
  - One-hot encoding (categorical)
- Tuned regularization strength using cross-validation  

---

**Final Model**

*Ridge Regression (cross-validated alpha)*  
- Test Log RMSE ≈ 0.13  
- ≈ 14% multiplicative error  
- Stable coefficients under multicollinearity  
- Strong generalization compared to baseline OLS  

---

**Observations**

- Regularization dramatically reduced variance  
- Lasso removed 172 redundant dummy features  
- Feature scaling is essential for fair L1/L2 penalization  
- Pipelines prevent leakage and ensure reproducibility  

---

**Business Framing**

The focus is reliable baseline valuation, not perfect prediction.
Regularization ensures the model remains stable under high dimensionality and correlated features, making it more suitable for real-world pricing systems.
