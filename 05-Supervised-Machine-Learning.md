# Supervised Machine Learning

**Supervised** मतलब किसी के **Supervision** के अंदर सीखना।

यानि Machine को ऐसे Examples की help से सिखाया जाता है जिनका Answer पहले से ही दिया होता है। इसे **Labeled Data** कहते हैं।

### Example:

Let एक Student है। उसके सामने 10 Questions दिए गए।

उनमें से 9 Questions का Answer पहले से दिया गया है और 1 Question का Answer नहीं दिया गया।

Machine उन 9 Examples के basis पर 10th Question का Answer Predict करेगी।

---

## यहाँ पर हम Machine को Train करेंगे दो चीजों के लिए

1. **Predict Numbers**
   - Marks Predict करना
   - Price Predict करना
   - etc.

2. **Categories Predict करना**
   - Pass / Fail
   - Spam / Not Spam
   - Yes / No
   - etc.

---

# Supervised Machine Learning Cycle

```text

Collect Labeled Data
        ↓
Train Model
        ↓
Make Predictions
        ↓
Evaluate Performance
        ↓
Refine Model
        ↓
Collect Labeled Data (Repeat Cycle)
```

---

# Machine Learning Algorithms and Training Process

```text
                  Regression
                 /          \
      Linear Regression   Classification
                           /      |       \
          Logistic Regression    KNN    Decision Tree Classifier

                    ↓
              Model Training
               /          \
           fit()       predict()
```
