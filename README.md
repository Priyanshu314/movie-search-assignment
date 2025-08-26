# Movie Semantic Search Assignment

This repository contains my solution for **Assignment-1: Semantic Search on Movie Plots** using SentenceTransformers (`all-MiniLM-L6-v2`).  
The goal is to build a semantic search engine that retrieves the most relevant movies based on a text query.

---

## 📌 Objective
- Load and process the `movies.csv` dataset.
- Generate embeddings using `all-MiniLM-L6-v2`.
- Implement `search_movies(query, top_n)` to return top results ranked by cosine similarity.
- Verify correctness using unit tests.

---

## ⚙️ Setup Instructions
1. Clone this repository:
   ```bash
   git clone https://github.com/Priyanshu314/movie-search-assignment.git
   cd movie-search-assignment
   ```

2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   # On Windows
   venv\Scripts\activate
   # On macOS/Linux
   source venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the Jupyter notebook:
   ```bash
   jupyter notebook movie_search_solution.ipynb
   ```

---

## 🧪 Testing
Run unit tests to ensure correctness:
```bash
python -m unittest tests/test_movie_search.py -v
Output : 
(venv) PS C:\Users\sriva\Desktop\movie-search-assignment\Assignment-1> python -m unittest tests/test_movie_search.py -v
Loaded 3 movies and created embeddings with shape: (3, 384)
test_search_movies_output_format (tests.test_movie_search.TestMovieSearch.test_search_movies_output_format)
Test if search_movies returns a DataFrame with correct columns. ... ok
test_search_movies_relevance (tests.test_movie_search.TestMovieSearch.test_search_movies_relevance)
Test if returned movies are relevant to the query. ... ok
test_search_movies_similarity_range (tests.test_movie_search.TestMovieSearch.test_search_movies_similarity_range)
Test if similarity scores are between 0 and 1. ... ok
test_search_movies_top_n (tests.test_movie_search.TestMovieSearch.test_search_movies_top_n)
Test if search_movies returns the correct number of results. ... ok

----------------------------------------------------------------------
Ran 4 tests in 3.176s
```

---

## 🚀 Usage
Example query:
```python
from movie_search import search_movies
results = search_movies("spy thriller in Paris", top_n=5)
print(results)

Output :
(venv) PS C:\Users\sriva\Desktop\movie-search-assignment\Assignment-1> python movie_search.py
Loaded 3 movies and created embeddings with shape: (3, 384)

Testing search with query: 'spy thriller in Paris'

Top 3 results:
              title                                               plot  similarity
0         Spy Movie  A spy navigates intrigue in Paris to stop a te...    0.769684
1  Romance in Paris  A couple falls in love in Paris under romantic...    0.388029
2      Action Flick  A high-octane chase through New York with expl...    0.256777
```

---

## 📂 Repository Structure
```
movie-search-assignment/
├── tests/test_movie_search.py   # Unit tests
├── movie_search.py              # Main Python module
├── movie_search_solution.ipynb  # Jupyter notebook
├── movies.csv                   # Dataset
├── requirements.txt             # Dependencies
├── README.md                    # Documentation
└── .gitignore                   # Ignore unnecessary files
```

---

## ✅ Notes
- All unit tests pass locally.  
- Built using Python 3.9+, Jupyter, and SentenceTransformers.  
- Developed as part of **AI Systems Development (IIIT Naya Raipur)**.

---
