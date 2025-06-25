# 🎧 Spotify Track Recommender System using K-Means Clustering

##  Overview
This project builds a Spotify music recommender system using unsupervised clustering. Based on a user's input of a favorite **track**, **artist**, or both, the system recommends **5 new tracks from 5 different artists**, tailored to their musical taste. The recommender is built using **KMeans clustering** applied to Spotify track features.

The dataset used is a public kaggle dataset, containing various audio features for a wide range of Spotify tracks. 
https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset

---

##  Project Structure

### Part 1: Clustering Analysis

1. **Data Cleaning & Preprocessing**
   - Handled missing values
   - Removed irrelevant or duplicate columns
   - Applied feature scaling and normalization
   - Conducted exploratory data analysis (EDA)

2. **Feature Selection**
   - Selected numeric audio features (e.g., `danceability`, `energy`, `tempo`, etc.)
   - Used PCA for dimension reduction

3. **KMeans Clustering**
   - Applied the KMeans algorithm
   - Used the elbow method and silhouette score to determine optimal number of clusters
   - Evaluated clusters with performance metrics
   - Analyzed clusters with visualizations and descriptive statistics

4. **Cluster Labeling**
   - Labeled each track in the dataset with a cluster ID
   - Used cluster assignments for recommendation logic

---

### Part 2: Recommender System

- **User Input Handling**
  - User can input:
    - A favorite **track**
    - A favorite **artist**
    - Or **both**

- **Recommendation Logic**
  - Identify the cluster of the user’s input
  - Utilize cosine similarity to find closest artist/song
  - Recommend **5 tracks** from that cluster
    - Must be from **5 different artists**
    - Must **exclude** the user’s input artist(s) or track(s)

- **Output**
  - Final list of 5 track recommendations
  - Displayed with track name, artist name and similarity score

---

## ⚙️ Technologies Used

- **Python**
- **Pandas** for data wrangling
- **NumPy** for numerical operations
- **Matplotlib / Seaborn** for visualization
- **Scikit-learn** for clustering (KMeans) and metrics

---

##  Dataset Column Descriptions

- **track_id**  
  The Spotify ID for the track.

- **artists**  
  The artists' names who performed the track. If there is more than one artist, they are separated by a `;`.

- **album_name**  
  The album name in which the track appears.

- **track_name**  
  Name of the track.

- **popularity**  
  A value between 0 and 100 that reflects the popularity of the track, calculated based on total and recent plays. Higher values indicate more recent and frequent plays. Duplicate tracks (e.g., same track on single and album) are rated separately.

- **duration_ms**  
  The track length in milliseconds.

- **explicit**  
  Whether the track has explicit lyrics. `true` = yes, `false` = no or unknown.

- **danceability**  
  Describes how suitable a track is for dancing based on tempo, rhythm stability, beat strength, etc. Ranges from 0.0 (least danceable) to 1.0 (most danceable).

- **energy**  
  Measures intensity and activity from 0.0 to 1.0. Energetic tracks typically feel fast, loud, and noisy.

- **key**  
  The key the track is in, using standard Pitch Class notation:  
  `0 = C`, `1 = C♯/D♭`, `2 = D`, ..., `11 = B`. `-1` indicates no key detected.

- **loudness**  
  The overall loudness of a track in decibels (dB).

- **mode**  
  Indicates the modality (scale type) of the track:  
  `1 = major`, `0 = minor`.

- **speechiness**  
  Detects presence of spoken words:  
  - >0.66: likely spoken word (e.g., talk show)  
  - 0.33–0.66: mix of music and speech (e.g., rap)  
  - <0.33: likely instrumental or sung

- **acousticness**  
  Confidence from 0.0 to 1.0 of whether the track is acoustic.  
  `1.0` = high confidence that the track is acoustic.

- **instrumentalness**  
  Predicts likelihood that a track contains no vocals:  
  Higher values indicate more instrumental content.

- **liveness**  
  Detects audience presence. Values above `0.8` suggest the track was likely recorded live.

- **valence**  
  Measures musical positiveness from 0.0 (sad, depressed) to 1.0 (happy, euphoric).

- **tempo**  
  Estimated tempo in beats per minute (BPM), representing the speed or pace of the track.

- **time_signature**  
  Estimated time signature of the track. Values typically range from 3 to 7, corresponding to 3/4 to 7/4 time.

- **track_genre**  
  The genre classification of the track.

