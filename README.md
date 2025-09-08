
# 🔍 Project 7: Recommendation System with PySpark

This project implements a recommendation system for a **movie and series streaming platform** using the **Alternating Least Squares (ALS)** algorithm with **Apache Spark** (via **PySpark**), focused on offering personalized recommendations based on user rating data.

## 📌 Objective

Develop a scalable recommendation system using **PySpark**, based on the **ALS (Alternating Least Squares)** algorithm, capable of predicting affinity between users and items. The project includes an interactive web interface for testing and demonstrations, built with the **Gradio** library.

---

## 🚀 Technologies Used

- `PySpark`
- `ALS (Alternating Least Squares)`
- `Gradio` (web interface)
- `Pandas`
- `Matplotlib`
- `Google Colab / SparkSession`

---

## 🛠️ Project Stages

### 1. 📦 Import and Initial Setup
- Configuration of SparkSession
- Loading essential libraries

### 2. 🧼 Data Preprocessing
- Reading the ratings dataset (user, item, rating)
- Conversion to `Spark DataFrame`

### 3. 🤖 ALS Model Training and Results 🔍

- **Algorithm used:** ALS (Alternating Least Squares)
- **Number of observations:** ~100,000 records
- **Train/test split:** 80% / 20%
- **Best hyperparameters found via Cross-Validation:**
  - Rank: 40
  - MaxIter: 10
  - RegParam: 0.05
- **Mean error (RMSE) on test set:** 3.61

🔧 📈 The model achieved an RMSE of 3.61, considering a rating scale from 1 to 10.  
This error indicates intermediate performance, with room for some improvements.  
Even without using additional information about users and items, ALS managed to capture relevant recommendation patterns.

---

## 💼 Estimated Financial Impact

This scalable recommendation system, developed with PySpark and ALS, processed around 100,000 ratings to offer personalized recommendations.

Considering a simulated scenario:

- **Active customer base:** 50,000  
- **Average annual revenue per customer:** R$ 2,000  
- **Current retention rate:** 70%  
- **Potential retention increase with personalized recommendations:** 12% (over the retained base)

### Impact calculation:

1. Customers currently retained:  
   50,000 × 70% = 35,000 customers

2. Additional customers retained with recommendations:  
   35,000 × 12% = 4,200 customers

3. Additional annual revenue:  
   4,200 × R$ 2,000 = **R$ 8,400,000**

---

### 4. 🎯 Recommendation Generation
- Use of the `.transform()` method to apply the model to new data
- Sorting predictions by affinity score (`prediction`)
- **Affinity Score** grouped by ID to return the customer's propensity to purchase a given item based on affinity score

### 5. 🌐 Interactive Interface
- Creation of the function `fazer_recomendacao(user_id)` to predict the items most likely to appeal
- Implementation of a `Gradio` interface
- Input: User ID
- Output: Top-N personalized recommendations

---

## 🎥 Demonstration

The interactive application allows you to enter a user's ID and get a real-time, personalized recommendation list.
![image](https://github.com/user-attachments/assets/79c11bfe-9e81-4c35-9492-eaba42436676)

---

## 🧠 Next Steps

- Add content filters based on categories
- Integration with a real database (e.g., PostgreSQL, MongoDB)
