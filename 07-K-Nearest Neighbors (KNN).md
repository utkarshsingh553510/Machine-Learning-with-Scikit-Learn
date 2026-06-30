# K-Nearest Neighbors (KNN)

KNN (**K-Nearest Neighbors**) एक **Supervised Machine Learning Algorithm** है।

यह Prediction अपने **आस-पास (Nearest Neighbours)** के Data Points के आधार पर करता है।

---

## Example

मान लो 4 लोगों का एक Group है।

अगर 3 लोग बोल रहे हैं कि **Party चलेंगे**, तो बहुत ज्यादा Chance है कि 4th Person भी Party जाने का Decision लेगा।

इसी तरह KNN अपने आसपास के Neighbours को देखकर Prediction करता है।

---

# Uses

1. Email Spam है या नहीं।
2. Product आपको पसंद आएगा या नहीं।

---

# Working

## 1. Choose K

K मतलब **Number of Nearest Neighbours**.

Example:

```text
K = 3
```

मतलब आसपास के 3 सबसे पास वाले Examples को देखेंगे।

---

## 2. Find the Closest Neighbour Points

Machine सबसे पास वाले **K Neighbours** को ढूंढती है।

---

## 3. Count the Neighbours

फिर यह देखती है कि हर Class में कितने Points हैं।

Example:

```text
YES = 2
NO  = 1
```

---

## 4. Majority Voting

जिस Class के Points ज्यादा होंगे वही Final Prediction होगी।

Example:

```text
YES = 2
NO  = 1

Prediction = YES
```

---

# Note

1. K की Value हमेशा **Odd** Select करना अच्छा रहता है।

Example:

```text
3, 5, 7 ...
```

2. KNN बड़े Data पर थोड़ा Slow काम करता है क्योंकि यह हर नए Point के लिए सभी Data Points से Distance Check करता है।

---

# Example

Let Say हमें Fruit का Type पता करना है based on:

- Weight (gm)
- Size (cm)

## Dataset

| Weight (gm) | Size (cm) | Fruit |
|------------:|----------:|:------|
| 180 | 7.0 | A (Apple) |
| 200 | 7.5 | A (Apple) |
| 250 | 8.0 | A (Apple) |
| 300 | 8.5 | O (Orange) |
| 330 | 9.0 | O (Orange) |
| 360 | 9.5 | O (Orange) |

---

# Syntax

```python
from sklearn.neighbors import KNeighborsClassifier
```

---

# Example Code

```python
from sklearn.neighbors import KNeighborsClassifier

x = [
    [180, 7],
    [200, 7.5],
    [250, 8],
    [300, 8.5],
    [330, 9],
    [360, 9.5]
]

# 0 = Apple
# 1 = Orange

y = [0, 0, 0, 1, 1, 1]

model = KNeighborsClassifier(n_neighbors=3)

model.fit(x, y)

weight = float(input("Enter the Weight in grams: "))
size = float(input("Enter the Weight Size in cm: "))

prediction = model.predict([[weight, size]])[0]

if prediction == 0:
    print("This is likely an Apple")
else:
    print("This is likely an Orange")
```

---

# Note

`model.predict()` एक List Return करता है।

इसलिए Single Value लेने के लिए `[0]` लगाया जाता है क्योंकि हमें List के अंदर का पहला Value Return करना होता है।
