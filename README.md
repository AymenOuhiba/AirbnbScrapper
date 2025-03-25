
# 🏠 AirbnbScrapper

## 🧠 Project Overview

**AirbnbScrapper** is a web scraping and data cleaning project that collects listing information from Airbnb and organizes it into a structured dataset for further analysis. The project is built using `Selenium` for browser automation and `Pandas` for data manipulation.

It targets listings in **Jardins De Carthage, Tunisia**, for a specific travel period, extracting detailed information such as prices, titles, ratings, number of beds, and listing URLs.

---

## 🛠 Components

### 🔍 Scraping Script — `main.py`
Automates data collection from Airbnb using Chrome WebDriver. It extracts and saves the following data into CSV files:
- Listing Titles (`airbnb_listings.csv`)
- Prices (`airbnb_prices.csv`)
- Ratings (`airbnb_listings_ratings.csv`)
- Beds (`airbnb_listings_beds.csv`)
- Names (`airbnb_listings_names.csv`)
- Listing Links (`airbnb_listings_links.csv`)

### 🧹 Cleaning & Merging Script — `Cleaning.py`
- Converts prices from "XX $ par nuit" format to numeric values.
- Loads all CSV files and merges them into one final Excel file: `combined_airbnb_listings.xlsx`.

---

## 📦 Output Files

After running the full pipeline, the following files are generated:

| File Name                     | Description                                |
|------------------------------|--------------------------------------------|
| `airbnb_listings.csv`        | Titles of Airbnb listings                  |
| `airbnb_prices.csv`          | Prices per night (raw text format)         |
| `airbnb_listings_beds.csv`   | Number of beds                             |
| `airbnb_listings_names.csv`  | Display names of listings                  |
| `airbnb_listings_links.csv`  | URLs of each listing                       |
| `airbnb_listings_ratings.csv`| User ratings                               |
| `combined_airbnb_listings.xlsx` | Final cleaned dataset with merged info |

---

## 🚀 How to Run the Project

### 📌 Prerequisites
- Python 3.7+
- Google Chrome browser
- ChromeDriver (managed automatically by `webdriver-manager`)
- Install required libraries:
```bash
pip install selenium pandas webdriver-manager openpyxl
```

### 🖥️ Step-by-Step Execution

1. **Run the scraping script:**
```bash
python main.py
```
This will launch a browser window and begin scraping data from Airbnb.

2. **Run the cleaning script:**
```bash
python Cleaning.py
```
This script loads the raw CSVs, converts price strings to numeric, merges all datasets, and saves the final Excel file.

---

## 💡 Notes

- The scraper currently targets a fixed search result for **Jardins De Carthage, Tunisia**, for a given travel window. You can change the URL in `main.py` to scrape another location or date.
- Make sure the page is fully loaded before scraping; the script waits 15 seconds (`sleep(15)`) before starting extraction.
- Running the script multiple times appends to the same CSVs, which may result in duplicate entries.
