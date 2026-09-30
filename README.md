# Spotify Song Data Analysis

---

## **Table of Contents**

1. [Introduction](#introduction)  
2. [Dataset Description](#dataset-description)  
3. [Project Objectives](#project-objectives)  
4. [Installation and Setup](#installation-and-setup)  
5. [Project Workflow](#project-workflow)  
6. [Key Findings](#key-findings)  
7. [Tools and Technologies](#tools-and-technologies)  
8. [Future Work](#future-work)  
9. [Acknowledgments](#acknowledgments)  

---

## **Introduction**

An exploratory Python project focused on preparing track data, comparing streaming and playlist metrics, and visualizing audio features. It is retained as an earlier portfolio project demonstrating data preparation, metric design, and exploratory reporting.

[Current analyst portfolio](https://github.com/AnalyzerArik/AnalyzerArik)

[Previous Analysis](https://github.com/AnalyzerArik/Spotify-Song-Data-Exploratory-Data-Analysis/blob/main/exploratory-data-analysis-of-spotify-song-data.ipynb) / 
[Revised Analysis](https://github.com/AnalyzerArik/Spotify-Song-Data-Exploratory-Data-Analysis/blob/main/spotify-songs-data-analysis-2.ipynb)

---

## **Dataset Description**

- **Source**: [Kaggle Dataset](https://www.kaggle.com/datasets/ashishak3000/spotify-dataset), supplemented with track durations through a Spotify API lookup documented in the notebook.
- **Loaded data**: 953 rows and 25 columns, including the added duration field.
- **Analysis sample**: 952 rows after removing one record with a nonnumeric `streams` value.
- **Example fields**: `track_name`, `artist(s)_name`, `streams`, `in_spotify_playlists`, `bpm`, and `danceability_%`.
- **Preparation**: Standardized text, converted numeric fields, and filled missing durations using artist-level means followed by a global mean. Duration-based results therefore include imputed values.

---

## **Project Objectives**

- Examine associations between audio features, playlist counts, and streams within the sample.
- Compare audio-feature averages by release year.
- Explore track groupings using energy, valence, and danceability.
- Communicate descriptive results with clear metrics and explicit limitations.

---

## **Installation and Setup**

The linked notebooks contain saved outputs for review. To work locally:

```bash
git clone https://github.com/AnalyzerArik/Spotify-Song-Data-Exploratory-Data-Analysis.git
cd Spotify-Song-Data-Exploratory-Data-Analysis
python -m pip install jupyter pandas numpy matplotlib seaborn scikit-learn
jupyter notebook
```

The repository does not include a `requirements.txt` or the input CSV. The revised notebook reads `updated_dataset_with_durations.csv` from a Kaggle-specific path; supply that enriched input and update the path before rerunning. The commented API enrichment code is historical reference, not a ready-to-run setup step. Dependencies are not pinned, and a clean-environment rerun has not been verified.

---

## **Project Workflow**

### **Data Preprocessing**

- Standardized text and numeric types, removed an invalid streams record, and imputed missing durations.

### **Exploratory Data Analysis (EDA)**

- Compared track and artist-string stream totals, playlist counts, and release-year averages.
- Examined correlations and distributions of audio features.

### **Visualization**

- Built charts with matplotlib and seaborn.
- Applied K-means with four clusters to energy, valence, and danceability.

### **Summary**

- Demonstrates preparation, aggregation, visualization, and the need to distinguish exploratory patterns from validated business conclusions.

---

## **Key Findings**

1. **Data quality affects the analysis sample.** The saved cleaning output identifies one invalid streams record; filtering it reduces the loaded data from 953 to 952 rows.
2. **Duration results depend on imputation.** After artist-level filling, 248 durations remained missing and were filled using a global mean. Duration summaries should not be read as entirely observed measurements.
3. **The composite ranking is a designed metric.** Its weights are 50% normalized streams, 20% danceability, 20% energy, and 10% valence. High energy and danceability contribute to the ranking by construction; it is not an objective measure of song quality.
4. **Clustering is exploratory.** Four K-means groups summarize selected audio features; the analysis does not validate them as genres or listener segments.

### **Interpretation limits**

- Playlist and stream comparisons are observational; they do not establish that playlist placement causes additional streams.
- Rankings and release-year averages describe this sample, not the full Spotify catalog or market-wide changes in listener preferences. Artist totals group the complete artist-credit string, including collaborations.
- The historical notebook contains broader language about song quality, engagement, and popularity drivers. Those interpretations are not established by the saved analysis; this README states the narrower supported scope.

---

## **Tools and Technologies**

- **Programming Language**: Python  
- **Libraries**:  
  - `pandas` for data manipulation  
  - `numpy` for statistical calculations
  - `scikit-learn` for K-means clustering  
  - `matplotlib` and `seaborn` for visualizations  
- **Platforms**: Kaggle Notebook for analysis and presentation.  

---

## **Future Work**

- Package the enriched input and pinned dependencies for reproducible runs.
- Quantify associations, show sample sizes by release year, and test sensitivity to imputed durations and ranking weights.
- Validate cluster stability before assigning business meaning to the groups.

These are proposed improvements, not completed analyses.

---

## Final Thoughts

The project's relevance to analyst and BI work is the preparation of usable reporting data, comparison of clearly defined metrics, and communication of analytical limits. See my [current portfolio](https://github.com/AnalyzerArik/AnalyzerArik) for featured work.

---

## **Acknowledgments**

Special thanks to Spotify for providing publicly available data and to the data analysis community for inspiring continuous growth and learning.  
