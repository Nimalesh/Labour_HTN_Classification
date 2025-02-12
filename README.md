# How to Run my code

## Prerequisites
Before running the project, ensure you have the following installed:
- Python (>=3.8)
- Required libraries: 
  
## Steps to Run the Project

### 1. Clone the Repository

### 2. Load the Dataset
Ensure the dataset file (`4501_AMANHI_With_USG.xlsx`) is placed in the `df/` directory.

### 3. Preprocess the Data
Run the preprocessing script to clean and prepare the data

### 4. Train Models
To train the models, execute

### 5. Evaluate Models
Run the evaluation script to assess performance


### 6. Run the Prediction Pipeline

### 7. Visualize Results

# Understand Variables
Key Features:
Outcome Variables:
Derived Features: Calculate the difference between the highest and lowest blood pressure readings (SBP range, DBP range) to capture BP fluctuations. Combine proteinuria readings across time points into a single aggregated feature (e.g., mean or max proteinuria). Create interaction terms (e.g., SBP × APH) to capture combined effects.

Anterpartum Hemorrhage (APH): Dependent variable 1. Hypertension in Labor (LABOUR_HTN): Dependent variable 2.

Predictor Variables:
Physiological: MAT_WEIGHT, SBP/DBP values, UDIP_PROT (Proteinuria).

Pregnancy History: PREV_SB, PREV_MIS, PREV_PTB, PREV_CS, PREV_MULTIP.

Birth-Related: BIRTH_WEIGHT, GAGEBRTH, SINGLE_TWIN.

Socio-economic: WEALTH_INDEX, PW_EDUCATION.

Maternal Factors: PW_AGE, GRAVIDITY, PARITY.

Time-Based and Derived Features:

Calculate intervals (e.g., DEL_DATE - LABOUR_24).

Previous outcomes as summary statistics (e.g., total complications).

Step 2: Data Preprocessing
Data Cleaning: Handle missing values in variables like UDIP_PROT, PW_EDUCATION, DEL_DATE.

Standardization/Normalization: Normalize continuous features like SBP/DBP, MAT_WEIGHT, BIRTH_WEIGHT.

Categorical Encoding: Convert categorical data (e.g., SINGLE_TWIN, TYPEDELIV) to numerical format using one-hot encoding or label encoding.

Step 3: Feature Engineering
Aggregate SBP/DBP values (e.g., mean or trend over time). Encode pregnancy history (e.g., create a risk index from PREV_SB, PREV_CS). Interaction features (e.g., WEALTH_INDEX × PW_EDUCATION).

Step 4: Model Development
Objective 1: Predict APH
Binary Classification using Logistic Regression, Random Forest, or Gradient Boosting. Consider imbalanced data techniques like SMOTE or class-weighted loss.

Objective 2: Predict HTNL
Similar classification approaches, but experiment with time-based features like LABOUR_24.

Evaluation Metrics:
Accuracy, Precision, Recall, F1-Score for model comparison. Use ROC-AUC for imbalanced targets.

Step 5: Explainability and Interpretability
Apply SHAP or LIME to explain how features like MAT_WEIGHT, PW_AGE influence predictions. Use class-contrastive techniques to identify unique risk factors for APH vs. HTNL.

Step 6: Validate with Domain Experts
Collaborate with obstetricians to validate the importance of key features and the model’s risk factor identification.

Columns Description
Here's a one-word explanation for each column:

WHOWID: Identifier
ORIG_ID: Original ID
PARTICIPANT_ID: Participant
PW_AGE: Maternal Age
PW_EDUCATION: Education
PREV_SB: Spontaneous Abortion
PREV_MIS: Miscarriage
PREV_PTB: Preterm Birth
PREV_MULTIP: Multiples
PREV_CS: Cesarean Section
WEALTH_INDEX: Socioeconomic
SINGLE_TWIN: Pregnancy Type
GRAVIDITY: Pregnancies
PARITY: Births
LABOUR_HTN: Hypertension
LABOUR_24: Labor Start
BIRTH_OUTCOME: Outcome
BABY_SEX: Sex
BIRTH_WEIGHT: Birth Weight
BABY_ID1: Baby ID 1
BIRTH_OUTCOME1: Outcome 1
BABY_SEX1: Sex 1
BIRTH_WEIGHT1: Birth Weight 1
BABY_ID2: Baby ID 2
BIRTH_OUTCOME2: Outcome 2
BABY_SEX2: Sex 2
BIRTH_WEIGHT2: Birth Weight 2
BABY_ID3: Baby ID 3
BIRTH_OUTCOME3: Outcome 3
BABY_SEX3: Sex 3
BIRTH_WEIGHT3: Birth Weight 3
SBP1: Systolic BP 1
DBP1: Diastolic BP 1
UDIP_PROT1: Proteinuria 1
SBP2: Systolic BP 2
DBP2: Diastolic BP 2
UDIP_PROT2: Proteinuria 2
SBP3: Systolic BP 3
DBP3: Diastolic BP 3
UDIP_PROT3: Proteinuria 3
SBP4: Systolic BP 4
DBP4: Diastolic BP 4
UDIP_PROT4: Proteinuria 4
DEL_DATE: Delivery Date
GAGEBRTH: Gestational Age
TYPEDELIV: Delivery Type
age_death_b1: Baby Death Age 1
age_death_b2: Baby Death Age 2
age_death_b3: Baby Death Age 3
APH: Antepartum Hemorrhage
MAT_WEIGHT: Maternal Weight
Missing value imputation
Few Missing Values (≤5% missing): Mean Imputation for normally distributed data. Median Imputation for skewed data or presence of outliers.

Mode for cat values
