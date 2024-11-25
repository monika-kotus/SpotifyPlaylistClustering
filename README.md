# Spotify Playlist Clustering

This project leverages clustering techniques to group 5000 Spotify tracks into cohesive playlists based on their audio features. The goal is to evaluate whether machine learning methods like K-Means can create meaningful playlists and explore potential improvements.

---

## Features of the Prototype

### How Was the Prototype Created?
1. **Data Preprocessing**: Cleaned the dataset by removing irrelevant columns (`name`, `artist`, `id`, `html`, `time_signature`, etc.) to reduce noise.
2. **Feature Selection**: Retained audio features such as `danceability`, `energy`, `valence`, and `tempo`, which are critical for grouping similar songs.
3. **Scaling**: Applied PowerTransformer to normalize data and reduce skewness for better clustering performance.
4. **Dimensionality Reduction**: Used PCA to reduce dimensionality while retaining 95% of the dataset's variance, improving clustering efficiency.
5. **Clustering**: Implemented K-Means with 50 clusters based on insights from the Elbow and Silhouette methods.
6. **Evaluation**: Analyzed the cohesion of playlists qualitatively, focusing on audio feature similarity.

---

### Results and Insights

#### How Many Playlists?
- The dataset was grouped into **50 clusters**.
- **Why 50?**
  - The Silhouette Method indicated that 50 clusters provide the most well-defined and separated groups.
  - This granularity balances playlist specificity and broad appeal, averaging ~100 songs per playlist.

#### Audio Features Used:
- **Retained**: `danceability`, `energy`, `speechiness`, `acousticness`, `valence`, `tempo`, etc.
- **Dropped**: Columns unrelated to song similarity (`name`, `artist`) or redundant/low-variance features (`time_signature`, `duration_ms`).

#### Prototype Effectiveness:
The playlists effectively grouped songs with similar audio characteristics, demonstrating cohesion within clusters. Example clusters include:
- **Cluster 15**: A heavy metal playlist featuring intense instrumentation and high energy.
- **Cluster 6**: A pop and electronic dance playlist with upbeat rhythms and consistent tempo.

---

### Evaluation of Spotify Features

Spotify’s audio features can partially identify "similar songs" based on measurable criteria like mood and tempo. However, human judgment considers additional factors like lyrics, cultural context, and personal preferences, which are not captured in numerical features.

---

### Suggestions for Improvement

#### What Data Could Improve Playlists?
1. **Lyric Analysis**: Incorporate sentiment and themes for richer playlists.
2. **User Behavior**: Use listening history and skip rates to refine clustering.
3. **Cultural Tags**: Include genres, eras, or regional popularity to enhance relevance.

---

### Is K-Means the Best Approach?

**Pros**:
- Simple, scalable, and interpretable.
- Efficient for large datasets.

**Cons**:
- Assumes clusters are spherical, which may not align with song relationships.
- Sensitive to the choice of cluster numbers and outliers.

Alternative clustering methods like DBSCAN could be explored for non-spherical relationships.

---

### Next Steps
- **Validate Playlists**: Conduct user testing and gather feedback for personalization.
- **Refine Clustering**: Experiment with algorithms like DBSCAN.
- **Enhance Data**: Add diverse sources such as lyrics, user behavior, and cultural tags.
- **Develop a Recommendation System**: Integrate real-time user behavior for dynamic playlist creation.

---

This project demonstrates the potential of machine learning in playlist generation and opens avenues for further research and enhancement.

