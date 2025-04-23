# PHASE-4-PROJECT
# 🎬 Movie Recommender System 🎬

## Overview

This project develops a movie recommender system using the MovieLens dataset. The MovieLens dataset is a popular benchmark dataset in the field of recommender systems. It provides rich information about movies, user ratings, tags, and links to external movie databases.  This project aims to provide valuable insights into user behavior and movie preferences, ultimately leading to improved movie recommendations.

## Objectives

The primary objectives of this project are to:

* **Understand User Beliefs:** Analyze how users form opinions about movies they haven't watched.
* **Investigate Relationships:** Explore the connections between user beliefs, past movie ratings, and received recommendations.
* **Evaluate Alignment:** Assess how well the recommendations align with and influence user beliefs.
* **Study Decision-Making:** Examine user choices and behaviors in the context of movie consumption.

## Business Questions

This project seeks to answer the following key business questions:

* ❓ **Belief Formation:** How do users develop beliefs or expectations about movies they haven't seen?
* ❓ **Influence Factors:** What factors (e.g., genres, tags, ratings, recommendations) most significantly shape these beliefs?
* ❓ **Belief vs. Ratings:** How closely do user beliefs match their actual ratings after watching a movie?
* ❓ **Past Impact:** How do past user ratings and behaviors affect the relevance of future recommendations?
* ❓ **Recommendation Influence:** To what extent do recommendations impact or modify user expectations and decisions?

## Data Understanding

The project utilizes data from the following four files:

1.  **Movies Data (movies.csv):**
    * Contains movie information.
    * **Columns:**
        * `movieId`: Unique identifier for each movie.
        * `title`: Title of the movie (includes release year).
        * `genres`: Genres of the movie (e.g., Action|Adventure|Comedy).

2.  **Links Data (links.csv):**
    * Provides identifiers for linking to external movie databases.
    * **Columns:**
        * `movieId`: Unique identifier for each movie.
        * `imdbId`: Identifier for IMDb (Internet Movie Database).
        * `tmdbId`: Identifier for TMDb (The Movie Database).

3.  **Ratings Data (ratings.csv):**
    * Contains user ratings for movies.
    * **Columns:**
        * `userId`: Unique identifier for each user.
        * `movieId`: Unique identifier for each movie.
        * `rating`: User's rating for the movie (0.5 to 5.0).
        * `timestamp`: Timestamp of the rating.

4.  **Tags Data (tags.csv):**
    * Contains user-generated tags for movies.
    * **Columns:**
        * `userId`: Unique identifier for each user.
        * `movieId`: Unique identifier for each movie.
        * `tag`: User-generated tag describing the movie.
        * `timestamp`: Timestamp of the tag.
##   Dataset Attributes

The analysis utilizes the MovieLens dataset, which comprises several files. Here's a summary of their key attributes after cleaning and merging:

* **Merged Dataset Shape:** The merged dataset has 102,695 rows and 10 columns.
* **Column Information:**
    * `movieId`:  Unique identifier for movies (integer).
    * `title`:  Movie titles (object/string).
    * `genres`: Movie genres (object/string, pipe-separated).
    * `userId`:  Unique identifier for users (object).
    * `rating`: User ratings for movies (float).
    * `timestamp_rating`: Timestamps of when ratings were given (float).
    * `tag`: User-generated tags for movies (object/string). Missing values were filled with "unknown".
    * `timestamp_tag`: Timestamps of when tags were applied (float). Missing values were filled with the mean timestamp.
    * `imdbId`:  Identifier for movies in IMDb (integer).
    * `tmdbId`: Identifier for movies in TMDb (object).
      
## Data Cleaning

The following data cleaning steps were performed:

* **Missing Values:**
    * Handled missing values in the `tag` column by filling them with "unknown".
    * Handled missing values in the `timestamp_tag` column by filling them with the mean timestamp.
    * Removed rows with missing values in `userId`, `rating`, `timestamp_rating`, and `tmdbId`.
* **Duplicates:**
    * Checked for and confirmed that there were no duplicate entries in the merged dataset.
* **Data Types:**
    * Converted the data types of the `userId` and `tmdbId` columns to object for consistency.

## Exploratory Data Analysis (EDA)

