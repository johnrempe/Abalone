## Analysis of Abalone Rings

This project analyzes physical measurements of abalone to predict age (measured by ring count + 1.5 years) using multiple linear regression, transformation techniques, and regression diagnostics.

### Research Focus
- Examine relationships between physical characteristics (length, diameter, height, and weight measures) and ring count  
- Improve model assumptions through log transformation of the response variable  
- Detect and remove influential observations using Cook’s Distance  
- Evaluate model fit using R², adjusted R², F-statistics, and diagnostic plots  

### Key Findings
- Log transformation improved normality and stabilized variance  
- Several predictors were statistically significant in the final model  
- Final adjusted R² ≈ 39–40%, indicating moderate explanatory power  

### Next Steps
To improve predictive performance, future work will implement machine learning models including:
- Random Forest  
- Support Vector Machine (SVM)  
- XGBoost 

---
<img width="1186" height="891" alt="Screenshot 2026-02-11 at 8 41 10 PM" src="https://github.com/user-attachments/assets/e1ab8351-06e4-4bfd-8901-c3a7914adc6a" />
