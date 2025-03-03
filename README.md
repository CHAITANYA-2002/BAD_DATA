# BAD_DATA: A Machine Learning Approach for Detecting Corrupt Data

## 📌 Overview
This repository contains a Jupyter Notebook that explores **bad data detection using machine learning**. The project introduces **artificial errors** into a dataset, processes the data to clean and encode it, and then trains a **Random Forest and XGBoost model** to detect the errors. Additionally, performance is evaluated on a **newly generated test dataset** to verify the model's generalization ability.

---

## 📂 Repository Structure
```
BAD_DATA/
│-- Data/                     # Contains the dataset used for training and testing
│-- bad_data.ipynb            # Jupyter Notebook with all steps: data corruption, cleaning, training, and evaluation
│-- README.md                 # Documentation of the repository
```

---

## 📊 Dataset Information
**Dataset Name:** `Housing.csv`

### 📑 Description:
The dataset contains various features about housing properties, including:
- **price**: The price of the property
- **area**: Size of the house in square feet
- **bedrooms, bathrooms, stories**: Property specifications
- **parking**: Number of available parking spaces
- **furnishingstatus**: Whether the house is furnished, semi-furnished, or unfurnished
- **mainroad, guestroom, basement, hotwaterheating, airconditioning, prefarea**: Boolean attributes describing property features

### 🔍 Data Corruption Applied:
To simulate real-world bad data scenarios, the following corruptions were introduced:
- **Missing Values**: Randomly removed data from different features
- **Invalid Values**: Injected incorrect entries such as "unknown", "error", "###", or out-of-range values
- **Outliers**: Generated unrealistic negative and extreme values for numerical fields
- **Logical Inconsistencies**: Introduced conflicting values in categorical fields

---

## ⚙ Machine Learning Pipeline
### **Step 1: Data Preprocessing**
- Identify and replace invalid categorical values
- Convert non-numeric values to NaN in numerical columns
- Handle missing values using the most frequent value imputation
- Encode categorical variables using Label Encoding

### **Step 2: Feature Engineering**
To improve model accuracy, additional features were created:
- **Price per square foot** (`price / area`)
- **Bathroom-to-bedroom ratio** (`bathrooms / bedrooms`)
- **Log transformation** for `price` and `area` to handle skewed distributions

### **Step 3: Model Training**
Two machine learning models were trained to detect bad data:
1. **Random Forest Classifier** (Baseline Model)
2. **XGBoost Classifier** (Optimized Model for Better Accuracy)

Both models were evaluated using:
- **Accuracy Score**
- **Precision & Recall**
- **Confusion Matrix**
- **Feature Importance Analysis**

### **Step 4: Model Evaluation on New Bad Data**
A separate test dataset was generated with **different types of corruptions** to assess the model's generalization ability. The performance on this test set was compared to the training results.

---

## 🔥 Optimization Strategies Used
To improve model accuracy, the following enhancements were applied:
1. **Hyperparameter Tuning** using `RandomizedSearchCV` to find the best model parameters
2. **Feature Engineering** to create new meaningful attributes
3. **Using XGBoost**, which handles missing values more effectively than Random Forest
4. **Comparison of model accuracy on training vs unseen test data**

---

## 📈 Results & Visualizations
Several visualizations were included in the notebook to analyze model performance:
- **Feature Distributions:** Initial dataset visualization
- **Missing & Corrupt Data Count:** Bar plot showing injected errors
- **Confusion Matrix:** Evaluating model classification performance
- **Feature Importance:** Identifying the most important attributes for bad data detection
- **Accuracy Comparison Chart:** Comparing Random Forest vs Tuned Random Forest vs XGBoost

---

## 🛠 Installation & Usage
### **1️⃣ Clone the Repository**
```bash
git clone https://github.com/CHAIYANYA-2002/BAD_DATA.git
cd BAD_DATA
```

### **2️⃣ Install Dependencies**
```bash
pip install pandas numpy scikit-learn matplotlib seaborn xgboost
pip install -r reuirements.txt
```

### **3️⃣ Run the Jupyter Notebook**
```bash
jupyter notebook bad_data.ipynb
```

---

## 🚀 Expected Results
After running the notebook, the following outputs should be observed:
- **Random Forest Accuracy:** ~80%
- **Tuned Random Forest Accuracy:** ~85%
- **XGBoost Accuracy:** ~90-95%
- **Successful bad data detection** in both training and test datasets

---

## 📌 Future Improvements
- Experiment with **Deep Learning models** for anomaly detection
- Implement **autoencoder-based outlier detection**
- Enhance bad data generation using **synthetic data techniques**
- Deploy the model using **Flask or FastAPI** for real-time bad data detection

---

## 👨‍💻 Contributors
- **Chaitanya-2002** (Repository Owner & Developer)

---

## 📜 License
This project is licensed under the **MIT License**. Feel free to modify and improve it!

