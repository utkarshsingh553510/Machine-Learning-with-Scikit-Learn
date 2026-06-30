# Regression Metrics

Regression Models को Evaluate करने के लिए मुख्य रूप से 3 Metrics का use किया जाता है:

1. MAE (Mean Absolute Error)
2. MSE (Mean Squared Error)
3. RMSE (Root Mean Squared Error)

इन Metrics की मदद से हम पता करते हैं कि Model की Prediction Actual Value से कितनी दूर है।

---

# Example Dataset

| Student | Real Marks | Model Prediction | Mistake |
|----------|-----------:|-----------------:|---------:|
| A | 90 | 85 | 5 |
| B | 60 | 70 | 10 |
| C | 80 | 70 | 10 |
| D | 100 | 95 | 5 |

इन Mistake Numbers का use करके हम MAE, MSE और RMSE निकालते हैं।

---

# 1. MAE (Mean Absolute Error)

MAE का मतलब है कि Average में Model Actual Value से कितना Error कर रहा है।

### Steps

1. Prediction और Actual Value का Difference निकालो।
2. Negative Sign हटा दो (Absolute Value लो)।
3. सभी Errors को Add करो।
4. Total Values से Divide कर दो।

### Example

```text
MAE = (5 + 10 + 10 + 5) / 4

= 30 / 4

= 7.5
```

---

# 2. MSE (Mean Squared Error)

MSE में सभी Errors का Square करके Average निकाला जाता है।

### Formula

```text
MSE = (5² + 10² + 10² + 5²) / 4

= (25 + 100 + 100 + 25) / 4

= 250 / 4

= 62.5
```

---

# 3. RMSE (Root Mean Squared Error)

RMSE, MSE का Square Root होता है।

### Formula

```text
RMSE = √62.5

≈ 7.90
```

---

# Python Example

```python
from sklearn.metrics import mean_absolute_error, mean_squared_error
import numpy as np

real_scores = [90, 60, 80, 100]
predicted_scores = [85, 70, 70, 95]

mae = mean_absolute_error(real_scores, predicted_scores)
mse = mean_squared_error(real_scores, predicted_scores)
rmse = np.sqrt(mse)

print("MAE :", mae)
print("MSE :", mse)
print("RMSE:", rmse)
```

---

# Output

```text
MAE  : 7.5
MSE  : 62.5
RMSE : 7.905694...
```

---

# Notes

### MAE का use कब करें?

जब Simply Average Error जानना हो।

---

### MSE का use कब करें?

जब बड़ी Mistakes (Large Errors / Outliers) को ज्यादा Importance देनी हो।

---

### RMSE का use कब करें?

जब Error को Original Unit में समझना हो।

**Examples:**

- House Price Prediction
- Student Marks Prediction
- Salary Prediction

> **Add-on:** MAE, MSE और RMSE — तीनों में **जितनी कम Value होगी, Model उतना बेहतर माना जाता है।**