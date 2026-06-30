# Machine Learning Using Scikit-Learn

# Mathematics

Mathematics ka bahut important role hai Data Science me.

## Uses

### 1) Model Efficiency

Model ki efficiency ko pata karne ke liye Mathematics bahut helpful hoti hai.

**Example:**

Let say ek model hai aur uski efficiency **92%** aa rahi hai.

Ab ye dekhna hai ki ye sahi hai ya galat, isko analyze karne ke liye Mathematics use karte hain.

---

### 2) Error Fix

Error ko fix karne ke liye aur model ki performance badhane ke liye Mathematics zaruri hai.

---

### 3) Companies

Badi-badi companies jaise **Meta, Google** etc. sirf copy-paste nahi karti.

Wo khud research karti hain aur Mathematics ki help se naye models develop karti hain.

---

## Conclusion

**So Mathematics is very important in Machine Learning & Data Science.**

---

# Maths for Machine Learning

## Basics

Machine Learning ke liye basic Mathematics concepts:

- Mean
- Median
- Mode
- Percentage
- Probability
- Ratios
- Basic Algebra
- Plotting (X vs Y)
- Vectors
- Standard Deviation

---

## 1) Mean

Formula:

x1+x2+x3+.....+xn/N


## 2) Median

### Case 1

Agar total values **Odd** hain to beech wali value **Median** hoti hai.

### Case 2

Agar total values **Even** hain to beech ki dono values ka sum karke **2 se divide** kar dete hain.

---

## 3) Mode

Jo value sabse jyada baar aaye, use **Mode** kehte hain.

---

# Note

Mean, Median aur Mode nikalne ke liye sabse pehle dataset ko **Ascending Order** me arrange karna chahiye.

---

## Example

Find Mean, Median & Mode

Dataset:

45, 50, 70, 70, 76, 88, 90, 99

### Step 1

Ascending Order:

45, 50, 70, 70, 76, 88, 90, 99

---

### Mean
(45+50+70+70+76+88+90+99)/8
= 73.5


---

### Median

Total Values = 8

Median Position

4th value = 70

5th value = 76


Median= 70+76/2
= 73

---

### Mode

Mode = **70**







# Where Mean, Median & Mode are Used in Machine Learning

Let say ek School/College me total **100 Students** hain.

- 95 Students = Boys
- 5 Students = Girls

Ye ek **Unbalanced Dataset** hai.

Agar hum Gender Prediction Model train karte hain is dataset par, to model jyadatar **Boys** ko predict karega kyunki dataset me boys ki quantity jyada hai.

Is case me **Mode** sabse useful hota hai kyunki Mode batata hai ki sabse jyada baar kaunsi value aa rahi hai.

---

## Mean, Median & Mode Compare

Machine Learning me hum compare karte hain:

**Actual Value vs Predicted Value**

### Formula

```
Error = Actual Value - Predicted Value
```

### Example

| Student | Actual Value | Predicted Value | Error |
|---------|-------------:|----------------:|------:|
| A | 60 | 80 | -20 |
| B | 80 | 75 | 5 |

> **Jitna kam Error hoga, utna achha Model hoga.**

---

# Outliers

Outliers wo values hoti hain jo normal data se bahut jyada ya bahut kam hoti hain.

### Example

```
[5, 10, 20, 15, 125]
```

Yahan **125** Outlier hai.

Ya

```
[100, 50, 125, 95, 5]
```

Yahan **5** Outlier hai.

Agar dataset me Outliers honge to Model galat pattern seekh sakta hai aur Error ke chances badh jate hain.

---

# 4) Percentage

Percentage ka matlab hota hai **Parts of 100**

### Formula

```
Percentage = (Part / Whole) × 100
```

### Example

Let say kisi exam me **500** me se **450** number aaye.

```
Percentage
= (450 / 500) × 100
= 90%
```

---

# 5) Ratio (अनुपात)

### Formula

```
Ratio = First Quantity / Second Quantity
```

