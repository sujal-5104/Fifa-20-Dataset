# FIFA 20 Player Analysis and Skill-Based Clustering

A data science project exploring FIFA 20 player attributes, performance ratings, wages, and country-wise player representation. This project uses exploratory data analysis (EDA), visualization, dimensionality reduction, and unsupervised machine learning to identify groups of players with similar skill profiles.

## Project Overview

The project analyzes the FIFA 20 player dataset to discover patterns in player skills, age, overall ratings, and weekly wages. K-Means clustering is used to group players based on selected football attributes, and alternative clustering algorithms are compared to support model selection.

## Objectives

- Explore and clean the FIFA 20 player dataset.
- Identify the top 10 countries by player count.
- Investigate the relationship between player age and overall rating.
- Compare weekly wages for Strikers (ST), Right Wingers (RW), and Left Wingers (LW).
- Group players using their football skill attributes.
- Compare clustering algorithms and select a suitable model.
- Save trained models and preprocessing artifacts for reuse.

## Dataset

The project uses the FIFA 20 player dataset, containing player demographics, clubs, positions, ratings, market values, wages, and football skill attributes.

- Dataset file: `players_20.csv`
- Analyzed dataset: 18,278 rows and 104 columns after the project's cleaning process.

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook
- Joblib

## Project Workflow

1. Load and inspect the dataset.
2. Clean data and examine missing values.
3. Perform exploratory data analysis.
4. Visualize country-wise player counts and age-rating patterns.
5. Compare wages by playing position.
6. Prepare skill features and scale them for clustering.
7. Apply and evaluate clustering algorithms.
8. Use PCA for dimensionality reduction and visualization.
9. Save trained models and supporting artifacts.
10. Reload the saved artifacts and test a sample prediction.

## Key Findings

- **Country representation:** England has the highest player count in the analyzed dataset, followed by Germany and Spain.
- **Age and rating:** Median overall ratings generally increase through younger and middle age groups, then remain relatively stable. Small age groups should be interpreted cautiously.
- **Wages by position:** Left Wingers have the highest mean weekly wage among ST, RW, and LW in this dataset. All three groups have a median weekly wage of €4,000.
- **Player clustering:** K-Means with two clusters separates players into a larger group with generally stronger technical and movement attributes and a smaller group with generally lower skill ratings.
- **Model selection:** K-Means was retained as the deployment candidate because it supports straightforward prediction for new samples and produces interpretable clusters. Alternative algorithms were also evaluated.

## Model Evaluation

Clustering algorithms were compared using the Silhouette Score, Davies–Bouldin Index, Calinski–Harabasz Score, and execution time.

| Algorithm | Silhouette Score | Davies–Bouldin Index |
|---|---:|---:|
| K-Means | 0.44 | 0.84 |
| Agglomerative Clustering | 0.46 | 0.73 |
| DBSCAN | 0.47 | 0.71 |

The alternative algorithms were evaluated on samples, so the metrics are not perfectly comparable. K-Means was selected for the saved prediction workflow based on its practical usability and interpretable two-cluster solution.

## Saved Artifacts

The `fifa20_artifacts/` directory contains:

- `preprocessor.joblib` — preprocessing object
- `kmeans_model.joblib` — trained K-Means model
- `skill_features.joblib` — selected skill feature names
- `cluster_profiles.joblib` — cluster summary profiles
- `pca_model.joblib` — trained PCA object

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/sujal-5104/Fifa-20-Dataset.git
cd Fifa-20-Dataset
```

### 2. Install dependencies

Use a Python environment and install the packages used in the notebook:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter joblib
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook PRCP_1004_FIFA20.ipynb
```

Run the notebook cells in order. Keep `players_20.csv` and the `fifa20_artifacts/` directory in the expected project locations.

## Limitations

- Results depend on the available FIFA 20 dataset and its data quality.
- Cluster labels represent statistical groupings, not official player positions or quality categories.
- Wages and ratings describe the dataset and should not be interpreted as causal relationships.
- Clustering metrics can differ depending on sampling, scaling, and feature selection.

## Future Improvements

- Add an interactive player-cluster exploration dashboard.
- Compare additional clustering methods and feature-selection strategies.
- Improve cluster interpretation using more visualizations.
- Add automated tests for loading artifacts and generating cluster predictions.

## Author

**Sujal-5104**

GitHub: [@sujal-5104](https://github.com/sujal-5104)

---

*This project was developed for data analysis and machine learning practice.*
