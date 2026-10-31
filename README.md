# 💰 ANN Salary Prediction

An **Artificial Neural Network (ANN)** based Machine Learning project that predicts an employee's **monthly salary** using work-related features such as experience, working hours, working days, and overtime.

The project includes complete data generation, preprocessing, model training, evaluation, model saving/loading, and an interactive **Streamlit web application**.

---

## 🚀 Project Overview

The goal of this project is to build a neural-network-based salary prediction system.

The model takes four inputs:

- 📅 Experience in Months
- ⏰ Working Hours Per Day
- 📆 Working Days Per Month
- 🕐 Overtime Hours Per Month

and predicts:

> 💰 Monthly Salary

The notebook creates a dataset containing **500 employee records** and saves it as `salary_dataset.csv`.

---

## ✨ Features

- 📊 Synthetic salary dataset generation
- 🔍 Dataset exploration and statistical analysis
- 🧹 Missing-value checking
- 📏 Feature scaling using `StandardScaler`
- 🧠 ANN-based regression model
- 📈 Model training for 100 epochs
- 📊 MAE, MSE, RMSE and R² evaluation
- 🔮 Actual vs Predicted salary comparison
- 💾 Save trained ANN model
- 💾 Save trained scaler
- 🔄 Load model and scaler for prediction
- 🌐 Interactive Streamlit application

---

## 🧠 ANN Architecture

The project uses a fully connected Artificial Neural Network:

```text
Input Layer
4 Features
     │
     ▼
Dense Layer
64 Neurons
ReLU
     │
     ▼
Dense Layer
32 Neurons
ReLU
     │
     ▼
Dense Layer
16 Neurons
ReLU
     │
     ▼
Output Layer
1 Neuron
     │
     ▼
Predicted Monthly Salary
```

The network contains **2,945 trainable parameters**.

---

## 📥 Input Features

| Feature | Description |
|---|---|
| `Experience_Months` | Employee experience in months |
| `Working_Hours_Per_Day` | Average working hours per day |
| `Working_Days_Per_Month` | Number of working days per month |
| `Overtime_Hours_Per_Month` | Monthly overtime hours |

### 🎯 Target

```text
Monthly_Salary
```

The notebook uses a dataset with **500 records and 5 columns**: four input features plus the salary target.

---

## 📊 Dataset

The dataset is generated programmatically using NumPy and Pandas.

```text
500 Employee Records
        │
        ├── Experience
        ├── Working Hours
        ├── Working Days
        ├── Overtime
        │
        ▼
Monthly Salary
```

The generated dataset is saved as:

```text
salary_dataset.csv
```

The notebook also checks dataset shape, information, missing values, and statistical summary.

---

## ⚙️ Machine Learning Workflow

```text
Dataset Generation
        ↓
Data Exploration
        ↓
Feature Selection
        ↓
Train/Test Split
        ↓
StandardScaler
        ↓
ANN Model
        ↓
Model Training
        ↓
Prediction
        ↓
Model Evaluation
        ↓
Save Model + Scaler
        ↓
Streamlit Application
```

---

## 🛠️ Technologies Used

### Programming Language
- Python

### Machine Learning
- TensorFlow
- Keras
- Scikit-learn

### Data Processing
- NumPy
- Pandas

### Visualization
- Matplotlib

### Model Deployment
- Streamlit

### Model Persistence
- Keras `.keras` model
- Joblib `.pkl` scaler

The notebook imports NumPy, Pandas, Matplotlib, TensorFlow/Keras, Scikit-learn and related evaluation tools.

---

## 📏 Data Preprocessing

The dataset is divided into:

```text
Training Data → 400 records
Testing Data  → 100 records
```

A `StandardScaler` is fitted on the training features and then used to transform both training and testing data.

---

## 🏋️ Model Training

The ANN is compiled using:

```python
optimizer = "adam"
loss = "mse"
metric = "mae"
```

The model is trained for:

```text
100 Epochs
Batch Size: 16
```

Training and validation loss/MAE are monitored during training.

---

## 📊 Model Evaluation

The project evaluates the model using:

- **MAE** — Mean Absolute Error
- **MSE** — Mean Squared Error
- **RMSE** — Root Mean Squared Error
- **R² Score** — Coefficient of Determination

The notebook also generates an **Actual vs Predicted Salary** visualization.

---

## 🔮 Salary Prediction

After training, the model predicts salaries for the test dataset.

Example output format:

```text
First 10 Actual Salaries:
[...]

First 10 Predicted Salaries:
[...]
```

The notebook also demonstrates prediction using custom employee information, including experience, working hours, working days and overtime.

---

## 💾 Saved Model Files

The trained ANN is saved as:

```text
salary_ann_model.keras
```

The fitted scaler is saved as:

```text
salary_scaler.pkl
```

These files allow the trained model to be loaded later without retraining. 

---

## 🌐 Streamlit Application

The project also contains a Streamlit interface for salary prediction.

The application loads:

```text
salary_ann_model.keras
salary_scaler.pkl
```

and allows users to enter their work details and receive a predicted monthly salary.

### Application Flow

```text
User Input
   │
   ├── Experience
   ├── Working Hours
   ├── Working Days
   └── Overtime
          │
          ▼
     StandardScaler
          │
          ▼
       ANN Model
          │
          ▼
   Predicted Salary
```

---

## 📂 Project Structure

```text
ANN-Salary-Prediction/
│
├── ANN_Salary_Prediction.ipynb
├── app.py
├── salary_dataset.csv
├── salary_ann_model.keras
├── salary_scaler.pkl
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/ANN-Salary-Prediction.git
```

Enter the project directory:

```bash
cd ANN-Salary-Prediction
```

Install dependencies:

```bash
python -m pip install -r requirements.txt
```

---

## ▶️ Run the Jupyter Notebook

Start Jupyter:

```bash
jupyter notebook
```

Open:

```text
ANN_Salary_Prediction.ipynb
```

Run the cells sequentially to reproduce the dataset generation, preprocessing, ANN training, evaluation and prediction workflow.

---

## 🌐 Run the Streamlit App

Run:

```bash
python -m streamlit run app.py
```

Then open:

```text
http://localhost:8501
```

---

## 🎯 Example Prediction

Example input:

```text
Experience: 12 Months
Working Hours: 10 Hours/Day
Working Days: 26 Days/Month
Overtime: 15 Hours/Month
```

The notebook demonstrates generating a predicted monthly salary from these inputs.

---

## 📌 Important Note

This project uses a **synthetically generated dataset** of 500 records. Therefore, the model is intended as an educational/demo project and should not be treated as a production salary estimation system.

Real-world salary prediction would require a larger and more representative dataset containing factors such as job role, location, education, industry, company size, skills and actual market salary data.

---

## 🚀 Future Improvements

- Add real-world salary datasets
- Add job role and industry
- Add location-based salary prediction
- Add education and skills as features
- Compare ANN with Linear Regression, Random Forest and XGBoost
- Hyperparameter tuning
- Improve model accuracy
- Deploy the application online
- Add interactive salary analytics dashboard
- Add salary range prediction

---

## 👨‍💻 Author

**Prince Yadav**

B.Tech CSE Student | Web Developer | AI & ML Enthusiast

---

## ⭐ Support

If you found this project useful:

⭐ Star the repository  
🍴 Fork the repository  
🐛 Report issues  
💡 Suggest improvements
