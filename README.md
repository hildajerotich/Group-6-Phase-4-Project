# 🎬 Movie Recommender System

##  Project Overview

This project focuses on building a **movie recommender system** using the **MovieLens dataset (100K)**.  
The dataset contains **100,000 ratings** given by **610 individual users** for **9,724 individual movies**.  

The aim is to **recommend the top 5 movies** to users based on their ratings through **collaborative filtering**.  
This project aims towards solving the **business problem of personalized movie recommendations**, which allows users find relevant movies with ease, thus and increasing user engagement.

---

##  Data Science Workflow

### 1. Business Understanding

- Problem: Users find it difficult to find movies aligned with their preferences.

- Goal: Build a system that recommends **personalized top 5 movies** to each user.  

### 2. Data Understanding
- **Source:** [MovieLens Dataset (100K)]  https://grouplens.org/datasets/movielens/latest/


The dataset contains 4 csv files:
 1. **Movies Data (movies.csv)**:
Contains movie information, including titles and genres.
2. **Links Data (links.csv)**:
Provides identifiers for linking to external movie-related sources (IMDb, TMDb).
3. **Ratings Data (ratings.csv)**:
Each entry represents a user's rating for a specific movie.
Contains user ratings on a 5-star scale for movies.
4. **Tags Data (tags.csv)**:
Contains user-generated metadata (tags) about movies.

- **Features retained:**  
  - 'userId' – Unique user identifier  
  - 'movieId' – Unique movie identifier  
  - 'title' – Movie name  
  - 'genres' – Genres associated with the movie  
  - 'rating' – User rating (1–5)  
  - 'rating year' – Year when the rating was given between(1996-2018)  

### 3. Data Preparation
- Dropped duplicate identifiers.  
- Merged multiple files ('ratings', 'movies', 'links', 'tags').  
- Imputed missing values with **zeros** to ensure complete representation of users and movies in the user interaction matrix.
- Encoded categorical features using **LabelEncoder**.
- Scaled data for **model stability**.

- **Libraries used:** 'pandas', 'numpy','matplotlib', 'scikit-learn' ('SimpleImputer', 'StandardScaler', 'Pipeline','TruncatedSVD', 'ridge','GridSearchCV').  

### 4. Modeling
- **Collaborative filtering via Matrix Factorization**.  
- Implemented a **Pipeline** with:  
  - **TruncatedSVD** → Dimensionality reduction (latent factor extraction).  
  - **Ridge Regression** → Predicting ratings from latent features.  
- Hyperparameters tuned using **GridSearchCV** with 5-fold cross-validation.  

### 5. Evaluation
- **Train-test split** and **cross-validation** applied.  
- Best model achieved:  
  - **RMSE:** '3.29'  

---

## ✅ Conclusion
Our recommender system shows that **collaborative filtering with matrix factorization** can generate useful and personalized movie suggestions.  
By leveraging **user ratings** and **key metadata**, the model achieved good accuracy with an **RMSE of 3.29**, meaning most recommendations aligned with user interests.  

However, to improve the model, future work should explore:  
- **Hybrid approaches** (combining collaborative and content-based filtering).  
- **Time-awareness** (capturing evolving user preferences).  
- **Diversity in recommendations** (reducing repetitive suggestions).  

Overall, this project provides a **strong baseline** for a movie recommendation engine and a **foundation for more advanced systems.



##  How to Run the Project 
To run this repository and run the project, follow these steps:

### 1. How to navigate the Repository
 - Start with README.md for the project overview.

 - Explore notebooks/ for exploratory analysis and model development.

 - Review presentation/ for a concise, stakeholder-friendly summary.

 - Clone the Repository.

### 2. Clone the Repository
```bash
git clone https://github.com/hildajerotich/Group-6-Phase-4-Project.git
cd movie-recommender-system 
```
## Contributors
- Hilda Jerotich
- Erick Kibugi
- Barnice Wandeto
- Alice Muia
- David Muriithi
- Boniface Njeri