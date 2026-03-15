# Movie Recommendation System (Content-Based) 🎬🤖

This project implements a recommendation engine using the TMDB 5000 Movies dataset. It uses Natural Language Processing (NLP) to recommend movies based on their metadata and calculates a weighted rating score to rank the top-rated films.

## 🚀 Project Highlights
* **Hybrid Ranking:** Implemented the **IMDB Weighted Rating** formula to provide a fair score for movies with varying vote counts.
* **Metadata Soup:** Combined `Director`, `Top 3 Cast members`, `Genres`, and `Keywords` into a single string to capture the essence of each movie.
* **Similarity Engine:** Used **CountVectorizer** and **Cosine Similarity** to measure the distance between movies in a multi-dimensional feature space.
* **Data Persistence:** Optimized storage by saving the similarity matrix and dataframes using **Pickle with Gzip compression**.

## 🛠️ Tech Stack
* **Python**
* **Pandas & NumPy** (Data Processing)
* **Scikit-learn** (Feature Extraction & Similarity)
* **Matplotlib** (Data Visualization)
* **AST (Abstract Syntax Trees):** To safely evaluate stringified literal lists in the dataset.

## 🏗️ How it Works
1. **Weighted Rating Chart:**
   To avoid bias toward movies with very few votes but high averages, I used the formula:
   $$W = (\frac{v}{v+m} \cdot R) + (\frac{m}{v+m} \cdot C)$$
   *Where $v$ is vote count, $m$ is minimum votes required, $R$ is average rating, and $C$ is the mean vote across the whole report.*

2. **Content-Based Filtering:**
   * **Preprocessing:** Cleaned data by converting to lowercase and removing spaces (e.g., "Johnny Depp" becomes "johnnydepp") so the vectorizer treats full names as unique entities.
   * **Vectorization:** Converted the "Metadata Soup" into a word count matrix.
   * **Similarity:** Calculated the cosine of the angle between vectors to determine how "close" two movies are based on their content.

[Image of Content-based filtering vs Collaborative filtering]

## 📊 Top 10 Recommendations (Metadata-Based)
When searching for a movie like **"Gandhi"**, the system identifies other historical dramas and biographies:
1. *A Bridge Too Far*
2. *Schindler's List*
3. *The Great Escape*
4. *The Conspirator*
5. ...and more.

## 📈 Visualizations
The project includes horizontal bar charts to visualize:
* **Popular Movies:** Based on the TMDB popularity metric.
* **High Budget Movies:** Comparing financial investments.
* **Revenue Leaders:** Identifying the highest-grossing films in the dataset.

## ⚙️ Installation & Usage
1. **Clone the repo:**
   ```bash
   git clone
