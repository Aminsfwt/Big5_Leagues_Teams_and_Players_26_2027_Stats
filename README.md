# Big Five European Leagues — Teams & Players Statistics

A Python data analysis project exploring football statistics from Europe's **Big Five Leagues** using data collected from [FBref](https://fbref.com/).

The project combines team-level league analysis with player-level attacking performance comparisons, data cleaning, statistical calculations, and football visualizations.

## Project Overview

This project analyzes football teams and players across five major European football competitions:

- Premier League — England
- La Liga — Spain
- Bundesliga — Germany
- Serie A — Italy
- Ligue 1 — France

The goal is to explore team performance, compare league statistics, identify top-performing clubs, and evaluate attacking players using per-90-minute metrics and percentile rankings.

## Repository Structure

The repository contains two main Jupyter notebooks:

| Notebook | Description |
|---|---|
| `Big5_Leauges_Stats_20-27.ipynb` | Team statistics collection, cleaning, analysis, and visualization. |
| `Mbappe_Raphinha_Yamal_Season_Stats.ipynb` | Player statistics analysis, attacking performance calculations, and player visualizations. |

## Data Sources

The project collects data from FBref:

**1. Team Statistics**

[Big Five European Leagues Stats](https://fbref.com/en/comps/Big5/Big-5-European-Leagues-Stats)

**2. Player Statistics**

[Big Five European Leagues Player Statistics](https://fbref.com/en/comps/Big5/stats/players/Big-5-European-Leagues-Stats)

Data is extracted from HTML tables using Python browser automation and Pandas.

## Notebook 1: Big Five Leagues — Team Statistics

**File:** `Big5_Leauges_Stats_20-27.ipynb`

### Data Collection and Processing

The notebook performs the following steps:

1. Opens the FBref competitions page using `undetected_chromedriver`.
2. Extracts the Big Five leagues statistics table using `pandas.read_html()`.
3. Removes repeated header rows.
4. Cleans country and top-team-scorer information.
5. Converts statistical columns into appropriate numeric data types.
6. Performs team-level analysis and creates visualizations.
7. Exports the cleaned dataset into a CSV file.

### Analysis and Insights

The notebook explores:

- Team standings and league positions.
- Matches played, wins, draws, and losses.
- Goals scored and goals conceded.
- Goal difference and total points.
- Points and goals correlation.
- Total goals scored by country.
- Top 10 clubs by attendance per match.
- Top-performing teams based on goal difference.

### Exported Dataset

The cleaned dataset is exported as:

`big_5_Leagues_Stats_20-27.csv`

## Notebook 2: Players — Attacking Performance Analysis

**File:** `Mbappe_Raphinha_Yamal_Season_Stats.ipynb`

This notebook focuses on evaluating attacking players across Europe's Big Five leagues.

### Data Collection and Cleaning

The notebook:

1. Extracts player standard statistics from FBref.
2. Removes repeated headers and unnecessary columns.
3. Cleans player nationality and statistical fields.
4. Converts numeric columns into appropriate data types.
5. Filters attacking players whose position contains `FW`.
6. Keeps players with at least **400 minutes played**.

### Calculated Performance Metrics

The notebook calculates attacking statistics per 90 minutes:

| Metric | Description |
|---|---|
| Goals per 90 | Goals scored per 90 minutes |
| Assists per 90 | Assists provided per 90 minutes |
| Non-Penalty Goals per 90 | Goals excluding penalties per 90 minutes |
| Goals + Assists per 90 | Combined attacking contribution |
| Non-Penalty Goals + Assists | Combined contribution excluding penalty goals |

### Percentile-Based Player Evaluation

To compare players fairly, the project uses percentile ranking through Pandas:

`rank(pct=True) * 100`

Five performance scores are generated:

- Goals
- Assists
- Goals + Assists
- No Penalty Goals
- No Penalty Goals + Assists

**Important:** These values represent relative percentile-style rankings within the filtered forward-player dataset, not actual goals or assists.

For example, a score of 95 indicates a player ranks approximately in the top 5% of the comparison group for that metric.

### Players Analyzed

The notebook includes performance analysis for:

- Kylian Mbappé — Real Madrid
- Raphinha — Barcelona
- Lamine Yamal — Barcelona
- Erling Haaland — Manchester City

### Visualizations

Using Matplotlib and MPLSoccer, the project creates:

- Individual player radar charts.
- Combined player performance comparisons.
- Pizza charts for attacking performance.
- Visual comparisons across five attacking metrics.

These visualizations help identify each player's strengths and weaknesses in scoring and creating goals.

## Technologies and Libraries

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Jupyter Notebook | Interactive analysis |
| Pandas | Data extraction, cleaning, and transformation |
| Undetected ChromeDriver | Browser automation |
| LXML | HTML parsing |
| HTML5lib | HTML parsing support |
| Matplotlib | Data visualization |
| MPLSoccer | Football performance visualizations |
| Tabulate | Formatted statistical tables |

## Installation and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/Aminsfwt/Big5_Leagues_Teams_and_Players_26_2027_Stats.git
cd Big5_Leagues_Teams_and_Players_26_2027_Stats
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install pandas undetected-chromedriver lxml html5lib matplotlib tabulate mplsoccer jupyter
```

Google Chrome must also be installed.

### 4. Run Jupyter Notebook

```bash
jupyter notebook
```

Open either notebook and execute the cells sequentially.

An active internet connection is required because the notebooks retrieve statistics directly from FBref.

## Project Outputs

The project generates:

- Cleaned team statistics CSV.
- Team performance charts.
- Player attacking performance radar charts.
- Player comparison visualizations.
- Erling Haaland pizza chart.

The notebooks generate these outputs when the relevant cells are executed.

## Important Notes

- Statistics are collected from live FBref pages and may change over time.
- The season represented by the source data should be verified when running the notebooks.
- Some notebook names and output filenames contain legacy season references.
- Player percentile scores depend on the filtered comparison group.
- The 400-minute threshold excludes players with limited playing time.
- Changes to FBref's HTML structure may require updates to the scraping code.

## Future Improvements

- Build an automated data pipeline for periodic data collection.
- Store historical football statistics in a SQL database.
- Add more detailed player metrics, including passing, defending, and possession.
- Compare players across different seasons.
- Develop an interactive Tableau or Power BI dashboard.
- Add automated data-quality validation.
- Organize the Python code into reusable modules.
- Add a version-controlled `requirements.txt` file.

## Author

**Amin Safout**

GitHub: [@Aminsfwt](https://github.com/Aminsfwt)

Repository: [Big Five Leagues — Teams and Players Statistics](https://github.com/Aminsfwt/Big5_Leagues_Teams_and_Players_26_2027_Stats)

---

*This project was developed for football statistics exploration, data analysis practice, and portfolio demonstration.*
