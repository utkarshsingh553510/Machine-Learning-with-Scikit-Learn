# PCA (Principal Component Analysis)

## 1) PCA

### Full Form

**PCA = Principal Component Analysis**

---

### PCA क्या है?

PCA का उपयोग **High Dimensional Data** को कम Dimensions में Convert करने के लिए किया जाता है **without losing much information**.

यदि Dataset में बहुत सारे Features (Columns) हों लेकिन सभी जरूरी न हों, तो PCA सबसे Important Information को रखकर बाकी कम Important Features को Reduce कर देता है।

---

### Example

मान लो एक Car Dataset है जिसमें लगभग 100 Features हैं।

जैसे

- Mileage
- Color
- Speed
- Engine
- Weight
- Length
- Width
- Price
- etc.

लेकिन हमें केवल Car की Performance Predict करनी है।

तो सभी 100 Features की जरूरत नहीं होगी।

PCA कम Important Features हटाकर केवल Important Information रखता है।

---

## PCA कैसे Help करता है?

1. Less Important Columns Remove करता है।
2. केवल Important Features रखता है।
3. Accurate Prediction और Grouping में मदद करता है।

---

# Low Dimensional Data

Low Dimensional Data का मतलब है ऐसा Data जिसमें Features/Columns कम हों।

### Example

अगर हमें केवल किसी Batsman की Performance देखनी है तो केवल जरूरी Features रखेंगे।

जैसे

- Runs
- Balls Faced
- Strike Rate
- 4s
- 6s
- Out Balls
- Fitness Level
- Average

बाकी Unnecessary Columns हटाए जा सकते हैं।

---

# High Dimensional Data

High Dimensional Data मतलब बहुत ज्यादा Features/Columns वाला Dataset।

Example

Batsman के लिए

- Runs
- Balls Faced
- Strike Rate
- Fitness
- Average
- Power Play Runs
- etc.

यदि Features बहुत ज्यादा हों तो Data High Dimensional कहलाता है।

---

# High Dimensional Data की Problems

1. Model Training Slow हो जाती है।
2. Data Visualization Difficult हो जाता है।
3. Overfitting की संभावना बढ़ जाती है।

---

# Dimensionality Reduction

Dimensionality Reduction का मतलब है

**Input Features (Columns) की संख्या कम करना बिना Important Information खोए।**

### Example

यदि Dataset में 10 Columns हों,

तो PCA उन्हें 2 या 3 Columns में बदल सकता है।

इससे

- Analysis आसान होता है।
- Visualization आसान होती है।
- Model Faster Train होता है।

---

# Image Example

मान लो एक बड़ी Image है।

यदि उसे Compress करना हो बिना Quality ज्यादा खोए,

तो PCA Image को Compress करने में भी उपयोग किया जाता है।

Original Image की Maximum Information Save रहती है।

---

# Advantages of PCA

1. Model को Faster बनाता है।
2. Visualization आसान हो जाती है।
3. Performance Improve होती है।
4. Training Fast होती है।
5. Noise Remove करता है।
6. Overfitting कम करता है।

---

# Important Note

PCA एक Mathematical Technique है।

यह Columns को Reduce करता है लेकिन Important Information को Preserve करता है।

Example

4 Page की Book पढ़ने की बजाय उसका Summary पढ़ लेना।

---

# Python Code

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
```

---

## StandardScaler

PCA लगाने से पहले सभी Features को Equal Scale पर लाना जरूरी होता है।

इसीलिए PCA से पहले StandardScaler लगाया जाता है।

---

# Dataset

```python
data = {

    "Age":[25,30,35,40,45,50],

    "Income":[30000,40000,50000,60000,70000,80000],

    "Spending":[70,60,50,40,30,20],

    "Saving":[1000,5000,8000,10000,15000,20000]

}

df = pd.DataFrame(data)
```

---

# Standard Scaling

```python
scaler = StandardScaler()

scaled_data = scaler.fit_transform(df)
```

---

### fit()

Data से Mean और Standard Deviation सीखता है।

---

### transform()

सीखी हुई Values का उपयोग करके Data Scale करता है।

---

## Z-Score Formula

```text
Z = (X − Mean)
/ Standard Deviation
```

---

### Example

Income

```text
30000

Mean = 55000

Std = 18708.29
```

```text
Z

=

(30000 - 55000)

/

18708.29

≈ -1.34
```

Negative Value

→ Average से नीचे

Positive Value

→ Average से ऊपर

0

→ Exactly Average

---

# PCA Example 

```python

pca = PCA(n_components=2)  # iska matlab hai ki jo 4 columns the Age,income,spending,saving inko Todkar 2 columns me kar do 

pca_result = pca.fit_transform(scaled_data)

pca_df = pd.DataFrame(pca_result,columns=["PCA1","PCA2"])

explained_variance = pca.explained_variance_ratio_

print(np.round(explained_variance * 100,2))

plt.figure(figsize=(8,6))

plt.scatter(

pca_df["PCA1"],

pca_df["PCA2"]

)

plt.title("PCA Projection (2D View)")

plt.xlabel("PCA1 (Main Pattern)")

plt.ylabel("PCA2 (Minor Pattern)")

plt.grid(True)

plt.show()
```

---

## Output

```text
Variance Captured

[99.65, 0.35]
```

मतलब

**PCA1**

लगभग

**99.65%**

Information Hold कर रहा है।

और

**PCA2**

केवल

**0.35%**

Information Hold कर रहा है।

यानी लगभग पूरी Information PCA1 में आ गई है और PCA2 में बहुत कम Information बची है।

---

# Quick Revision

- PCA = Principal Component Analysis
- High Dimensional Data → बहुत ज्यादा Features
- Low Dimensional Data → कम Features
- PCA Important Information बचाकर Features Reduce करता है।
- PCA से पहले हमेशा **StandardScaler** लगाते हैं।
- `explained_variance_ratio_` बताता है कि प्रत्येक Principal Component कितनी Information Capture कर रहा है।
- PCA Training Fast करता है, Visualization आसान बनाता है और Overfitting कम करने में मदद करता है।