# Regression

Regression का use तब किया जाता है जब हमें किसी **Number** को Predict करना होता है।

### Examples

1. Student के Marks Predict करना on the basis of Study Hours.
2. Predicting Salary on the basis of Year of Experience.
3. Size के basis पर घर का Price पता करना.

> **Add-on:** Regression हमेशा Continuous Numerical Values Predict करता है।


# Linear Regression

## Linear Regression

### यह कैसे काम करता है?

1. सबसे पहले यह Old Data में एक Pattern बनाएगा।
2. फिर एक Straight Line Draw करेगा।
3. फिर उस Line की मदद से Future में Prediction करेगा।

---

यह एक **Supervised Machine Learning Algorithm** है जिसका use Numbers को Predict करने के लिए किया जाता है।

यह Input और Output के बीच **Straight Line Relationship** बनाता है।

### Formula

```text
y = mx + b
```

- `x` → Input
- `y` → Output
- `m` → Slope
- `b` → Intercept

---

## Syntax

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(x, y)

model.predict([[value]])
```

### Notes

- `LinearRegression()` → Object Create करता है।
- `model.fit(x, y)` → Model Pattern सीखता है।
- `model.predict()` → Prediction करता है।
- `predict()` में Input **2D List** होना चाहिए, इसलिए `[[value]]` लिखा जाता है।

---

## Example Dataset

| Hours Studied | Marks Obtained |
|--------------:|---------------:|
| 2 | 40 |
| 3 | 50 |
| 4 | 65 |
| 5 | 75 |
| 6 | 90 |

---

## Example Code

```python
from sklearn.linear_model import LinearRegression

x = [[2], [3], [4], [5], [6]]
y = [40, 50, 65, 75, 90]

model = LinearRegression()

model.fit(x, y)

hours = float(input("Enter how many hours you studied: "))

predicted_marks = model.predict([[hours]])

print(f"Based on your hours ({hours}) you may score around {predicted_marks}")
```

---

## Note

1. यह Data के जितना अच्छा Pattern सीखेगा उतनी अच्छी Prediction होगी।
2. Accuracy हमेशा Goal नहीं होती।
3. अच्छे Results के लिए Quality Data जरूरी है।




# Classification

Classification का use हम **Category Predict** करने के लिए करते हैं।

### Examples

1. Predicting a Student is **Pass or Fail**
2. Predicting an Email is **Spam or Not Spam**

---

## इसके लिए 3 चीजें हैं

1. Logistic Regression
2. K-Nearest Neighbors (KNN)
3. Decision Tree Classifier

---

## Logistic Regression

Logistic Regression का Output हमेशा **0 या 1** में होता है।

- **0 = No / False / Fail**
- **1 = Yes / True / Pass**

> बाद में जरूरत के अनुसार 0 और 1 को Labels (Yes/No, Pass/Fail, Spam/Not Spam आदि) में Convert कर देते हैं।

---

## K-Nearest Neighbors (KNN)

KNN अपने आसपास (Nearest) के Data Points को देखकर Decision लेता है।

अगर आसपास के अधिकतर लोगों का Decision **YES** है, तो यह भी **YES** Predict करेगा और यदि अधिकतर **NO** हैं तो **NO** Predict करेगा।

---

# Model Training

## 1. fit()

```python
model.fit(x, y)
```

**Meaning:** अपने Data के according Model को Train करना।

---

## 2. predict()

```python
model.predict()
```

**Meaning:** Trained Model का use करके Prediction करना।

---

### Example

जिस तरह हम Book पढ़कर पहले सीखते हैं और फिर Answer देते हैं।

उसी तरह

- `fit()` → पहले Model सीखता (Train होता) है।
- `predict()` → उसके बाद सीखी हुई Knowledge से Prediction करता है।

---


# Classification

**Meaning:** Machine को Examples देकर चीजों को अलग-अलग **Groups / Labels / Categories** में Classify करना।





---

## Logistic Regression

### Examples

| Problem | Predict | Classification Label |
|---------|---------|----------------------|
| Email Filter | Spam / Not Spam | 2 Labels |
| Diagnosis Test | Disease / No Disease | 2 Labels |

---

### Important Point

Logistic Regression का Output केवल **Yes/No**, **Pass/Fail**, **Spam/Not Spam** जैसे Binary Output में होता है।

यानि Model पहले **0 या 1** Predict करता है और फिर उसे Required Label में Convert कर दिया जाता है।

---

# Logistic Regression Syntax

```python
from sklearn.linear_model import LogisticRegression

# बाकी Steps Linear Regression जैसे ही रहते हैं
```

---

## Example Dataset

| Hours Studied | Result |
|--------------:|-------:|
| 2 | 0 |
| 3 | 0 |
| 4 | 1 |
| 5 | 1 |

**Label Meaning**

- `0 = Fail`
- `1 = Pass`

---

## Example Code

```python
from sklearn.linear_model import LogisticRegression

x = [[1], [2], [3], [4], [5]]
y = [0, 0, 1, 1, 1]

model = LogisticRegression()

model.fit(x, y)

hours = float(input("Enter No. of Hours You Have Studied: "))

result = model.predict([[hours]])[0]

if result == 1:
    print(f"Based on {hours} hours, you are likely to PASS")
else:
    print(f"Based on {hours} hours, you are likely to FAIL")
```

> **Note:** `model.predict()` एक List Return करता है, इसलिए Single Value लेने के लिए `[0]` लगाया जाता है।