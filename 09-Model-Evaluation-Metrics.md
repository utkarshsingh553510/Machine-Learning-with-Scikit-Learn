# Model Evaluation Metrics

## Mastering Model Evaluation

Basically हमारा Model कैसा Performance कर रहा है, यह पता करने के लिए हम अलग-अलग **Metrics** का use करते हैं।

### Example

Let Say हमें एक Car लेनी है।

तो हम देखते हैं कि:

- Mileage कितना अच्छा है।
- Seats कितनी हैं।
- Engine CC कितना है।
- Features क्या-क्या हैं।

इसी तरह Machine Learning Model को Evaluate करने के लिए भी कई Parameters / Metrics होते हैं।

जैसे:

- Accuracy
- Precision
- Recall
- F1 Score

---

## Topics

1. Sklearn Metrics
2. Regression Metrics
3. Confusion Matrix
4. Classification Metrics

---

# 1. Sklearn Metrics

**Sklearn Metrics** basically एक Toolbox की तरह होता है जिसमें हमारे Model की Performance Measure करने के लिए पहले से बने Functions होते हैं।

इनकी मदद से हम पता कर सकते हैं कि Model कितना अच्छा Predict कर रहा है।

Examples:

- Accuracy
- Precision
- Recall
- F1 Score

---

# 2. Regression Metrics

Regression Models को Evaluate करने के लिए मुख्यतः इन Metrics का use किया जाता है:

- MAE (Mean Absolute Error)
- MSE (Mean Squared Error)
- RMSE (Root Mean Squared Error)

---

# 3. Confusion Matrix

Confusion Matrix का use Classification Model की Performance को Analyze करने के लिए किया जाता है।

यह बताता है कि Model ने:

- कितनी Predictions सही की।
- कितनी गलत की।
- कहाँ Positive को Negative Predict किया।
- कहाँ Negative को Positive Predict किया।

---

# 4. Classification Metrics

Classification Models को Evaluate करने के लिए इन Metrics का use किया जाता है:

- Accuracy
- Precision
- Recall
- F1 Score

---

# Accuracy

Accuracy का मतलब है कि Model ने कुल Predictions में से कितनी Predictions सही की।

### Example

Let 100 लोगों को Disease है।

Model ने उनमें से 90 लोगों को सही Detect किया।

```text
Accuracy = Correct Prediction / Total Prediction

Accuracy = 90 / 100 = 90%
```

---

# Precision

Precision बताता है कि Model ने जितने लोगों को Positive बताया, उनमें से वास्तव में कितने Positive थे।

### Example

Machine ने 10 लोगों को Covid Positive बताया।

लेकिन वास्तव में केवल 6 लोगों को Covid था।

```text
Precision = True Positive / Predicted Positive

Precision = 6 / 10 = 60%
```

---

# Recall

Recall बताता है कि वास्तव में जितने Positive लोग थे, उनमें से Model ने कितनों को सही Detect किया।

### Example

Actual Covid Positive = 8

Machine ने Detect किए = 6

```text
Recall = True Positive / Actual Positive

Recall = 6 / 8 = 75%
```

---

# F1 Score

F1 Score एक Smart Balancing Score होता है।

यह Precision और Recall दोनों को Balance करता है।

इसका use तब करते हैं जब Data काफी ज्यादा **Imbalanced** हो।

### Example

100 लोगों में केवल 5 लोगों को Disease है और बाकी 95 लोगों को Disease नहीं है।

ऐसे Data को **Imbalanced Dataset** कहते हैं।

---



# Sklearn Metrics Example

```python
from sklearn.metrics import (
    accuracy_score,
    precision_score,
    recall_score,
    f1_score
)

y_true = [1, 0, 1, 1, 0, 1, 0]
y_pred = [1, 0, 1, 0, 0, 1, 1]

print("Accuracy :", accuracy_score(y_true, y_pred))
print("Precision:", precision_score(y_true, y_pred))
print("Recall   :", recall_score(y_true, y_pred))
print("F1 Score :", f1_score(y_true, y_pred))
```

### Output

```text
Accuracy = 0.666666...
```

अगर Percentage में चाहिए तो:

```python
print("Accuracy:", accuracy_score(y_true, y_pred) * 100)
```

---

# Note

1. Accuracy हमेशा Enough Metric नहीं होती, खासकर जब Data **Imbalanced** हो।

### Example

100 लोगों में केवल 2 लोगों को Covid है और 98 लोगों को Covid नहीं है।

अगर Model सभी लोगों को **Negative** Predict कर दे, तब भी Accuracy बहुत High आ सकती है, लेकिन Model वास्तव में अच्छा नहीं होगा।

इसीलिए ऐसे Cases में Precision, Recall और F1 Score का use किया जाता है।