# PRICE COMPARISON TOOL - PROJECT SUMMARY
Project Title: Laptop Price Comparison across E-commerce Sites
Organization: NewtonAI Technologies
Submission Date: February 14, 2026

## OVERVIEW:
This project implements a web scraping solution to compare laptop prices
across Flipkart and Amazon India using Python, Selenium, and BeautifulSoup.

## SCRAPING LOGIC:
1. Uses Selenium WebDriver (Firefox) to handle dynamic JavaScript content
2. BeautifulSoup parses the rendered HTML to extract product data
3. Anti-detection measures prevent bot blocking:
   - Custom user agent
   - Disabled webdriver flags
   - Human-like delays between requests

4. For each platform:
   - Searches for user-specified laptop model
   - Extracts top 10 results
   - Parses: Product Name, Price, Rating, Product Link
   - Handles missing fields gracefully

5. Data Processing:
   - Combines results from both platforms
   - Cleans price data (removes ₹, commas)
   - Exports to CSV with timestamp

6. Visualization:
   - Generates bar chart comparing prices
   - Shows side-by-side comparison of top 5 products

## ERROR HANDLING:
- Missing product names/prices: Skipped with warning
- Login popups: Automatically closed
- CAPTCHA: Manual intervention prompt
- Network errors: Graceful failure with error messages

## LIBRARIES USED:
- selenium: Browser automation
- beautifulsoup4: HTML parsing
- pandas: Data manipulation
- matplotlib: Chart generation
- re: Price extraction

## Installation Instructions:
```
# Install required packages
pip3 install selenium beautifulsoup4 pandas matplotlib lxml

# Install GeckoDriver (macOS)
brew install geckodriver
xattr -d com.apple.quarantine $(which geckodriver)

# Run the script
python3 scrape.py
```

## USAGE:
python3 scrape.py

Then enter laptop model when prompted.

## OUTPUT FILES:
1. laptop_price_comparison_YYYYMMDD_HHMMSS.csv
2. price_comparison_chart_YYYYMMDD_HHMMSS.png
