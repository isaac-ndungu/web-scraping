# Jumia Flash Sales Scraper

A Python web scraper that extracts product data from [Jumia Kenya's Flash Sales](https://www.jumia.co.ke/flash-sales) page and saves it to a CSV file.



## Overview

This tool automates a browser session to visit each product listed on the Jumia flash sales page, extract key details from the individual product pages, and compile the results into a structured CSV file.


## Data Collected

For each product, the following fields are captured:

- **Product Name** - Full product title
- **New Price** - Current discounted price
- **Old Price** - Original price before discount
- **Discount (%)** - Percentage discount applied
- **Brand** - Product brand
- **Items Left** - Remaining stock count
- **Rating** - Average customer star rating
- **Time Left** - Remaining time on the flash deal

## Requirements

- Python 3.7+
- Google Chrome browser
- Jupyter Notebook

Install dependencies:

```bash
pip install selenium webdriver-manager bs4 jupyter
```

## Usage

Open `main.ipynb` in Jupyter and run all cells: 

The browser will open automatically, navigate through all pages of the flash sales listing, visit each product page, and print progress as each product is scraped. Once complete, results are saved to `products.csv` in the working directory.


## Output

A CSV file (`products.csv`) with one row per product and the columns listed above.


## How It Works

1. Opens the Jumia flash sales listing page
2. Finds all product cards on the current page 
3. For each product, extracts the product URL and navigates to it
4. Scrapes the required fields from the product page using BeautifulSoup
5. Returns to the listing page and moves to the next product
6. Paginates through all available pages
7. Writes all collected data to `products.csv` on completion

