# Clustering

### i)

Clustering का मतलब होता है **Same / Similar** चीजों को एक Group में रखना, even उन पर कोई Labeling ना हो।

### ii)

Clustering एक Machine Learning Method है जो Data में मौजूद Patterns को पहचानती है।

Similar Habits वाले लोगों को एक Group में रखा जाता है, जबकि पहले से कोई Labeling नहीं होती।

---

## Example

जैसे Friend Circle बनाना।

हम Automatically अपने जैसे Interested लोगों का Group बना लेते हैं।

Examples:

- Cricket खेलने वालों का एक Group
- Music पसंद करने वालों का एक Group

इसे भी Clustering कहा जा सकता है।

---

### Example

YouTube पर जो Videos Suggest होती हैं, वे भी Similar Interest वाले Users की Clustering के आधार पर होती हैं।

---

# Notes

1. **K-Means Clustering** सबसे Common Clustering Algorithm है।

2. K-Means Clustering में हम कोई Number Predict नहीं करते।

यह केवल Similar Data Points को अलग-अलग Groups में Divide करती है।

---

# Supervised ML vs Unsupervised ML

| Supervised ML | Unsupervised ML |
|--------------|-----------------|
| Data के साथ Question और Answer दोनों होते हैं। | Data के साथ कोई Answer या Label नहीं होता। |
| Labeled Dataset | Unlabeled Dataset |
| Model Known Labels से सीखता है। | Model खुद Patterns खोजता है। |

---

# 4. Mean & Centroids

## i) Mean

Mean यानी किसी List की **Average Value**.

### Example

| Customer | Age | Spending |
|----------|----:|----------:|
| Riya | 20 | 100 |
| Aman | 30 | 200 |
| Faiz | 40 | 300 |

Mean Spending

```text
(100 + 200 + 300) / 3

= 600 / 3

= 200
```

---

## ii) Centroid

Centroid मतलब **Middle Point**.

K-Means में हर Cluster का एक Center Point होता है जिसे Centroid कहते हैं।

Example:

Age का Centroid

```text
(20 + 30 + 40) / 3

= 30
```

अब कोई नया Customer आएगा तो उसके Age और Spending के आधार पर उसे सबसे नज़दीकी Centroid वाले Group में रखा जाएगा।

---

# 5. Distance (Euclidean Distance)

मान लो दो Groups हैं:

- Group A
- Group B

अब कोई नया Person आया जिसकी Age 22 Years है।

हमें पता करना है कि वह Group A में जाएगा या Group B में।

इसके लिए Euclidean Distance का use किया जाता है।

Euclidean Distance बताती है कि दो Data Points एक-दूसरे से कितनी दूर हैं।

---

## Formula (2D)

```text
d = √((x₂ - x₁)² + (y₂ - y₁)²)
```

## Formula (3D)

```text
d = √((x₂-x₁)² + (y₂-y₁)² + (z₂-z₁)²)
```

---

## Example

A = (1, 2)

B = (4, 6)

```text
d = √((4-1)² + (6-2)²)

= √(3² + 4²)

= √(9 + 16)

= √25

= 5
```

---

# Applications

1. Flipkart, Amazon Recommendation System
2. Dating Apps में Similarity के Basis पर Matching
3. Medical Diagnosis में Similar Patients को Group करना

---

# Use Cases in ML

### 1. K-Means Clustering

नए Person को किस Group में रखना है।

### 2. KNN

नए Student की Height और Weight देखकर Nearest Students से Compare करके Prediction करना।

### 3. Outlier Detection

अगर कोई Person बाकी लोगों से बहुत अलग है, तो System बता सकता है कि वह Error है या Fraud।

---



# 6. Variance & Spread

Variance बताता है कि Data Mean से कितना फैला (Spread) हुआ है।

let say ek person hai wo  40-50 rs ke beech me paisa Kharcha Kr rha hai to jitne log itna Kharcha krenge unhe Hum ek group me daal denge but let say agar koi person 10 rs Kharcha kr rha hai and koi person 500 rs kharcha kr rha hai to inke beech me Bahut Bada Diff hai isi ko hum spread khte hai and iska Mathematical Naam hai Variance .


---

### Important Points

- Data Points पास-पास होंगे → **Low Variance**
- Data Points दूर-दूर होंगे → **High Variance**

---

## Formula

```text
Variance = Σ(x - x̄)² / n
```

---

## Example

Data:

```text
[100, 120, 130, 150, 100]
```

Mean

```text
(100 + 120 + 130 + 150 + 100)

= 600 / 5

= 120
```

Variance

```text
((100-120)² +
 (120-120)² +
 (130-120)² +
 (150-120)² +
 (100-120)²) / 5

= (400 + 0 + 100 + 900 + 400) / 5

= 1800 / 5

= 360