# Data Preprocessing

## Data Preprocessing Funnel

```
           Raw Data
              │
              ▼
      Handle Missing Data
              │
              ▼
   Encode Categorical Values
              │
              ▼
      Feature Scaling
              │
              ▼
         Split Data
              │
              ▼
        Prepared Data
```

---

# Advantages of Data Preprocessing

## 1) Raw Data ko Clean Data me Convert karna

Raw Data generally **Incomplete** ya **Dirty Data** hota hai.

Data Preprocessing ki help se hum Raw Data ko **Cleaned Data** me convert kar sakte hain.

**Example:**

Jaise hum Market se Fresh Sabzi kharidte hain aur ghar laakar use saaf (Clean) karte hain.

Waise hi Machine Learning me bhi Raw Data ko pehle clean kiya jata hai.

---

## 2) Missing Data Handle karna

Agar Data me Missing Values hain to unhe:

- Delete kar sakte hain.
- Ya Default Value (0, 1 etc.)
- Ya Mean / Median / Mode se Fill kar sakte hain.

---

## 3) Encode Categorical Data

Machine Learning Models **Numerical Data** ko samajhte hain Text Data Nahi 

Ye Text Data ko directly understand nahi karte.

### Example

```
Male
Female
```

Isko Numeric Values me convert karte hain.

```
Male   → 0
Female → 1
```

Is process ko **Encoding** kehte hain.

---

## 4) Feature Scaling

Suppose ek Feature ki Range hai:

```
0 – 100
```

Aur dusre Feature ki Range hai:

```
10000 – 20000
```

Agar directly Model me de diya jaye to bada value wala Feature dominate karega.

Isliye dono Features ko same Scale par lana padta hai.

Is process ko **Feature Scaling** kehte hain.

---

## Common Feature Scaling Methods

- Standard Scaler
- Min-Max Scaler

---

## 5) Split Data

Machine Learning me Data ko mainly do parts me divide kiya jata hai.

```
X → Features (Input)

y → Labels (Output)
```

Uske baad Data ko Train aur Test me divide kiya jata hai.

---

## Important Note

Jaise hum Raw Vegetables ko directly nahi khate,

Pehle unhe Wash aur Clean karte hain.

Waise hi Machine Learning me bhi Raw Data ko directly Model me nahi dete.

Pehle Data Preprocessing karte hain i.e Clean Krte Hai Then Use Krte hai 

---

## Conclusion

Data Preprocessing Machine Learning ka bahut important step hai.

Agar Data sahi tarike se preprocess nahi hoga to Model ki Accuracy bhi achhi nahi hogi.






# Handling Missing Data

Machine Learning Models **Missing Values (NaN / NULL)** ko directly handle nahi kar paate.

Isliye Data ko Model me dene se pehle Missing Values ko clean karna zaruri hota hai.

---

## Example

| Name | Age | Salary |
|------|----:|-------:|
| Pavan | 25 | 50000 |
| Rajesh| NaN| 60000 |
| Kapil | 32 | NaN |

Yahan:

- Age me ek Missing Value hai.
- Salary me ek Missing Value hai.

Isliye pehle Missing Values ko handle karna padega.

---

# Missing Data Handle Karne ke Best Ways

### 1. `dropna()`

Jis Row ya Column me Missing Value ho use Delete kar deta hai.

### 2. `fillna(value)`

Missing Value ki jagah koi Value Fill kar deta hai.

### 3. `isnull().sum()`

Har Column me kitni Missing Values hain, ye count batata hai.

---

# Example

```python
import pandas as pd

data = {
    "Name": ["Pavan", "Kapil", "Lalit", "Ishan", "Om"],
    "Age": [25, None, 44, 23, None],
    "Salary": [50000, 60000, 70000, None, None]
}

df = pd.DataFrame(data)

print("Original Data Frame")
print(df)
```

---

## Original Output

| Name | Age | Salary |
|------|----:|-------:|
| Pavan | 25 | 50000 |
| Kapil | NaN| 60000 |
| Lalit | 44 | 70000 |
| Ishan | 23 | NaN   |
| Om    | NaN| NaN   |

---

## Missing Values Count

```python
print(df.isnull().sum())
```

### Output

