# 📚 Book Recommendation System

A simple **content-based book recommendation system** built with Python, TF-IDF, and K-Nearest Neighbors (KNN). This project also includes exploratory data analysis (EDA) and visualizations of book ratings and popularity.

## Project Overview

The project uses book titles and author names to recommend similar books. It does not use reader profiles, book descriptions, or genres, so recommendations are based on **metadata similarity**, not personal reading preferences.

## Objectives

- Explore and understand a book dataset.
- Visualize rating distributions and the top-rated popular books.
- Identify highly rated books with at least 1,000 ratings.
- Build a content-based recommendation system using TF-IDF and Nearest Neighbors.
- Display recommendations with cosine similarity scores.

## Dataset

The project reads `books.csv`. The notebook uses these columns:

| Column | Description |
|---|---|
| `bookID` | Book identifier |
| `title` | Book title |
| `authors` | Author(s) |
| `average_rating` | Average reader rating |
| `ratings_count` | Number of reader ratings |
| `language_code` | Book language code (used in the data overview) |

Some rows in the source CSV may be malformed; the notebook uses `on_bad_lines='skip'`, so such rows may be omitted. Verify the original dataset's license before redistributing it.

## Workflow

1. Import libraries and load the dataset.
2. Inspect data types, missing values, and summary statistics.
3. Visualize the distribution of average ratings and rating counts.
4. List the top-rated books with at least 1,000 ratings.
5. Combine lowercase titles and author names into text features.
6. Convert text to TF-IDF vectors.
7. Fit a Nearest Neighbors model using cosine distance.
8. Recommend similar books and display cosine similarity scores.
9. Run basic checks for output size, unique titles, and unknown queries.

## Example

```python
recommend_books('The Hobbit')
recommend_books('Harry Potter and the Half-Blood Prince')
```

Each result includes a book title, author, average rating, and **similarity_score**. The similarity score measures textual overlap in the chosen features; it is **not** a prediction of whether a reader will enjoy the book.

## Limitations and Future Work

- Recommendations often favor the same author or book series.
- Different editions with variant titles may still appear.
- The dataset has no descriptions, genres, or user-book interaction history.
- Accuracy or recommendation relevance has not been validated with reader feedback or labeled evaluation data.

Potential improvements include genre/description features, title normalization, and evaluation using relevant book pairs or user interactions.

## Tech Stack

Python, pandas, NumPy, Matplotlib, scikit-learn, Jupyter Notebook
