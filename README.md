\# Cognitive Status Classification Using Machine Learning



\## Overview



This project uses machine learning to classify cognitive status from clinical and demographic data from the OASIS Longitudinal dataset.



The target variable contains three classes:



\* Nondemented

\* Demented

\* Converted



Several machine learning models were trained and compared to identify the best-performing model.



\## Dataset



The project uses the OASIS Longitudinal dataset.



The dataset contains clinical, demographic, and MRI-derived measurements such as:



\* Age

\* Education (EDUC)

\* MMSE

\* CDR

\* eTIV

\* nWBV

\* ASF

\* Gender

\* Socioeconomic Status (SES)



The original dataset is not included in this repository.



\## Methodology



The following steps were performed:



1\. Data loading and exploration

2\. Missing-value handling

3\. Categorical feature encoding

4\. Patient-wise train-test splitting

5\. Feature scaling where required

6\. Training multiple machine learning models

7\. Model evaluation

8\. Feature importance analysis

9\. Cross-validation

10\. Final model saving and verification



\### Patient-wise Split



The dataset contains multiple visits from some subjects. Therefore, the train-test split was performed at the subject level to avoid having records from the same subject in both training and testing sets.



\## Models Compared



\* Decision Tree

\* Random Forest

\* Logistic Regression

\* Support Vector Machine (SVM)



\## Results



Logistic Regression achieved the best performance among the tested models, with \*\*86.8% accuracy\*\* and a \*\*macro F1-score of 0.74\*\* on the patient-wise test set.



Patient-wise 5-fold cross-validation was also performed for Logistic Regression:



\* With CDR: \*\*90.61% ± 1.51% accuracy\*\*

\* Without CDR: \*\*74.27% ± 2.25% accuracy\*\*



This comparison shows that CDR is highly informative for distinguishing the target groups.



\## Visualizations



The `results/` folder contains:



\* Model accuracy comparison

\* Random Forest feature importance

\* CDR distribution across groups

\* Feature correlation heatmap



\## Final Model



The final Logistic Regression pipeline includes:



\* StandardScaler

\* LogisticRegression



The trained model was saved as:



`cognitive\_status\_model.pkl`



The saved model was loaded again and tested to verify that it produced the same test accuracy.



\## Tools and Technologies



\* Python

\* Pandas

\* NumPy

\* Scikit-learn

\* Matplotlib

\* Seaborn

\* Joblib

\* Jupyter Notebook / Kaggle



\## Project Structure



```text

cognitive-status-classification/

│

├── Cognitive\_Status\_Classification.ipynb

├── cognitive\_status\_model.pkl

├── README.md

│

└── results/

&#x20;   ├── model\_comparison.png

&#x20;   ├── feature\_importance.png

&#x20;   ├── cdr\_vs\_group.png

&#x20;   └── correlation\_heatmap.png

```



\## Note



This project is an independent machine learning portfolio project focused on demonstrating data preprocessing, leakage-aware evaluation, model comparison, and interpretation of clinical tabular data.