```text
Name      0
Age       2
Salary    2
dtype: int64
```

---

# Method 1: Drop Missing Values

```python
df_drop = df.dropna()

print(df_drop)
```

### Output

| Name | Age | Salary |
|------|----:|-------:|
| Pavan | 25 | 50000 |
| Lalit | 44 | 70000 |

**Note:** `dropna()` un Rows ko remove kar deta hai jisme Missing Value hoti hai.

---

# Method 2: Fill Missing Values

Age Column me Missing Values ko Mean se Fill karte hain.

```python
df["Age"].fillna(df["Age"].mean(), inplace=True)
```

Age  Column me Missing Values ko Mean Value se Fill karte hain.

```python
df["Salary"].fillna(df["Salary"].mean(), inplace=True)
```

Salary Column me Missing Values ko Mean Value se Fill karte hain.

---

## Updated Output

| Name | Age | Salary |
|------|-----------:|----------:|
| Pavan | 25.000000 | 50000 |
| Kapil | 30.666667 | 60000 |
| Lalit | 44.000000 | 70000 |
| Ishan | 23.000000 | 60000 |
| Om    | 30.666667 | 60000 |

---

# Notes

1. Agar Data bahut kam Missing hai to `dropna()` use kar sakte hain.

2. Numeric Data ke liye Missing Values ko **Mean**, **Median** ya **Mode** se Fill karna better hota hai.

3. Categorical Data ke liye generally **Mode** use kiya jata hai.

4. Data Cleaning shuru karne se pehle hamesha check karo ki kitne %  Missing Values hain.

Print(df.isnull().Sum()*100)





# Encoding Categorical Values

Machine Learning Models **Text (Categorical Data)** ko directly understand nahi karte.

Ye sirf **Numerical Data** par kaam karte hain.

Isliye Categorical Values ko Numbers me convert karna padta hai.

Is process ko **Encoding** kehte hain.

---

# Example

Suppose ek Dataset me Car Brand diya hua hai.

```
Car Brand

BMW
Tata
Audi
BMW
Audi
```

Machine in Text Values ko directly process nahi kar sakti.

Isliye hume Encoding karni padti hai.

---

# Types of Encoding

1. Label Encoding
2. One Hot Encoding

---

# 1) Label Encoding

Label Encoding me har Unique Category ko ek Unique Number assign kiya jata hai.

Lable Encoding Sirf Categorical Value Pr Lagta hai i.e Jaha Pr Sirf 2 Values ho Yes/No,Pass/Fail,Male/Female etc.

### Example

| Gender | Encoded |
|---------|---------|
| Male    | 0 |
| Female  | 1 |

Ya

| Car Brand | Encoded |
|-----------|---------|
| BMW       | 0 |
| Tata      | 1 |
| Audi      | 2 |

---

## Python Example

Suppose hamare paas CSV File hai jisme columns hain:

- Name
- Gender
- Passed

```python

import pandas as pd

from sklearn.preprocessing import LabelEncoder

df = pd.read_csv("student.csv")

df_label = df.copy()

le = LabelEncoder() -> It means Humne Lable Encoder Ka Humne ek Object Bana Liya 
```

Gender Encode:

```python
df_label["Gender_Encoded"] = le.fit_transform(df_label["Gender"])
```

Passed Encode:

```python
df_label["Passed_Encoded"] = le.fit_transform(df_label["Passed"])
```

Output:

```python
print("\nEncoded Data")

print(df_label[
    [
        "Name",
        "Gender",
        "Gender_Encoded",
        "Passed",
        "Passed_Encoded"
    ]
])
```

---

## Label Encoding Output

| Name | Gender | Gender_Encoded | Passed | Passed_Encoded |
|------|--------|---------------:|--------|---------------:|
| Pavan | Male  | 0              | Yes    | 1 |
| Kapil | Male  | 0              | No     | 0 |
| Lalit | Male  | 0              | Yes    | 1 |
| Ishan | Female| 1              | No     | 0 |

---

# Note

`fit_transform()` pehle unique values ko identify karta hai aur phir unhe numerical values me convert kar deta hai.

---

# 2) One Hot Encoding

Agar Category me **2 se zyada Unique Values** ho to One Hot Encoding use karna better hota hai.

### Example

Car Brand

