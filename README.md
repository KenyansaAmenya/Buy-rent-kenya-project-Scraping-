# Buy-rent-kenya-project-Scraping- At LUXDEVHQ Workshop
# Web Scraping for Real Estate Data & Power BI Dashboard

This project demonstrates how to scrape real estate data from [BuyRentKenya](https://www.buyrentkenya.com), store it in a PostgreSQL database, and visualize it in Power BI. The workshop was conducted at LUXDEVHQ.

## Project Overview

The project consists of:
1. Python web scraper for house listings
2. PostgreSQL database integration
3. Power BI dashboard for data visualization

## Technologies Used
- Python 3
- Libraries:
  - `requests` (HTTP requests)
  - `BeautifulSoup` (HTML parsing)
  - `pandas` (data manipulation)
  - `sqlalchemy` (database connection)
- PostgreSQL (database)
- Power BI (visualization)

## Data Pipeline
1. **Web Scraping**: Extracts house listing data including:
   - Title
   - Price
   - Location
   - Bedrooms
   - Bathrooms
   - Size
2. **Data Storage**: Stores cleaned data in PostgreSQL
3. **Visualization**: Connects Power BI to PostgreSQL for dashboard creation

## Code Structure

### Main Script (`web_scraper.ipynb`)
```python
import requests
from bs4 import BeautifulSoup
import pandas as pd
from sqlalchemy import create_engine

def scrape_pages(start_page, end_page):
    # Scrapes house listings from BuyRentKenya
    # Returns pandas DataFrame
    
# Database connection
engine = create_engine("postgresql://postgres:12345@localhost:5432/postgres")

# Scrape data (pages 2-7)
df = scrape_pages(start_page=2, end_page=7)

# Store in PostgreSQL
df.to_sql('house_details', engine, if_exists='replace', index=False, schema='houses')

# Database Setup
PostgreSQL database with:

* Database name: postgres

* Table name: house_details (in schema houses)

* Connection string: postgresql://postgres:12345@localhost:5432/postgres

# Power BI Integration
Connect Power BI to PostgreSQL database

Create visualizations showing:

* Price distribution
* Location analysis
* Bedroom/bathroom statistics
* Size vs. price correlations

# How to Use
Clone this repository

# Install requirements:
* pip install requests beautifulsoup4 pandas sqlalchemy psycopg2
* Ensure PostgreSQL is running
* Run the Jupyter notebook to scrape data
* Open Power BI and connect to your PostgreSQL database
# Sample Data
Here's a sample of the scraped data:

* Title	Price	Location	Bedrooms	Bathrooms	Size
5 Bed Townhouse in Lavington	KSh 130,000,000	Lavington	5 Bedrooms	6 Bathrooms	N/A
4 Bed House at Kiambu Road	KSh 20,000,000	Runda	4 Bedrooms	5 Bathrooms	N/A
# Workshop Notes
* Data was scraped from pages 2-7 of BuyRentKenya's house listings

* The scraper handles pagination and extracts key property features

* Data is cleaned and stored in PostgreSQL for analysis

# Future Improvements
* Add error handling for failed requests

* Implement scheduled scraping

* Enhance data cleaning (extract numeric values from text)

* Add more visualizations in Power BI

# Credits
Workshop conducted at LUXDEVHQ
