## Topics

1. K-Means Clustering
2. Elbow Method
3. PCA
4. Dimensionality Reduction
5. Cluster Visualization

इन सभी का उद्देश्य **Effective Data Analysis** करना है।



---

# 1. K-Means Clustering

मान लो कुछ Students हैं और हमें उन्हें **Height** और **Weight** के according Groups में Divide करना है।

मान लो कुल **3 Groups (Clusters)** बनेंगे।

```text
Cluster 1 → Short Height + Light Weight

Cluster 2 → Medium

Cluster 3 → Tall Height + Athletic
```

यहाँ System यह देखता है कि कितने Possible Clusters बनाए जा सकते हैं।

---

# Uses

1. Shopping Mall में Customers को Divide करना।

   - Premium Customers
   - Budget Buyers

2. School में तेज बच्चों और Weak बच्चों को अलग-अलग Group करना।

---

# K-Means Clustering (5 Step Process)

### Example

मान लो एक Classroom में 10 Students हैं।

हमें उन्हें Height और Weight के Basis पर 3 Groups में Divide करना है।

लेकिन Condition यह है कि Machine Students के बारे में पहले से कुछ नहीं जानती।

---

## Step 1

सबसे पहले Machine को बताना होगा कि कितने Groups बनाने हैं।

इसे **K Value** कहते हैं।

Example:

```text
K = 3
```

मतलब 3 Groups बनेंगे।

---

## Step 2

Machine Randomly **K Random Points** चुनती है।

इन Points को **Centroids (Group Leaders)** कहते हैं।

Example:

```text
K = 3

↓

Randomly 3 Centroids Choose होंगे।
```

---

## Step 3

अब हर Data Point का **Euclidean Distance** सभी Centroids से Calculate किया जाएगा।

जिस Centroid के सबसे पास होगा, उसी Cluster में चला जाएगा।

---

## Step 4

अब नए Cluster बनने के बाद Centroids को Update किया जाएगा।

---

## Step 5

Step 3 और Step 4 तब तक Repeat होंगे जब तक Centroids Stable नहीं हो जाते।

---




# 2. Elbow Method

Elbow Method का use **K (Number of Clusters)** की सही Value चुनने के लिए किया जाता है।

K-Means ke liye hume K ki ek proper Value Chunana padta hai agar humne K ko kam liya to Cluster bahut bade Honge and agar humne K jyada liya to Unnecesaary chote-chote Clusters Ban Jayenge isliye Hume Optimal K dundhana Hota hai 

अगर K बहुत कम होगा तो अलग-अलग Groups एक साथ मिल जाएंगे।

अगर K बहुत ज्यादा होगा तो Unnecessary छोटे-छोटे Groups बन जाएंगे।

इसलिए Optimal K ढूंढना जरूरी होता है।

---

## Example

Data:

```text
{1, 2, 10, 11}
```

---

### Step 1

```text
K = 1
```

Centroid

```text
(1 + 2 + 10 + 11) / 4

= 24 / 4

= 6
```

WCSS

```text
(1-6)² + (2-6)² + (10-6)² + (11-6)²

= 25 + 16 + 16 + 25

= 82
```

---

### Step 2

```text
K = 2
```

Cluster 1

```text
{1, 2}

Centroid = (1 + 2) / 2 = 1.5
```

Cluster 2

```text
{10, 11}

Centroid = (10 + 11) / 2 = 10.5
```

WCSS

```text
(1-1.5)² + (2-1.5)² +
(10-10.5)² + (11-10.5)²

= 0.25 + 0.25 + 0.25 + 0.25

= 1
```

---

### Step 3

```text
K = 3
```

Notebook के अनुसार:

```text
WCSS = 0
```

---

## WCSS Table

| K | WCSS |
|---|-----:|
| 1 | 82 |
| 2 | 1 |
| 3 | 0 |

---

## Elbow Graph

```text
WCSS
 ^
 |
 |\
 | \
 |  \
 |   \__
 |      \____
 +-------------------->
      1   2   3   K

Elbow Point = K = 2
```

इस Example में Best K = **2** माना जाएगा।

---

# Python Example (K-Means)

```python
import pandas as pd
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt

data = {
    "Customer": ["Riya", "Aman", "Faizan", "Neha", "Imran", "Sneha"],
    "Age": [20, 30, 40, 22, 38, 25],
    "Spending": [100, 200, 300, 110, 290, 130]
}

df = pd.DataFrame(data)

x = df[["Age", "Spending"]]

model = KMeans(
    n_clusters=2,
    random_state=42,
    n_init=10
)

df["Group"] = model.fit_predict(x)

plt.figure(figsize=(6,5))

for group in df["Group"].unique():

    group_data = df[df["Group"] == group]

    plt.scatter(
        group_data["Age"],
        group_data["Spending"],
        label=f"Group {group}"
    )

plt.xlabel("Age")
plt.ylabel("Spending Score")
plt.title("Customer Segments (K-Means)")
plt.legend()
plt.grid(True)
plt.show()

print(df)
```

---

# Notes

- `n_clusters` → कितने Groups बनाने हैं।
- `random_state=42` → हर बार लगभग Same Result पाने के लिए।
- `fit_predict()` → Model Train भी करता है और Group Number भी Return करता है।
- `x = df[["Age", "Spending"]]` → केवल उन्हीं Features को Select करते हैं जिनके आधार पर Clustering करनी है।

> **Add-on:** WCSS (Within Cluster Sum of Squares) जितना कम होगा, Cluster उतना Compact होगा। Elbow Method का उद्देश्य ऐसा K चुनना है जहाँ WCSS तेजी से कम होना बंद हो जाए। 