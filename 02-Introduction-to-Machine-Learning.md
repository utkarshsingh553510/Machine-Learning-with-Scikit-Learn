 # Foundation of Machine Learning

```
Artificial Intelligence (AI)
        │
        ├── Machine Learning (ML)
        │       │
        │       └── Deep Learning (DL)
```

---

## Machine Learning ko Example se Samjho

Let say tum ek **Pizza Shop** me daily Pizza khane jaate ho.

Wahan ke employees ko pehle se pata hota hai ki tumhe kaunsa Pizza pasand hai.

Jaise hi tum shop me enter karte ho, bina puche hi tumhara favourite Pizza banana start kar dete hain.

Ye isliye hota hai kyunki unhone tumhara **old pattern** observe kiya hai.

Isi tarah Machine Learning bhi **Historical Data** aur **Patterns** ko dekhkar future me prediction karti hai.

---

## Machine Learning Definition

Machine Learning ka matlab hai ki jab Machine/Computer **Past Data** aur **Patterns** ko dekhkar khud se Smart Decision aur Prediction kare, bina har rule ko manually program kiye.

Machine Historical Data se seekhti hai.

---

## Applications of Machine Learning

- YouTube Recommendation
- E-mail Spam Classifier
- Fraud Detection in Bank

---

# AI, ML & DL

## 1) Artificial Intelligence (AI) — Phase 1

Artificial Intelligence ka matlab hai Machine ko itna intelligent banana ki wo smart decision le sake.

### Example

- Chess Playing Robot
- Smart Assistant

---

## 2) Machine Learning (ML) — Phase 2

Machine Learning me machine **Without Explicit Programming** seekhti hai.

Yahan machine ko Rules nahi diye jaate.

Machine ko **Examples (Data)** diye jaate hain aur wo unse Pattern seekhti hai.

> Machine Learning = Giving a machine memory of examples, not rules.

---

## 3) Deep Learning (DL) — Phase 3

Deep Learning Human Brain ki working ko mimic karne ki koshish karta hai.

Ye Mathematics aur Neural Networks ki help se kaam karta hai.

Features:

- Huge Data par kaam karta hai.
- High Computing Power ki requirement hoti hai.
- Complex Problems solve kar sakta hai.

---

# AI vs ML vs DL

| Role | Meaning |
|------|---------|
| AI | Pura School |
| ML | Classroom |
| DL | Ek Student jo cheezein seekh raha hai |

---

# Scikit-Learn ki Help se Kya-Kya Bana Sakte Hain?

- Student Pass / Fail Prediction
- House Price Prediction
- Disease Prediction
- Search Recommendation
- Spam Detection
- Recommendation System

---

# Machine Learning Kaise Padhein?

1. Feel it (Concept ko visualize karo.)
2. Story ya Formula se samjho.
3. Slowly-Slowly Basic se Advance ki taraf badho.

```
Basic  →  Intermediate  →  Advanced
```




# Types of Machine Learning

Machine Learning ko mainly **4 types** me divide kiya jata hai:

1. Supervised Learning
2. Unsupervised Learning
3. Reinforcement Learning
4. Semi-Supervised Learning

---

# Machine Learning

```
Machine Learning
│
├── Supervised Learning
│   ├── Classification
│   │   ├── Logistic Regression
│   │   ├── Decision Tree
│   │   ├── KNN
│   │   └── Naive Bayes and SVM 
│   │
│   └── Regression
│       ├── Linear Regression, Lasso Regression 
│       ├── Decision Tree Regression
│       └── Random Forest Regression
│
├── Unsupervised Learning
│   ├── Clustering
│   │   ├── K-Means
│   │   ├── Hierarchical Clustering
│   │   └── Mean-Shift Clustering, Gaussian Mixture  
│   │
│   └── Association
│
├── Reinforcement Learning
│   ├── Q-Learning
│   ├── R-Learning
│   └── TD-Learning
│
└── Semi-Supervised Learning
```

---

# 1) Supervised Learning

## Definition

Supervised Learning ek Machine Learning technique hai jisme machine ko **Labelled Dataset** diya jata hai.

Machine input aur output dono ko dekhkar pattern seekhti hai aur future data ke liye prediction karti hai.

