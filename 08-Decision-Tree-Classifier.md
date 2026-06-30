# Decision Tree Classifier

Decision Tree एक **Supervised Machine Learning Algorithm** है। 

iska Use Classification and Regression dono Model ke liye Hota hai  

यह Decision लेने के लिए **Tree Structure** का use करता है।

यह Questions पूछता है और उनके Answers के basis पर Final Decision तक पहुँचता है।

---

# Real Life Example

मान लो तुम्हें बाहर जाना है।

```text
Is it raining?
        │
   ┌────┴────┐
  Yes       No
   │         │
Take Umbrella   Go Outside
```

इसी तरह Decision Tree भी एक-एक Question पूछकर Final Prediction देता है।

---

# Uses

1. Loan Approval
2. Disease Prediction
3. Student Pass / Fail
4. Email Spam Detection

---

# Working

## Step 1 : Root Node

सबसे पहला Question पूछा जाता है।

Example:

```text
Study Hours > 4 ?
```

---

## Step 2 : Split

Answer के according Data अलग-अलग Branches में Divide हो जाता है।

```text
Study Hours > 4 ?

Yes  → Branch 1

No   → Branch 2
```

---

## Step 3 : Internal Nodes

अब हर Branch पर नया Question पूछा जाता है।

Example:

```text
Attendance > 75% ?
```

---

## Step 4 : Leaf Node

जब Final Decision मिल जाता है, तब वहाँ कोई और Question नहीं पूछा जाता।

Example:

```text
PASS
```

या

```text
FAIL
```

---

# Example Tree

```text
             Study Hours > 4 ?
                  │
          ┌───────┴────────┐
         Yes              No
          │                │
 Attendance > 75% ?      FAIL
      │
  ┌───┴────┐
 Yes      No
  │         │
PASS      FAIL
```

---

# Syntax

```python
from sklearn.tree import DecisionTreeClassifier
```

---

# Example Dataset

| Study Hours | Attendance | Result |
|-------------:|-----------:|-------:|
| 2 | 60 | 0 |
| 3 | 65 | 0 |
| 4 | 70 | 0 |
| 5 | 80 | 1 |
| 6 | 85 | 1 |
| 7 | 90 | 1 |

**Label Meaning**

- `0 = Fail`
- `1 = Pass`

---

# Example Code

```python
from sklearn.tree import DecisionTreeClassifier

x = [
    [2, 60],
    [3, 65],
    [4, 70],
    [5, 80],
    [6, 85],
    [7, 90]
]

y = [0, 0, 0, 1, 1, 1]

model = DecisionTreeClassifier()

model.fit(x, y)

hours = float(input("Enter Study Hours: "))
attendance = float(input("Enter Attendance (%): "))

prediction = model.predict([[hours, attendance]])[0]

if prediction == 1:
    print("You are likely to PASS")
else:
    print("You are likely to FAIL")
```

---

# Note

- `DecisionTreeClassifier()` Decision Tree Model Create करता है।
- `fit()` Model को Training Data से Train करता है।
- `predict()` नए Data पर Prediction करता है।
- `model.predict()` एक List Return करता है, इसलिए Single Value लेने के लिए `[0]` लगाया जाता है।





# Overfitting, Underfitting & Perfect Fit

जब Machine Learning Model को Train किया जाता है, तब उसके Performance के आधार पर Model तीन प्रकार का हो सकता है।

1. Underfitting
2. Perfect Fit
3. Overfitting

---

# 1. Underfitting

Underfitting तब होता है जब Model Training Data से अच्छे से नहीं सीख पाता।

यानी Model बहुत Simple होता है और Data का Pattern समझ नहीं पाता।

### Characteristics

- Low Training Accuracy
- Low Testing Accuracy
- Poor Prediction

### Example

अगर किसी Student ने Exam के लिए केवल 2–3 Questions ही पढ़े हैं, तो वह Exam में अच्छा Perform नहीं करेगा।

इसी तरह Model ने Data से पर्याप्त Learning नहीं की होती।

---

# 2. Perfect Fit

Perfect Fit वह स्थिति होती है जहाँ Model Data का Pattern सही तरीके से सीखता है।

यह Training Data पर भी अच्छा Perform करता है और New Data पर भी अच्छी Prediction करता है।

### Characteristics

- High Training Accuracy
- High Testing Accuracy
- Good Generalization

### Example

जिस Student ने Concepts अच्छे से समझकर पढ़ाई की हो, वह पुराने और नए दोनों प्रकार के Questions Solve कर सकता है।

---

# 3. Overfitting

Overfitting तब होता है जब Model Training Data को बहुत ज्यादा याद (Memorize) कर लेता है।

यह Training Data पर बहुत अच्छा Perform करता है लेकिन New Data पर अच्छी Prediction नहीं कर पाता।

### Characteristics

- Very High Training Accuracy
- Low Testing Accuracy
- Poor Generalization

### Example

1) अगर कोई Student केवल Previous Year Questions को याद कर ले और Concepts न समझे, तो नए Questions आने पर वह अच्छा Perform नहीं कर पाएगा।

2) Agar Batsman ne sirf straight Ball par Shot marna Sikha & and Jab Match me Bowler ne spin ya Bouncer  Daala to wo out ho gya 

---

# Comparison Table

| Feature | Underfitting | Perfect Fit | Overfitting |
|----------|-------------|-------------|-------------|
| Training Accuracy| Low | High | Very High |
| Testing Accuracy | Low | High | Low |
| Learning         | Too Less| Balanced | Too Much |
| Prediction       | Poor | Good | Poor on New Data |

---

# Diagram

```text
Accuracy
^
|
|                           Overfitting
|                          /\
|                         /  \
|                        /    \
|              Perfect Fit
|                   /\
|                  /
|                 /
|      Underfitting
|
+-------------------------------------------------> Model Complexity
```

---

# Key Points

- **Underfitting** → Model ने कम सीखा।
- **Perfect Fit** → Model ने सही मात्रा में सीखा।
- **Overfitting** → Model ने Training Data को याद कर लिया।

---

> **Add-on:** हमारा Goal हमेशा ऐसा Model बनाना होता है जो **Perfect Fit (Good Generalization)** के सबसे करीब हो, ताकि वह नए (Unseen) Data पर भी अच्छी Prediction कर सके.