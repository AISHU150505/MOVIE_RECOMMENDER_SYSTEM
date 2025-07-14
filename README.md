# 🎬 Movie Recommendation System using Apriori Algorithm

A data mining project that implements a movie recommendation engine using the **Apriori algorithm** and **Association Rule Mining (ARM)**. The system analyzes user-movie interactions from the Netflix Prize Dataset to suggest personalized movie recommendations, with enhancements through a hybrid model that combines **Collaborative Filtering** and **Apriori-based rules**.

---

## Project Overview

This project addresses the challenge of overwhelming movie choices by providing intelligent, data-driven, and personalized recommendations. It explores:

- Data preprocessing and sparse matrix creation  
- Frequent itemset mining using Apriori  
- Association rule generation  
- A hybrid approach combining ARM with collaborative filtering  
- Performance comparison with FP-Growth algorithm  

---

## Objectives

- 🧹 Clean and preprocess large-scale movie rating data  
- 🔍 Extract frequent itemsets (L1, L2, L3) with Apriori  
- 📊 Generate association rules based on support, confidence, and lift  
- 🎥 Recommend relevant movies based on user history  
- ♻️ Build a hybrid recommender combining Apriori and Collaborative Filtering  

---

##  Modules

1. **Data Preprocessing** – Clean missing values, remove duplicates, and prepare ratings  
2. **Binary Matrix Generation** – Convert ratings into a user-movie binary sparse matrix  
3. **Frequent Itemset Mining** – Generate L1, L2, L3 using Apriori  
4. **Association Rule Generation** – Compute support, confidence, lift  
5. **Recommendation Engine** – Generate personalized movie suggestions  
6. **Hybrid System** – Combine Collaborative Filtering and ARM for better results  
7. **FP-Growth Implementation** – Alternative to Apriori for faster performance on large data  

---

## Dataset

- **Netflix Prize Dataset** (~2GB)
- 100M+ ratings | 480K+ users | 17,770 movies
- Link: [Netflix Prize Data](https://www.kaggle.com/datasets/netflix-inc/netflix-prize-data)

Files used:
- `combined_data_*.txt`: Rating data
- `movie_titles.csv`: Metadata about movies
- `qualifying.txt`: Prediction challenge data

---

### Dataset Access

Due to GitHub’s file size restrictions, the full Netflix Prize dataset used in this project is **not included** in this repository.

👉 **Download the dataset directly from Kaggle**:  
🔗 [Netflix Prize Data on Kaggle](https://www.kaggle.com/datasets/netflix-inc/netflix-prize-data)

Once downloaded, place the following files inside a `Dataset/` directory in the root of the project:

- `combined_data_1.txt`
- `combined_data_2.txt`
- `combined_data_3.txt`
- `combined_data_4.txt`
- `movie_titles.csv`
- *(Optional)* `qualifying.txt` for rating prediction

---

### 🛠 File Organization Tip

```
DATA_MINING_PROJECT/
├── Dataset/
│   ├── combined_data_1.txt
│   ├── combined_data_2.txt
│   ├── combined_data_3.txt
│   ├── combined_data_4.txt
│   └── movie_titles.csv
├── MAIN_FILE/
├── README.md
└── ...
```

---

## Metrics Used

- **Support** – Frequency of itemset in dataset  
- **Confidence** – Likelihood of B given A  
- **Lift** – Strength of A ⇒ B over random chance  
- **Conviction & Leverage** – Measure rule quality  

---

## Output Files

- `data.csv` – Cleaned and preprocessed ratings  
- `merged.csv` – Ratings + movie titles merged  
- `filtered_association_rules.csv` – Final rule set  
- `recommendations.csv` – Generated movie recommendations  

---

## Results

- Improved movie recommendations based on mined patterns
- Hybrid system enhanced personalization and scalability
- FP-Growth proved more efficient on larger itemsets

---

## Conclusion

The system accurately predicts user preferences by mining frequent movie patterns and combining them with collaborative scores. This dual-strategy approach significantly enhances recommendation quality and system efficiency.

---

## 👩‍💻 Authors

- Aishwarya S 
- Sujana S  
Department of Computer Science and Engineering, College of Engineering, Guindy, Anna University  

---


---

## Accuracy Metrics Explained

Understanding the effectiveness of the generated association rules and recommendations requires rigorous evaluation using multiple metrics:

### 1. **Support**
- Indicates how frequently an itemset appears in the dataset.
- Helps in identifying popular item combinations.
- **Formula**:  
  **Support(A ⇒ B)** = (Number of transactions containing both A and B) ÷ (Total number of transactions)

### 2. **Confidence**
- Measures the likelihood of item B being purchased/viewed when item A is.
- High confidence implies strong association between A and B.
- **Formula**:  
  **Confidence(A ⇒ B)** = Support(A ∪ B) ÷ Support(A)

### 3. **Lift**
- Quantifies the strength of a rule over random co-occurrence.
- Lift > 1 implies a positive association between A and B.
- **Formula**:  
  **Lift(A ⇒ B)** = Confidence(A ⇒ B) ÷ Support(B)

### 4. **Conviction**
- Measures the degree of implication of A ⇒ B.
- A higher conviction value means stronger implication.
- **Formula**:  
  **Conviction(A ⇒ B)** = (1 − Support(B)) ÷ (1 − Confidence(A ⇒ B))

### 5. **Leverage**
- Measures the difference between observed and expected frequency of A and B appearing together.
- Leverage = 0 means no correlation; > 0 implies a positive correlation.
- **Formula**:  
  **Leverage(A, B)** = Support(A ∪ B) − (Support(A) × Support(B))

These metrics were crucial in filtering and selecting only the strongest and most meaningful rules for our final recommendation engine.