it is just like a Techer or Guide Who Helps you To Learn 

---

## Example

Maan lo hume ek Machine ko **Cat** aur **Bird** ki images dikhani hain.

- Cat image → Cat label
- Bird image → Bird label

Machine in labelled images ko dekhkar pattern seekh leti hai.

Agar baad me koi nayi image di jaye to machine usse automatically predict kar legi ki wo Cat hai ya Bird.

Agar machine galat prediction karti hai to hum usse feedback dete hain aur model ko improve karte hain.

Isliye ise **Supervised Learning** kaha jata hai kyunki machine ko supervision (guide) milta hai.

---

# Classification

Classification me Supervised Learning Technique hai jisme labelled data ki help se data ko alag-alag categories me divide karti hai.

### Examples

- Email Spam Detection
- Medical Diagnosis (Diabetic / Non-Diabetic)
- Image Recognition (Cat / Dog)

---

## Types of Classification

### 1. Binary Classification

Sirf **2 classes** hoti hain.

Examples:

- Yes / No
- 0 / 1
- Spam / Not Spam

---

### 2. Multi-Class Classification

2 se jyada classes hoti hain.

Example:

```
Fruit → Apple, Banana, Mango
```

---

### 3. Multi-Label Classification

Ek hi data ko ek se jyada labels diye ja sakte hain.

Example:

Ek Movie ko ek saath

- Action
- Comedy
- Romance

teeno labels mil sakte hain.

---

# Regression

let say hamare Pass Multiple Variable Hai To unke beech ke Relation ko Understand krna and Unke Basis pr kuch prediction krna Yhi kaam hota Regression ka 

Regression tab use hota hai jab hume **Continuous / Numerical Values** predict karni hoti hain.

Ye quantitative data ke basis par prediction karta hai.

### Examples

- House Price Prediction
- Height Prediction
- Weight Prediction
- Salary Prediction

Regression me variables continuous hote hain.

Example:

```
Height = 6 Feet
Weight = 100 Kg
```

Ye dono continuous variables hain.


# 2) Unsupervised Learning

## Definition

Unsupervised Learning ek Machine Learning technique hai jisme machine ko **Unlabelled Dataset** diya jata hai.

Yahan data ke saath koi **label** ya **correct answer** nahi hota.

Machine khud hi data me **similarity**, **patterns** aur **relationships** ko find karti hai.

it is just like exploring a new city without any Guide or Map 

---

## Features

- Unlabelled Data use hota hai.
- Koi Teacher ya Guide nahi hota.
- Machine khud Pattern discover karti hai.
- Classification ya Labels pehle se available nahi hote.

---

## Example

Maan lo machine ko alag-alag **Marbles** ki images de di.

Machine ko nahi bataya gaya ki kaunsa marble kis category ka hai.

Machine khud hi:

- Same Color wale ek group me
- Same Size wale dusre group me
- Same Shape wale teesre group me

divide kar degi. iss process ko hum Clustering Kehte hai and Division ke baad Jo Groups bante hai Unhe Hum Clusters Kehte hai 

Yahi Unsupervised Learning hai.

---

# Clustering

Clustering ka matlab hai **Similar Data ko ek group (Cluster) me divide karna.**

Machine Unlabelled Data me similarity find karti hai aur uske basis par groups bana deti hai.

jab hum machine ko unlabled data dete hai to machine inn Unlabled data ko similarity ke basis pr alag alag groups me Divide kr deti hai and isi Process ko hum Clustering kehte hai and division ke baad jo groups bane hai us ehum Clusters Kehte hai 


## Example

Different Fruits

```
🍎 🍌 🍎 🍊 🍌 🍇 🍊
        ↓
     Machine
        ↓

Cluster 1 → 🍎 🍎
Cluster 2 → 🍌 🍌
Cluster 3 → 🍊 🍊
Cluster 4 → 🍇
```

---

# Association

Association ka use ye jaanne ke liye hota hai ki **kaunsi cheezein ek saath purchase ya occur hone ki probability rakhti hain.**

it means agar X hai to Y hone ki Probability kya hai 

## Example

Agar customer **Milk** kharidta hai to uske saath **Bread** kharidne ki probability bhi high hoti hai.

