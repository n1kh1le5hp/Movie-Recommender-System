# Movie Recommender System

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=yellow)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-purple?logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0%2B-orange?logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-1.24%2B-green?logo=numpy&logoColor=white)

An intelligent content-based movie recommendation system using machine learning and natural language processing techniques.

---

## Overview

This project builds a movie recommendation engine that suggests similar movies based on content analysis. The system analyzes multiple features of movies including genres, keywords, plot overview, cast, and crew to provide personalized recommendations using cosine similarity and TF-IDF vectorization.

## Features

- **Content-Based Filtering**: Recommends movies based on content similarity
- **Multi-Feature Analysis**: Combines genres, keywords, overview, cast, and crew data
- **Text Preprocessing**: Advanced NLP techniques for feature extraction
- **Scalable Architecture**: Efficient vectorization and similarity computation
- **Interactive Recommendations**: Real-time movie suggestions

## How It Works

### 1. Data Collection & Integration
- Merges TMDB movie metadata (5,000 movies)
- Combines movie credits and movie details datasets
- Extracts relevant features for recommendation

### 2. Feature Engineering
```python
# Tags created from:
- Movie Genres (Action, Adventure, etc.)
- Keywords (culture clash, future, space war, etc.)
- Plot Overview (textual description)
- Cast Members (top 3 actors)
- Crew/Director information
```

### 3. Text Preprocessing
- **Text Cleaning**: Removes spaces and special characters
- **Lowercase Conversion**: Standardizes text for consistency
- **Tokenization**: Converts text to word tokens
- **Stop Words Removal**: Filters common English words

### 4. Vectorization & Similarity
- **CountVectorizer**: Converts text to numerical features
- **TF-IDF**: Term Frequency-Inverse Document Frequency weighting
- **Cosine Similarity**: Measures similarity between movies
- **Top-K Recommendations**: Returns 5 most similar movies

## Dataset

**Source**: TMDB (The Movie Database)
- **Movies**: 5,000 movies with comprehensive metadata
- **Features**: 23 columns including budget, revenue, genres, keywords, etc.
- **Credits**: Cast and crew information for each movie

## Algorithm & Techniques

### Content-Based Filtering
```
Input Movie → Feature Extraction → Vectorization → Similarity Calculation → Top Recommendations
```

### Similarity Metrics
- **Cosine Similarity**: Measures cosine of angle between vectors
- **Feature Weights**: Equal importance to all features
- **Top-5 Selection**: Highest similarity scores

## Technical Stack

| Component | Technology |
|-----------|--------------|
| **Language** | Python 3.8+ |
| **Data Processing** | Pandas, NumPy |
| **Machine Learning** | Scikit-learn |
| **Text Processing** | CountVectorizer, Cosine Similarity |
| **Serialization** | Pickle |
| **Development** | Jupyter Notebooks |

## Installation

### Prerequisites
```bash
pip install numpy pandas scikit-learn
```

### Setup
1. Clone the repository:
```bash
git clone https://github.com/n1kh1le5hp/Movie-Recommender-System.git
cd Movie-Recommender-System
```

2. Download datasets:
- `tmdb_5000_movies.csv` (5.7MB)
- `tmdb_5000_credits.csv` (40MB)

3. Run the notebook:
```bash
jupyter notebook MovieRecommender.ipynb
```

## Usage

### Basic Recommendation
```python
def recommend(movie):
    index = new[new['title'] == movie].index[0]
    distances = sorted(list(enumerate(similarity[index])), 
                       reverse=True, key=lambda x: x[1])
    for i in distances[1:6]:
        print(new.iloc[i[0]].title)

# Example
recommend('The Dark Knight')
```

### Example Output
```
Input: The Dark Knight Rises
Recommendations:
1. The Dark Knight
2. Batman Begins
3. Batman
4. Batman Returns
5. Batman Forever
```

## Project Structure

```
Movie-Recommender-System/
├── MovieRecommender.ipynb      # Main implementation notebook
├── README.md                    # Project documentation
├── .gitignore                   # Git ignore rules
└── data/                       # Dataset files (not included)
    ├── tmdb_5000_movies.csv
    └── tmdb_5000_credits.csv
```

## Model Artifacts

After running the notebook, the following files are generated:
- `movie_list.pkl`: Processed movie data with tags
- `similarity.pkl`: Cosine similarity matrix

## Performance & Optimization

### Optimization Techniques
- **Max Features**: Limited to 5,000 most frequent words
- **Stop Words**: Removed English stop words for efficiency
- **Memory Management**: Efficient data structures
- **Sparse Matrices**: Used for large-scale computations

### Scalability
- Supports adding new movies to the dataset
- Can be extended with user-based collaborative filtering
- Ready for deployment as a web service

## Future Enhancements

- [ ] Web interface for interactive recommendations
- [ ] User preference integration
- [ ] Collaborative filtering implementation
- [ ] Movie posters and trailers integration
- [ ] Genre-based filtering options
- [ ] Rating-based weighted recommendations

## Key Learnings

Through this project, I gained expertise in:

1. **Content-Based Filtering**: Understanding recommendation algorithms
2. **Feature Engineering**: Multi-feature combination strategies
3. **Text Processing**: NLP techniques for movie data
4. **Vectorization**: Converting text to numerical features
5. **Similarity Metrics**: Cosine similarity for recommendations
6. **Data Integration**: Merging and cleaning large datasets
7. **Model Serialization**: Saving and loading trained models

## Algorithm Complexity

- **Time Complexity**: O(n²) for similarity matrix computation
- **Space Complexity**: O(n×k) where n=movies, k=features
- **Query Time**: O(n) for single recommendation
- **Optimization**: Sparse matrices and efficient indexing

## Data Pipeline

```
Raw Data → Cleaning → Feature Extraction → Text Processing → Vectorization → Similarity Matrix → Recommendations
```

## Challenges & Solutions

### Challenge 1: Large Dataset Size
**Solution**: Used sparse matrices and limited max features

### Challenge 2: Text Preprocessing
**Solution**: Comprehensive cleaning and stop word removal

### Challenge 3: Feature Integration
**Solution**: Combined multiple features into unified tags

## Results

- **Dataset Size**: 5,000 movies
- **Feature Dimension**: 5,000 TF-IDF features
- **Recommendation Accuracy**: Contextually similar movies
- **Response Time**: <1 second per query

## Related Concepts

- **Content-Based Filtering**: Item-to-item recommendation
- **TF-IDF**: Term frequency weighting
- **Cosine Similarity**: Vector similarity measure
- **Feature Engineering**: Multi-feature combination
- **Natural Language Processing**: Text analysis techniques

## Datasets & Sources

- **TMDB Dataset**: The Movie Database (TMDB) API
- **Movie Metadata**: Budget, revenue, genres, keywords
- **Credits Data**: Cast and crew information

## License

This project is for educational purposes. The datasets are sourced from TMDB and are subject to their terms of use.

---

<div align="center">

Built for movie enthusiasts

</div>
