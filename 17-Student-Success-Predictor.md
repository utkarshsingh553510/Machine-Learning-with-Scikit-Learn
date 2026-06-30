# Project: Student Success Predictor

## Objective

Student Pass hoga ya Fail hoga predict karna.

---

# Workflow

1. Load & Understand Data
2. Data Preprocessing
3. Feature Scaling
4. Split the Dataset
5. Train the Model
6. Make Prediction
7. Evaluate Model
8. Visualize Results
9. Improve / Experiment
10. Wrap Up

---

# Dataset

| Feature | Description |
|----------|-------------|
| Study Hours | Student kitne ghante padhta hai |
| Attendance | Attendance (%) |
| Past Score | Previous Exam Marks |
| Internet | Internet Access (Yes/No) |
| Sleep Hours | Daily Sleep |
| Passed | Target Column (Yes/No) |

Target Column

```
Passed
```

---

# Step 1 : Load & Understand Data

Dataset ko load karte hain aur uski structure samajhte hain.

Check:

- Head
- Shape
- Info
- Describe
- Missing Values

---

## Code

```python
import pandas as pd

df = pd.read_csv("Student_Success_Dataset.csv")

print(df.head())

print(df.shape)

print(df.info())

print(df.describe(include="all"))

print(df.isnull().sum())
```

---

# Step 2 : Data Preprocessing

Machine Learning sirf Numerical Data accept karta hai.

Categorical Columns

- Internet
- Passed

ko Numeric banana hoga.

Methods

- LabelEncoder
- get_dummies()

---

## Code

```python
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df["Internet"] = le.fit_transform(df["Internet"])

df["Passed"] = le.fit_transform(df["Passed"])

print(df.head())

print(df.dtypes)
```

---

# Step 3 : Feature Scaling

Features

- Study Hours
- Attendance
- Past Score
- Sleep Hours

Different Scale par hote hain.

Scaling ke liye use karte hain

- StandardScaler
- MinMaxScaler

StandardScaler

Mean = 0

Standard Deviation = 1

---

# Step 4 : Split the Data

Dataset ko

80%

Training

20%

Testing

mein divide karte hain.

X = Features

Y = Target

---

# Step 5 : Train Model

Example Models

- Logistic Regression
- Decision Tree

Model Training

```python
model.fit(X_train, y_train)
```

---

# Step 6 : Prediction

```python
y_pred = model.predict(X_test)
```

---

# Step 7 : Evaluate Model

Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

---

# Step 8 : Visualize

Visualization

- Accuracy Charts
- Confusion Matrix Heatmap

---

# Step 9 : Improve

Different Models Try karo

- Logistic Regression
- Decision Tree
- Random Forest
- SVM

Hyperparameter Tuning bhi kar sakte ho.

---

# Step 10 : Wrap Up

- Code Clean karo
- Documentation Complete karo
- Final Result Check karo

---

# Complete Code

```python
import pandas as pd
import numpy as np

from sklearn.preprocessing import StandardScaler, LabelEncoder
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, confusion_matrix

import matplotlib.pyplot as plt
import seaborn as sns

# Load Data
df = pd.read_csv("Student_Success_Dataset.csv")

# Label Encoding
le = LabelEncoder()

df["Internet"] = le.fit_transform(df["Internet"])
df["Passed"] = le.fit_transform(df["Passed"])

# Features
features = [
    "StudyHours",
    "Attendance",
    "PastScore",
    "SleepHours"
]

# Scaling
scaler = StandardScaler()

df_scaled = df.copy()

df_scaled[features] = scaler.fit_transform(df[features])

# X and Y
X = df_scaled[features]

y = df_scaled["Passed"]

# Train Test Split
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)

# Model
model = LogisticRegression()

model.fit(X_train, y_train)

# Prediction
y_pred = model.predict(X_test)

# Report
print(classification_report(y_test, y_pred))

# Confusion Matrix
cm = confusion_matrix(y_test, y_pred)

plt.figure(figsize=(6,4))

sns.heatmap(
    cm,
    annot=True,
    fmt="d",
    cmap="Blues",
    xticklabels=["Fail","Pass"],
    yticklabels=["Fail","Pass"]
)

plt.xlabel("Predicted")
plt.ylabel("Actual")
plt.title("Confusion Matrix")

plt.show()

# User Prediction
print("\n------ Predict Student Result ------")

study_hours = float(input("Enter Study Hours: "))
attendance = float(input("Enter Attendance: "))
past_score = float(input("Enter Past Score: "))
sleep_hours = float(input("Enter Sleep Hours: "))

user_input = pd.DataFrame([{
    "StudyHours": study_hours,
    "Attendance": attendance,
    "PastScore": past_score,
    "SleepHours": sleep_hours
}])

user_scaled = scaler.transform(user_input)

prediction = model.predict(user_scaled)

result = "Pass" if prediction[0] == 1 else "Fail"

print(f"Prediction: {result}")
```

---

# Quick Revision

- Load Dataset
- Check Head, Shape, Info
- Handle Missing Values
- Encode Categorical Data
- Feature Scaling
- Split Data (80/20)
- Train Logistic Regression
- Predict
- Evaluate
- Confusion Matrix
- User Input Prediction