# 🎬 Movie Recommendation System

## 📌 Problem Statement
Build a **Movie Recommendation System** that suggests movies to users based on their preferences.  
We implement a **Content-Based Filtering** approach using the TMDB dataset.  

- **Content-Based Filtering** → Recommends movies similar to a given movie using metadata (genres, keywords, overview).  
- Uses **Bag-of-Words (CountVectorizer)** + **Cosine Similarity** to measure closeness between movies.  

---

## 📊 Dataset
- Dataset: [TMDB 5000 Movies Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)  
- File used: `tmdb_5000_movies.csv`  
- Features considered: `title`, `overview`, `genres`, `keywords`

---

## ⚙️ Steps in the Code
1. **Import Libraries** → pandas, sklearn (CountVectorizer, cosine_similarity).  
2. **Load Dataset** → Load `tmdb_5000_movies.csv`.  
3. **Preprocessing** →  
   - Select required columns: `id`, `title`, `overview`, `genres`, `keywords`.  
   - Handle missing values (`NaN → ""`).  
   - Merge text columns into a new feature `tags`.  
4. **Vectorization** → Convert `tags` into numerical vectors using **CountVectorizer**.  
5. **Similarity Matrix** → Use **Cosine Similarity** to calculate closeness between all movies.  
6. **Recommendation Function** →  
   - Input: a movie title.  
   - Find similarity scores with all movies.  
   - Sort movies by similarity (highest first).  
   - Skip the same movie (score = 1).  
   - Return **Top 5 Recommended Movies**.  
7. **Demonstration** → Tested with movies like *Avatar*, *The Dark Knight*, *Inception*, *Pirates of the Caribbean: At World's End*, *The Lion King*, *Titanic*.  

---

## 🧑‍💻 Code Usage
```python
# Run the recommender
recommend("Avatar")
recommend("The Dark Knight")
recommend("Inception")
recommend("Pirates of the Caribbean: At World's End")
recommend("The Lion King")
recommend("Titanic")
