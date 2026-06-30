#  Student Score Prediction Project

## Dataset

Dataset basically एक **CSV (Comma Separated Values)** File होती है जिसमें बहुत सारी Information Store होती है, जिसे Model पढ़ सकता है।

### Dataset Download Website

- Kaggle

---

## Example Dataset

| Hours | Score |
|------:|------:|
| 1 | 52 |
| 2 | 57 |
| 3 | 65 |
| 4 | 70 |
| 5 | 75 |
| 6 | 80 |

Dataset Name:

```text
Student.csv
```

---

# Complete Code

```python
import pandas as pd
import numpy as np

from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error, mean_squared_error

data = pd.read_csv("Student.csv")

x = data[["Hours"]]
y = data["Score"]

model = LinearRegression()

model.fit(x, y)

predicted_score = model.predict(x)

mae = mean_absolute_error(y, predicted_score)
mse = mean_squared_error(y, predicted_score)
rmse = np.sqrt(mse)

print("Mean Absolute Error (MAE):", mae)
print("Mean Squared Error (MSE):", mse)
print("Root Mean Squared Error (RMSE):", rmse)
```

> **Add-on:** MAE, MSE और RMSE जितने कम होंगे, Model की Prediction उतनी बेहतर मानी जाएगी।