* Performed exploratory data analysis to understand the distributions and characteristics of the data.
* Visualized the distribution of movie ratings.

## Recommendation Strategies

The project explores and implements several movie recommendation strategies, including:

* **Content-Based Filtering:** Recommends movies similar to those a user has liked in the past, based on movie features (e.g., genres, tags).
* **Collaborative Filtering:** Recommends movies that users with similar tastes have liked.
* **Hybrid Recommendation Model:** Combines content-based and collaborative filtering to provide more accurate and diverse recommendations.

## Model Tuning

* **Hyperparameter Tuning:** The project employed hyperparameter tuning techniques to optimize the performance of the collaborative filtering models. This involves systematically searching for the best combination of parameters to maximize the model's predictive accuracy.

## Key Observations based on the analysis

Based on the analysis and modeling in this project, here are the key observations and recommendations regarding movie recommender systems:

* **Complementary Strengths:** Content-based filtering and collaborative filtering offer complementary strengths. Content-based methods excel at leveraging movie features (genres, tags) for personalized recommendations, while collaborative filtering captures user-item interactions and patterns of similar tastes.
* **Hybrid Model Potential:** A hybrid recommendation model, combining content-based and collaborative filtering, has the potential to provide more accurate, diverse, and robust recommendations by mitigating the limitations of individual approaches.
* **Importance of Tuning:** Hyperparameter tuning is crucial for optimizing the performance of collaborative filtering models, particularly matrix factorization techniques like SVD. Fine-tuning parameters can significantly improve the accuracy of predictions.
* **Scalability Considerations:** For real-world applications, it's essential to consider the scalability of recommender systems. Evaluating performance on larger datasets and optimizing algorithms for efficiency is important.
* **Contextual Factors:** The optimal recommender system strategy depends on various factors, including the specific goals of the application, the characteristics of the data, and user behavior patterns.
* **Continuous Improvement:** Recommender systems should be continuously evaluated, updated, and refined to maintain their effectiveness. This includes incorporating new data, adjusting model parameters, and exploring new recommendation techniques.

##   Recommendations & Conclusions

* **User Belief Formation:** Understanding how users develop pre-consumption expectations about movies is essential for effective marketing .
* **Factors Influencing Beliefs:** Movie genres, tags, past ratings, and recommendations majorly shape user beliefs, requiring businesses to strategically leverage these elements.
* **Belief vs. Actual Ratings:** Analyzing the alignment between pre-consumption beliefs and post-consumption ratings helps businesses assess the accuracy of expectations set by marketing and recommendations.
* **Impact of Past Behavior:** User rating history and viewing patterns strongly influence future recommendations, emphasizing the need for robust user behavior tracking and analysis.
* **Influence of Recommendations:** Recommender systems play a major role in shaping user choices. Businesses must ensure responsible and accurate recommendations to build user trust and encourage content exploration.
* **Value of Hybrid Models:** Combining content-based and collaborative filtering offers the potential for more accurate, diverse, and engaging recommendations, providing a competitive advantage.
* **Importance of Continuous Improvement:** Recommender systems require ongoing evaluation and updates to adapt to evolving user preferences and maintain their effectiveness.


## Libraries Used

* `pandas`
* `numpy`
* `seaborn`
* `matplotlib.pyplot`
* `sklearn.model_selection`
* `sklearn.preprocessing`
* `sklearn.feature_extraction.text`
* `sklearn.metrics.pairwise`
* `scipy.sparse`
* `sklearn.neighbors`
* `surprise`

## Installation

1.  Clone the repository:

    ```bash
    git clone <https://github.com/Evee-hub/PHASE-4-PROJECT>
    ```

2.  Install the required libraries:

    ```bash
    pip install pandas numpy seaborn matplotlib scikit-learn surprise
    ```

3. Datasets (`movies.csv`, `ratings.csv`, `tags.csv`, `links.csv`) :in the same directory as the notebook.

## Usage

* Run the Jupyter Notebook (`Movie Recommender System.ipynb`) to execute the code and generate movie recommendations.

## Contributors

* [Mark Chiuri, Evelyn Mwangi, Wilberforce Kirui, Edel Lwoyelo, Khadija Hussein, Hakima Ibrahim]

---
