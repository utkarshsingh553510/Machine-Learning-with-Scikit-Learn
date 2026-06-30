# Confusion Matrix

Confusion Matrix का use **Classification Models** की Performance को Evaluate करने के लिए किया जाता है।

Let Say हमने एक Machine बनाई जो यह Predict करती है कि Person **Covid Positive** है या **Covid Negative**.

- **YES** → Person Covid Positive
- **NO** → Person Covid Negative

अब Prediction के कुल **4 Cases** हो सकते हैं।

---

# 1. True Positive (TP) ✅

Machine ने **YES** Predict किया और वास्तव में Person **Covid Positive** निकला।

```text
Prediction = YES
Actual = YES

✔ Correct Prediction
```

---

# 2. False Positive (FP) ❌

Machine ने **YES** Predict किया लेकिन वास्तव में Person **Covid Negative** था।

```text
Prediction = YES
Actual = NO

✘ Wrong Prediction
```

इसे **False Alarm** भी कहते हैं।

---

# 3. True Negative (TN) ✅

Machine ने **NO** Predict किया और वास्तव में Person **Covid Negative** था।

```text
Prediction = NO
Actual = NO

✔ Correct Prediction
```

---

# 4. False Negative (FN) ❌

Machine ने **NO** Predict किया लेकिन वास्तव में Person **Covid Positive** था।

```text
Prediction = NO
Actual = YES

✘ Wrong Prediction
```

यह सबसे Dangerous Error माना जाता है क्योंकि बीमारी होने के बाद भी Model ने Detect नहीं किया।

---

# Student Example

| Student | Actual Result | Machine Prediction |
|----------|---------------|--------------------|
| A | Pass | Pass ✅ |
| B | Fail | Fail ✅ |
| C | Pass | Fail ❌ |
| D | Fail | Pass ❌ |

### Mapping

- **True Positive (TP)** → Machine ने Student को Pass बताया और Student वास्तव में Pass था।
- **True Negative (TN)** → Machine ने Student को Fail बताया और Student वास्तव में Fail था।
- **False Positive (FP)** → Machine ने Student को Pass बताया लेकिन Student वास्तव में Fail था।
- **False Negative (FN)** → Machine ने Student को Fail बताया लेकिन Student वास्तव में Pass था।

---

# Confusion Matrix Structure

```text
                 Actual

               Positive   Negative
Prediction
Positive          TP         FP

Negative          FN         TN
```

---

# Python Example

```python
from sklearn.metrics import confusion_matrix

y_true = [1, 0, 1, 1, 0, 1, 0, 0]

y_pred = [1, 0, 1, 0, 0, 1, 1, 0]

cm = confusion_matrix(y_true, y_pred)

print("Confusion Matrix")

print(cm)
```

### Output

```text
[[4 1]
 [1 4]]
```

---

# Matrix Meaning

```text
[[TN  FP]
 [FN  TP]]
```

Example:

```text
[[4 1]
 [1 4]]
```

Means:

- TN = 4
- FP = 1
- FN = 1
- TP = 4

---

# Important Notes

### Precision का use कब करें?

जब **False Positive** Dangerous हो।

**Example:**

- Fraud Detection
- Crime Accusation
- Spam Detection

---

### Recall का use कब करें?

जब **False Negative** Dangerous हो।

**Example:**

- Cancer Detection
- Covid Detection
- Disease Screening

क्योंकि ऐसे Cases में बीमारी वाले Person को Miss नहीं करना चाहिए।

> **Add-on:** Confusion Matrix Classification Models के लगभग सभी Evaluation Metrics (Accuracy, Precision, Recall, F1 Score) का Base होता है।