Ya

```
First Quantity : Second Quantity
```

Ratio batata hai ki do quantities ki tulna kaise karte hain.

### Example

Ek class me

- Boys = 20
- Girls = 30

To Ratio hoga

```
20 : 30

= 2 : 3
```

Matlab har **2 Boys** par **3 Girls** hain.

---

# Accuracy

### Formula

```
Accuracy = (Correct Prediction / Total Prediction) × 100
```

---

# Precision

### Formula

```
Precision = True Positives / Total Predicted Positives
```

---

# Recall

### Formula

```
Recall = True Positives / Total Actual Positives
```

---

## Note

### Percentage

```
Percentage = (Part / Whole) × 100
```

### Ratio

```
Ratio = Part / Whole
```

---

## Example (Accuracy)

Let say ek Spam Classifier me

- Total Emails = 100
- Correct Prediction = 90
- Wrong Prediction = 10

```
Accuracy
= (90 / 100) × 100
= 90%
```

---

## Example (Precision)

Let say Model ne **20 Emails** ko Spam detect kiya.

Unme se sirf **15** actually Spam the.

```
Precision
= 15 / 20
= 0.75
= 75%
```

Matlab Model ne jitne bhi Spam Emails predict kiye unme se **75% prediction sahi the.**

# 5) Algebra

Linear Regression ka basic equation:

y = mx + b


Jahan,

- **y** = Output
- **m** = Rate of Change (Slope)
- **x** = Input / Independent Variable
- **b** = Starting Point / Intercept

---

## Example

Let say tumne ek company join ki.

- Joining Bonus = ₹1000
- Daily Salary = ₹500

```
Day 0 = 1000
Day 1 = 1500
Day 2 = 2000
Day 3 = 2500
```

Yahan,

- **y** = Final Salary (Total Output)
- **m** = 500/day (Rate of Change)
- **x** = Number of Days (Input)
- **b** = 1000 (Joining Bonus / Starting Point)

Equation:


y = mx + b


For **4 Days**:

```
y = 500 × 4 + 1000
y = 2000 + 1000
y = 3000
```

**Answer:** 4 din me ₹3000 milenge.

---

# 6) Plotting (X vs Y)

### Example

| Hours of Study (X) | Exam Marks (Y) |
|-------------------:|---------------:|
| 1 | 40 |
| 2 | 50 |
| 3 | 65 |
| 4 | 75 |
| 5 | 90 |

---

### Variables

- **X = Independent Variable**
- **Y = Dependent Variable**

**Independent Variable** wo hoti hai jise hum control karte hain.

**Dependent Variable** wo hoti hai jo Independent Variable ke basis par change hoti hai.

Example:

- Hours of Study → Independent Variable
- Exam Marks → Dependent Variable

Jitna zyada study hours badhenge, utne hi marks badhne ki possibility hogi.

---

# 7) Vectors

Vector ke paas **Magnitude (Distance)** aur **Direction** dono hote hain.

### Example

Agar hum kisi Point **A** se Point **B** tak Right Side move karte hain, to Vector hume batata hai:

- Kitni distance travel hui.
- Kis direction me move hua.

### Example

```
Weight = 60
Height = 175
```

Vector Representation:

```
[60, 175]
```

---

# 8) Standard Deviation

Standard Deviation batata hai ki data ki values **Mean** se kitni door ya kitni spread out hain.

### Low Standard Deviation

- Values Mean ke bahut paas hoti hain.
- Data me kam variation hota hai.

### High Standard Deviation

- Values Mean se kaafi door hoti hain.
- Data me zyada variation hota hai.

---

## Summary

Machine Learning me Mathematics ke important topics:

- Mean
- Median
- Mode
- Percentage
- Ratio
- Accuracy
- Precision
- Recall
- Algebra
- Plotting (X vs Y)
- Vectors
- Standard Deviation

Ye sab concepts Machine Learning Models ko samajhne, train karne aur evaluate karne ke liye bahut important hote hain.

