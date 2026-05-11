#  Top 1000 Movies - Exploratory Data Analysis

> Uncovering patterns in commercial performance, audience behaviour, and critical reception across the top 1000 highest-grossing films of all time.



##  Problem Statement

The entertainment industry generates massive amounts of data spanning ratings, revenue, audience engagement, and genre. This project performs a structured EDA on the **Top 1000 highest-grossing movies** (as listed on Box Office Mojo, sourced from IMDb) to identify factors that drive a film's commercial and critical success.



##  Repository Structure
```
movie-datasest-eda-analysis/
│
├── top_1000_movies.csv          # csv file
├── top_1000_movies_eda.ipynb    # Notebook
└── README.md
```


##  Dataset Structure

| Attribute | Description |
|---|---|
| Movie Title | Name of the film |
| Year of Release | Release year |
| Genre | One or more genre tags |
| Movie Rating | IMDb user rating (1–10) |
| Duration | Runtime |
| Gross | Domestic gross earnings (USD) |
| Worldwide LT Gross | Worldwide lifetime gross (USD) |
| Metascore | Weighted critic score (0–100) |
| Votes | Total IMDb votes cast |
| Logline | Brief Description|

**Source:** IMDb via Box Office Mojo - snapshot as of September 5, 2022.



##  Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-lightgrey?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Numerical-blue?logo=numpy)
![Plotly](https://img.shields.io/badge/Plotly-Interactive%20Viz-purple?logo=plotly)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Viz-teal)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Charts-orange)



##  Analysis Pipeline

### 1. Data Cleaning & Preprocessing
- Renamed and standardised column names
- Removed symbol characters (`$`, `,`, `M`) from financial columns and cast to numeric
- Rescaled revenue columns to **millions (USD)** and Metascore to **out of 10** for interpretability
- Handled missing values using **median imputation** (chosen over mean due to high right-skew in financial and vote distributions)

### 2. Univariate Analysis
- Histograms, KDE plots, and box plots across all numeric features
- Key finding: Gross, Worldwide LT Gross, and Votes are **heavily right-skewed** - a few blockbuster outliers dominate the distributions

### 3. Bivariate Analysis
#### A. Correlation & Scatter Analysis
- Strong positive correlation between Domestic Gross and Worldwide Gross
- **Votes (audience engagement) showed a stronger correlation with revenue than ratings** - the most significant finding in correlation analysis
- Moderate alignment between IMDb ratings and Metascore

#### B. Time-Based Trend Analysis
- Movies released post-1990 dominate the dataset (reflecting industry growth and data accessibility)
- Worldwide revenue and audience engagement both trend upward over time, driven by globalisation and online platforms

#### C. Genre-Wise Analysis
- Multi-label genre encoding via column melting (`Genre A`, `Genre B`, `Genre C`)
- Top 12 genres by film count analysed across votes, Metascore, and worldwide gross

### 4. Multivariate Analysis
- Density heatmap across `Votes × Movie Rating → Avg Worldwide Gross`
- Highest gross values clustered where **both** engagement and ratings are high



##  Key Findings

| # | Finding |
|---|---|
| 1 | Revenue and engagement metrics are heavily skewed due to blockbuster outliers. |
| 2 | Popularity-based metrics correlate more strongly with financial success than ratings alone. |
| 3 | Genre plays a major role in influencing both audience behavior and financial outcomes. |
| 4 | **Sci-Fi** leads all genres in audience engagement - ~40% more votes than second-ranked Mystery |
| 5 | **Drama, Animation & Crime** score highest critically (Metascore), yet underperform commercially |
| 6 | **Fantasy, Sci-Fi & Adventure** dominate worldwide box office revenue |
| 7 | **Animation** is the only genre that ranks high on both critical and commercial metrics |
| 8 | Most genres score between **5.5–6.5** on Metascore - but votes and revenue vary dramatically |
| 9 | **Audience engagement** (votes) is a stronger predictor of commercial success than ratings alone |
| 10 | Strong audience approval combined with widespread engagement is most closely associated with exceptional worldwide revenue. |



##  Business Questions Addressed

- Which genres generate the highest worldwide revenue? → **Fantasy, Sci-Fi, Adventure**
- Does audience engagement correlate with box office success? → **Yes - more strongly than ratings**
- Are highly rated movies always commercially successful? → **No - clear critical vs. commercial divide**
- How have movie trends evolved over time? → **Revenue and engagement rise steadily post-1990s**
- Which variables most influence box office success? → **Votes and audience reach over critic scores**

 
