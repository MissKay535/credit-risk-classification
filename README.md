# credit-risk-classification
Using supervised learning, build a model that can identify the creditworthiness of borrowers from a dataset of historical lending activity from a peer-to-peer lending services company.

## Logistic Regression Model for Credit Risk Prediction  

This project focuses on building and evaluating a logistic regression model to predict credit risk by classifying loans as either *healthy* (low-risk) or *high-risk*. The model achieves strong overall performance, but special attention is needed due to the inherent class imbalance in the dataset. Below is a detailed breakdown of the model's evaluation, results, and insights.

### **Dataset Overview**  
- **Total Observations:** 77,536 loans  
- **Healthy Loans (Label '0')**: 75,036 (96.77%)  
- **High-Risk Loans (Label '1')**: 2,500 (3.23%)  

This significant imbalance favors healthy loans, meaning that the model is more likely to predict loans as healthy. Handling such imbalance is crucial to ensure fair performance across both loan categories. 

### **Model Performance Summary**  
The logistic regression model was evaluated using accuracy, precision, recall, and F1-scores to assess its ability to predict both loan statuses effectively.

| Metric               | Value         |
|----------------------|---------------|
| **Overall Accuracy** | 99%           |
| **Balanced Accuracy**| 97%           |
| **Healthy Loans (Label '0') Precision** | 100%  |
| **High-Risk Loans (Label '1') Precision** | 84%  |
| **Healthy Loans (Label '0') Recall** | 99%   |
| **High-Risk Loans (Label '1') Recall** | 94%  |

### **Detailed Classification Report**  

| Class | Precision | Recall | F1-score | Support |
|-------|-----------|--------|----------|---------|
| **0** (Healthy Loans) | 1.00 | 0.99 | 1.00 | 18,765 |
| **1** (High-Risk Loans) | 0.84 | 0.94 | 0.89 | 619 |
| **Macro Average** | 0.92 | 0.97 | 0.94 | 19,384 |
| **Weighted Average** | 0.99 | 0.99 | 0.99 | 19,384 |

### **Key Insights and Observations**  
1. **Imbalanced Data:**  
   - The dataset is heavily weighted toward healthy loans, with 96.77% of observations belonging to this category. As a result, the model is inclined to favor predictions of healthy loans more accurately than high-risk loans.  

2. **Performance on Healthy Loans (Label '0'):**  
   - The model predicts healthy loans with perfect precision (100%) and very high recall (99%). This suggests that almost all healthy loans are correctly identified, with very few misclassified as high-risk.

3. **Performance on High-Risk Loans (Label '1'):**  
   - For high-risk loans, the model achieves a precision of 84%, meaning that 84% of predicted high-risk loans are correct. It also has a recall of 94%, indicating that the model captures most of the actual high-risk loans, though some healthy loans are misclassified as high-risk.

### **Conclusion**  
The logistic regression model delivers excellent predictive accuracy overall, with near-perfect performance on healthy loans and strong recall for high-risk loans. However, the imbalance in the dataset slightly affects the precision for high-risk loans.

This imbalance influences the predictions: the model identifies healthy loans with 100% precision and 99% recall. In contrast, for high-risk loans (label ‘1’), it achieves a precision of 84% and a higher recall of 94%. This suggests the model is more likely to correctly flag high-risk loans but at the expense of occasionally misclassifying non-risky loans as risky. The macro average scores (precision: 0.92, recall: 0.97) further confirm the performance imbalance between the two classes.