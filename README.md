# Content-Based Movie Recommendation System Using Embedding

## Overview
This project is a Content-Based Movie Recommendation System that suggests movies based on user preferences. It leverages BERT embeddings, Principal Component Analysis (PCA), and k-nearest neighbors (KNN) with cosine similarity for accurate recommendations.


## Features
- **Overview Embeddings**: Extracts numerical representations of movie overviews.
- **PCA Dimensionality Reduction**: Reduces embeddings to optimize performance.
- **Genre One-Hot Encoding**: Converts genres into numerical form.
- **KNN for Recommendations**: Uses cosine similarity to find the most relevant movies.
- **Filtering Liked Movies**: Ensures previously liked movies are not recommended again.
- **Cold Start Problem Handling**: Implements strategies to recommend movies even when data is sparse.

## Installation

 Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Preprocess Movie Data**
   - Load movie data (ID, name, genre, overview, etc.).
   - Generate embeddings for movie overviews.
   - Apply PCA for dimensionality reduction.
   - One-hot encode genres and combine with reduced embeddings.

2. **Generate User Profile**
   - Compute user preference embeddings based on liked movies.

3. **Find Similar Movies**
   - Fit a KNN model with movie embeddings.
   - Retrieve similar movies based on user preferences.
   - Filter out already liked movies from recommendations.

4. **Addressing Cold Start Problem**
   For users with few liked movies, the system recommends movies by:

    - Expanding Similarity Search: Finding recommendations using broader content-based filtering based on available preferences.
    - Genre-Based Recommendations: Suggesting movies from genres matching the user's limited preferences.
    - Adjusting KNN Sensitivity: Lowering similarity thresholds to include more diverse yet relevant recommendations.
    - Popular Choices as Backup: If insufficient data exists, suggesting highly-rated or trending movies within the user's preferred genres.



## Dependencies
- Python 3.8+
- NumPy
- Pandas
- Scikit-learn
- PyTorch (for embeddings)