Market Basket Analysis isi concept par based hota hai.

---

# 3) Reinforcement Learning

## Definition

Reinforcement Learning me Machine **Trial and Error** ke through seekhti hai.

Machine apne actions ke basis par **Reward** ya **Punishment** receive karti hai.

Jis action par Reward milta hai usse repeat karti hai.

Jis action par Punishment milta hai usse avoid karti hai.

it is Just Like Children LEarning New Behaviour and Skills 
---

## Example

Maan lo hum ek Robot ko chalna sikha rahe hain.

- Sahi step → Reward (+)
- Galat step → Punishment (-)

Dheere-dheere Robot sahi actions ko seekh leta hai aur apni performance improve karta hai.

---

## Types of Reinforcement

- **Positive Reinforcement** → Reward
- **Negative Reinforcement** → Punishment

---

# 4) Semi-Supervised Learning

## Definition

Semi-Supervised Learning, **Supervised Learning** aur **Unsupervised Learning** ka combination hai.

Isme:

- Kuch Data **Labelled** hota hai.
- Baaki Data **Unlabelled** hota hai.

Machine dono ka use karke better prediction karti hai.

---

## Example

Maan lo tumhare paas **1000 Emails** hain.

- 100 Emails Labelled hain (Spam / Not Spam)
- 900 Emails Unlabelled hain.

Machine pehle labelled data se seekhti hai, phir unlabelled data me pattern find karti hai aur apni accuracy improve karti hai.

---

# Core ML Concepts

## 1) Input (X) & Output (Y)

### Example

| Study Hours (X) | Score (Y) |
|----------------:|----------:|
| 1                   50      |
| 2                   60      |
| 3                   70      |

Machine in values ka pattern seekhti hai.

Agar hum puchhe:

> **4 Hours padhne par kitne marks aayenge?**

To Machine automatically prediction kar degi.

Example:

```
4 Hours → 80 Marks (Prediction)
```

> **Note:**
>
> - **X = Input / Independent Variable/ X Hamesha Capital Rhega**
> - **Y = Output / Dependent Variable / y always Small letters me hoga**




# 2) Model

Model Machine Learning ka **brain** hota hai.

Model Ek Mathematical Function ya Formula ya Logic hota hai Jo ki Computers/Machine ko Prediction krne me madad krta hai 

Ye input data se patterns seekhta hai aur us pattern ke basis par future predictions karta hai.

### Example

House Price Prediction

| Area (sq.ft.) | Price (₹) |
|--------------:|----------:|
| 1000          | 20,00,000 |
| 1200          | 24,00,000 |
| 1500          | 30,00,000 |
| 1800          | 36,00,000 |

Machine in examples ko dekhkar ek **Model** banati hai.

Agar hum naya input dein:

```
Area = 2000 sq.ft.
```

To Model prediction karega:

```
Predicted Price ≈ ₹40,00,000
```

---

# 3) Training

Training ka matlab hai Machine ko **Historical Data** dekar sikhana.

Is phase me Machine:

- Data ko padhti hai.
- Patterns identify karti hai.
- Relationship samajhti hai.
- Model create karti hai.

### Example

Teacher student ko bahut saare questions practice karwata hai.

Waise hi Machine bhi bahut saara data dekhkar seekhti hai.

---

# 4) Testing

Testing ka matlab hai Machine ko **naya data** dena jo usne pehle kabhi nahi dekha.

Isse pata chalta hai ki Model kitna achha perform kar raha hai.

### Example

Training ke baad Teacher exam leta hai.

Exam me naye questions aate hain.

Waise hi Machine Learning me Testing Data diya jata hai.

---

# 5) Prediction

Prediction ka matlab hai naye input ke liye output batana.

### Example

Training Data

| Hours Studied | Marks |
|--------------:|------:|
| 2             | 40 |
| 4             | 60 |
| 6             | 80 |

Machine pattern seekh leti hai.

Ab agar input diya jaye:

```
Hours = 5
```

Prediction:

```
Marks ≈ 70
```

---

# Machine Learning Workflow

```
Data Collection
        │
        ▼
Data Cleaning
        │
        ▼
Training
        │
        ▼
Model
        │
        ▼
Testing
        │
        ▼
Prediction