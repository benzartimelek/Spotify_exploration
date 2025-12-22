# Spotify Data Visualization Lab

## Project Overview

This project explores and visualizes Spotify music data to uncover insights about music trends, popular genres, artists, and song characteristics. The analysis works with a real-world dataset containing information about songs, their audio attributes, and popularity metrics.

**Authors:** Amisha & Melek  

## Table of Contents

- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Analysis Overview](#analysis-overview)
- [Key Findings](#key-findings)
- [Technologies Used](#technologies-used)
- [How to Run](#how-to-run)
- [Results & Visualizations](#results--visualizations)

## Dataset

**File:** `songs_normalize.csv`

The dataset contains normalized Spotify song data with the following key features:

- **Song Metadata:** Artist name, song title, genre, duration
- **Popularity Metrics:** Popularity score (0-100)
- **Audio Features:**
  - Danceability (0.0-1.0)
  - Energy (0.0-1.0)
  - Valence/positivity (0.0-1.0)
  - Acousticness (0.0-1.0)
  - Speechiness (0.0-1.0)
  - Instrumentalness (0.0-1.0)
  - Liveness (0.0-1.0)
  - Loudness (dB)
  - Tempo (BPM)
- **Content Rating:** Explicit content flag

## Project Structure

```
Lab5/
│
├── lab_draft.ipynb          # Main Jupyter notebook with analysis
├── songs_normalize.csv      # Dataset file
└── README.md               # Project documentation
```

## Installation & Setup

### Prerequisites

- Python 3.7 or higher
- Jupyter Notebook or JupyterLab

### Required Libraries

```bash
pip install pandas numpy matplotlib seaborn
```

Or install all dependencies at once:

```bash
pip install -r requirements.txt
```

## Analysis Overview

The project is divided into four main parts:

### Part I: Data Loading & Initial Exploration
- Import necessary libraries
- Load and inspect the dataset
- Examine dataset dimensions and structure
- Check data types and summary statistics
- Identify missing values

### Part II: Data Cleaning & Preprocessing
- Handle missing values (none found in this dataset)
- Identify and analyze duplicate records
- Remove duplicates based on artist and song, keeping the most popular version
- Ensure appropriate data types for all columns

**Key Decision:** Duplicates were found to be the same recordings with different genre classifications (likely from appearing in multiple playlists). The version with the highest popularity was retained as it represents the most current and accurate popularity reading.

### Part III: Exploratory Data Analysis (EDA)

#### Task 1: Genre Analysis
- Distribution of songs across music genres
- Identification of most popular genres
- Percentage analysis of top genres

#### Task 2: Popularity Patterns
- Distribution plots of popularity scores
- Statistical measures (mean, median, mode)
- Outlier detection using box plots
- Analysis of exceptional high/low popularity songs

#### Task 3: Artist Metrics
- Top 10 artists by song count
- Top 10 artists by average popularity
- Correlation between song count and popularity
- Most prolific artists identification

#### Task 4: Explicit Content Analysis
- Percentage of explicit vs non-explicit songs
- Visual comparison using pie/bar charts
- Popularity comparison between explicit and non-explicit content

### Part IV: Advanced Feature Analysis

#### Task 1: Correlation Analysis
- Heatmap showing correlations between audio features
- Identification of strongest positive/negative correlations
- Analysis of surprising relationships
- Popularity predictors examination

#### Task 2: Multi-Feature Comparison
- Radar charts for top 10 most popular songs
- Parallel coordinates plot for feature comparison
- Feature profile analysis of hit songs
- Pattern identification in popular music

## Key Findings

### General Insights

1. **Genre Distribution**
   - Multiple genres identified with varying song counts
   - Many songs have multi-genre labels (e.g., "rock, metal", "pop, Dance/Electronic")
   - Top 3 genres account for a significant portion of the dataset

2. **Popularity Patterns**
   - Popularity scores show a specific distribution pattern
   - Typical popularity range identified using IQR (Interquartile Range)
   - Small percentage of songs have exceptionally high (>80) or low (<20) popularity

3. **Artist Insights**
   - Top artists identified by both song count and average popularity
   - Having more songs does not necessarily correlate with higher average popularity
   - Most popular individual songs identified

4. **Explicit Content**
   - Clear percentage breakdown of explicit vs non-explicit songs
   - Explicit songs show varying popularity patterns compared to non-explicit

5. **Audio Feature Correlations**
   - **Strong Positive:** Energy ↔ Loudness (energetic songs are louder)
   - **Strong Negative:** Energy ↔ Acousticness (acoustic songs are less energetic)
   - **Surprising Finding:** Popularity is weakly correlated with audio features
   
6. **What Makes a Song Popular?**
   - No single audio feature strongly predicts popularity
   - Popular songs show diversity in their audio feature profiles
   - Popularity likely depends on external factors:
     - Marketing and promotion
     - Artist fame and reputation
     - Cultural trends and timing
     - Social media virality
     - Playlist placements

## Technologies Used

- **Python 3.x** - Programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Data visualization (static plots)
- **Seaborn** - Statistical data visualization
- **Jupyter Notebook** - Interactive development environment

## How to Run

1. **Clone or download the project**
   ```bash
   cd Lab5
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

3. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook lab_draft.ipynb
   ```

4. **Run the notebook**
   - Execute cells sequentially from top to bottom
   - Or use "Run All" from the Cell menu

5. **View results**
   - All visualizations will display inline
   - Statistical outputs will appear below code cells

## Results & Visualizations

The notebook generates comprehensive visualizations including:

- **Bar Charts:** Genre distribution, top artists by song count and popularity
- **Histograms & KDE Plots:** Popularity score distributions
- **Box Plots:** Outlier detection in popularity, explicit content comparison
- **Pie Charts:** Explicit vs non-explicit song proportions
- **Heatmaps:** Correlation matrices of audio features
- **Radar Charts:** Audio feature profiles for top songs
- **Parallel Coordinates Plots:** Multi-dimensional feature comparisons

## Data Cleaning Notes

### Duplicate Handling Strategy

The dataset contained duplicate entries for the same songs. Analysis revealed:

- Most duplicates had identical duration (std = 0.0)
- Duplicates were the same audio recordings with different metadata
- Variations were primarily in:
  - Genre classifications (multi-genre tagging)
  - Popularity scores (different snapshot times)
  - Minor audio feature differences

**Resolution:** Kept the version with the highest popularity score for each unique artist-song combination. This ensures:
- One row per song
- Most current popularity data
- Safe removal of redundant entries

## Future Enhancements

Potential extensions to this analysis:

1. Time series analysis if release dates are available
2. Machine learning models to predict song popularity
3. Sentiment analysis of song lyrics (if available)
4. Network analysis of artist collaborations
5. Genre evolution and trend analysis
6. Regional popularity comparisons (if location data available)
7. Audio feature clustering to identify song archetypes

## Contact

For questions or feedback regarding this analysis, please contact the authors through the course platform.

---
