# Project-MMA865---Big-Data-NLP
A Natural Language Processing (NLP) project to predict whether an Amazon product review is "helpful" using text analytics, feature engineering, and ML modeling on a large-scale dataset. Completed as part of **MMA865 – Big Data Analytics** at Queen’s University.

---
## Project Overview

**Objective**:  
Predict whether a given Amazon review will be marked as helpful based on its textual content and metadata.

**Dataset**:  
- Source: [Amazon Product Reviews (1996–2018)](https://jmcauley.ucsd.edu/data/amazon/)
- Size: Over 3.14 million reviews

**Target Variable**:  
- `label = 1` (helpful), `label = 0` (not helpful)

---
## 🧰 Tech Stack

- **Platform**: Azure Databricks (All-Purpose Compute)
- **Language**: PySpark (Spark NLP)
- **Libraries**: Spark MLlib, Databricks Notebook
- **Tools**: TF-IDF, Logistic Regression, Feature Indexing, Vector Assembler

---

## 🔍 Methodology

### 🔄 Data Preprocessing
- Removed duplicates
- Converted data types (e.g., review time → datetime)
- Extracted features: review length, days since review, verified status, reviewer ID, ASIN

### 🧼 Text Processing Pipeline
1. Sentence Detector  
2. Tokenizer  
3. Normalizer  
4. Stop Words Removal  
5. Lemmatizer  
6. Finisher  

### 🏗 Feature Engineering
- One-hot encoding for categorical variables
- TF-IDF vectorization of review text
- Created a dual-pipeline: one for `reviewText`, one for `summary`

### 📈 Modeling
- **Model**: Logistic Regression
  - Parameters: `maxIter=300`, `regParam=0.01`, `elasticNetParam=0.0`
- **Split**: 80% training, 20% testing

---

## 📊 Results

| Metric        | Value   |
|---------------|---------|
| AUC           | 0.888   |
| Precision     | 0.81    |
| Recall        | 0.35    |
| F1 Score      | 0.49    |

- **Top Feature**: Review Length (strongest positive coefficient)
- **TF-IDF terms**: Most important = "try", "style", "intend"; Least = "scary", "advantage"
- Verified reviews were surprisingly **less** helpful

---

## 💡 Business Insights

- Longer, more recent reviews tend to be marked as more helpful
- Overused or generic words negatively affect helpfulness
- Helpful reviews often include specific intent or advice
- Overall product rating and verification status are weak predictors of helpfulness

---

## 💰 Cost Breakdown

| Component             | Value                |
|----------------------|----------------------|
| Duration             | 4 weeks              |
| Analysts             | 6                    |
| Analyst Hours/Day    | 3                    |
| Cost per Hour        | $50                  |
| **Total Human Cost** | **$25,200**          |
| Compute Cost         | $436.80 (Databricks) |
| **Total Cost**       | **$25,636.80**       |

---

## 📁 Repository Structure

├── 00_TeamAdelaide_Presentation.pdf # Final project presentation
├── Notebook_Link.txt # (optional) link to Databricks notebook
├── README.md # You're here!

yaml
Copy
Edit

---

## 📬 Contact

**Ishaan Sinha**  
📫 [ishaan.sinha1997@gmail.com](mailto:ishaan.sinha1997@gmail.com)  
🔗 [LinkedIn](https://ca.linkedin.com/in/ishaan-sinha-56a968167)

---
