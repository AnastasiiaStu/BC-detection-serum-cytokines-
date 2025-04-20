#  Machine learning for breast cancer prediction
**Introduction**

Breast cancer is the most common malignant disease diagnosed in women worldwide. The prevalence and incidence of breast cancer is increasing every year. Early diagnosis of breast cancer is critically important for improving patient survival. Cytokines are known to play an important role in the processes of immunomodulation, and dysregulation of their levels in blood and tissues is associated with the appearance of various types of tumors. Thus, cytokine analysis can serve as a non-invasive biomarker for cancer detection, complementing traditional methods (such as mammography and biopsy). In recent years, machine learning methods have been increasingly used in medical diagnostics, making it possible to identify complex patterns in biomedical data. This work explores the possibility of using concentrations of various cytokines in the blood for the differential diagnosis of malignant and benign breast diseases using modern machine learning algorithms.

**Goal** of the work is to compare different machine learning algorithms to select the best model for classifying patients into groups of breast cancer and benign breast diseases based on data on blood cytokine concentrations.

**Data description**

A data set containing information on the concentration of 12 cytokines determined by enzyme immunoassay in 177 patients was used for the study.
**104** patients with **primary Breast Cancer** (patients who had not received chemotherapy/radiotherapy/endocrine therapy) and **47** patients with 
**Benign Breast Disease**

**Pre-processing of data**

Before training the models, the following preprocessing steps were performed:
1. Converting the target variable to binary format
2. Checking for missing values
3. Dividing the data into training (80%) and test (20%) samples while maintaining stratification
4. Balancing classes using the SMOTE method to eliminate the imbalance (130 cases of cancer versus 47 benign)
5. Standardization of features using Standard Scaler

**Algorithms:**
1.	Logistic regression
2.	The k-nearest neighbors (kNN) method
3.	Decision tree
4.	Random Forest
5.	AdaBoost
6.	Bagging
7.	XGBoost
8.	Gradient boosting (GBDT)

For each algorithm, optimal hyperparameters were searched using GridSearchCV and cross-validation (3 folds). The area under the ROC curve (ROC-AUC) was used as an optimization metric.

**Discussion**

The results of the study demonstrate that machine learning methods, especially ensemble algorithms (XGBoost, gradient boosting, and random forest), can effectively use cytokine concentration data for differential diagnosis of breast diseases.
The obtained metric values (ROC-AUC of about 0.82 for the best models) indicate a good classification quality. It is especially important to note the high sensitivity (recall) of the best models (0.92), which is extremely important in medical diagnostics, as it reduces the likelihood of missing cases.
The best results were shown by ensemble methods, especially XGBoost and gradient boosting.

**Further research may be aimed at:**
1. Increasing the sample size of patients
2. Adding patients' clinical data to the analysis
3. Study of the temporal dynamics of changes in cytokine concentration
4. Comparison with DL: Boosting can be inferior to deep neural networks (for example, CNN/Transformer) in detecting complex patterns.

The results obtained are important for the development of noninvasive breast cancer diagnosis methods and can be used as an additional tool in clinical practice.
