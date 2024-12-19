# Football Data Scraper and Match Outcome Predictor

## Overview
This project provides tools to scrape football match data from the FBref website and use the data to predict match outcomes using a machine learning model.  
-https://fbref.com/en/   
-Competitions  

### Features
- **Web Scraping**:  
  Scrape football match data from FBref for any specified league, year range, and save it as a CSV file.  
- **Machine Learning**:  
  Predict match outcomes (Win/Loss/Draw) using an ML model with options to clean the data and use rolling averages of previous matches for enhanced accuracy.

## Files
1. **`WebScraping.ipynb`**:  
   - Allows you to specify the league URL on FBref and the years to scrape data from.  
   - Save the scraped data to a CSV file with a custom filename.

2. **`ML_Model.ipynb`**:  
   - Loads the CSV data.  
   - Lets you choose the prediction mode:  
     - **WLD (Win/Loss/Draw)**  
     - **Binary (Win or Not Win)**  
   - Displays model accuracy with and without data cleaning using rolling averages from the previous three matches.

---

## Getting Started

### Prerequisites
Ensure you have Python and the following libraries installed:
- `pandas`
- `numpy`
- `requests`
- `BeautifulSoup`
- `scikit-learn` (for ML modeling)

### Instructions

#### 1. Scrape Match Data
- Open `WebScraping.ipynb`.
- Specify the league URL, year range, and desired filename:
  ```python
  years = list(range(2024, 2019, -1))  # Scrapes seasons 2024 through 2020
  match_df.to_csv("matchesPrem(2024-2019).csv")  # Saves the data to a CSV file
#### 2. Load and Analyze Data
- Open `ML_Model.ipynb`.  
- Load the scraped CSV file:  
  ```python
  matches = pd.read_csv("matchesPrem(2024-2019).csv", index_col=0)
#### 3. View Model Performance
- The notebook evaluates and displays the accuracy:
  - **Before Data Cleaning**:  
    Accuracy is calculated using the raw match data.  
  - **After Data Cleaning**:  
    Enhanced accuracy is calculated using rolling averages from the previous three games.