```
BMW
Tata
Audi
```

One Hot Encoding ke baad:

| BMW | Tata | Audi |
|----:|-----:|-----:|
| 1    | 0   | 0 |
| 0    | 1   | 0 |
| 0    | 0   | 1 |

---

## Python Example

```python
import pandas as pd

df = pd.read_csv("cars.csv")

df_encoded = pd.get_dummies(
    df,
    columns=["City"]
)

print("One Hot Encoded Data")

print(df_encoded.head())
```

---

# कब कौन-सी Encoding Use करें?

### Label Encoding

- Binary Categories
- Yes / No
- Male / Female
- Pass / Fail

---

### One Hot Encoding

- Car Brand
- City
- Country
- Product Category

यानी जहाँ **2 से ज्यादा Categories** हों।

---

# Summary

- Machine Learning Models Text Data ko directly process nahi karte.
- Label Encoding me har Category ko ek Number diya jata hai.
- One Hot Encoding me har Category ka alag Column ban jata hai.
- Binary Data ke liye Label Encoding better hoti hai.
- Multiple Categories ke liye One Hot Encoding best hoti hai.




# Feature Scaling

Ye ek Aisi Process hai jo ki Ek same Range ke andr Saari Values Ko lake Rakh deti hai taaki hamari Machine Learning Model Confuse Na ho Bade aur Chote No. ke beech 

Feature Scaling ek Data Preprocessing technique hai jiska use sabhi Features ko **same scale** par lane ke liye kiya jata hai.

Agar kisi Feature ki values bahut badi aur kisi ki bahut chhoti ho, to Machine Learning Model confuse ho sakta hai.

Isliye sabhi Features ko ek common range me convert kiya jata hai.

---

# Example

Suppose ek Dataset me:

| Feature | Value |
|---------|------:|
| Age     | 25    |
| Salary  | 500000|

Yahan Salary ki value Age se bahut badi hai.

Model Salary ko jyada importance de sakta hai.

Is problem ko Feature Scaling solve karta hai.

---

# Types of Feature Scaling

1. Standard Scaler
2. Min-Max Scaler

---

# 1) Standard Scaler

Standard Scaler data ko is tarah transform karta hai ki:

- Mean = **0**
- Standard Deviation = **1**

---

## Syntax

```python

from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

X_scaled = scaler.fit_transform(X)
```


# 2) Min-Max Scaler

Min-Max Scaler values ko **0 se 1** ke beech convert karta hai.

Ye tab use hota hai jab hume negative values nahi chahiye.


## Syntax

```python

from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()

X_scaled = scaler.fit_transform(X)
```




# fit_transform()

`fit_transform()` do kaam karta hai.

### fit()

- Mean
- Standard Deviation
- Minimum
- Maximum

jaise required statistics calculate karta hai.



### transform()

Calculated values ki help se original data ko scale karta hai by using a Formula 

z= x-u(meu) /sigma




# Train-Test Split

Machine Learning me Dataset ko do parts me divide kiya jata hai.

- Training Data
- Testing Data

Training Data se Model seekhta hai.

Testing Data se Model ki Performance check ki jati hai.

---

## Syntax

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)

```

### Parameters

- **test_size=0.2** → 20% Data Testing ke liye.
- **0.8 (80%)** Data Training ke liye.
- **random_state=42** → Har baar same split milega.

---

# Train-Test Split (Complete Example)

Train-Test Split Machine Learning ka ek bahut important step hai.

Isme hum Dataset ko do parts me divide karte hain.

- **Training Data** → Model ko sikhane ke liye.
- **Testing Data** → Model ki Performance check karne ke liye.

```python

X=df[['Study Hours']]
y=df[['Test Scores']]

X_train,X_test,Y_train,Y_test=train_test_split(X,y,test_size=0.2,randomstate=42)

Print("Training Data")
Print(X_Train)
Print("Testing Data")
Print(X_test)
Print("Training Output")
Print(y_Train)
Print("Testing Output")
Print(y_Test)

 
# Advantages of Train-Test Split

- Overfitting ko reduce karta hai.
- Model ki Actual Performance check karne me help karta hai.
- Unseen Data par Prediction capability ko evaluate karta hai.
- Real-world Performance ka idea milta hai.

