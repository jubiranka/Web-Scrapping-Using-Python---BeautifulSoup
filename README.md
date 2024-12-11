# Web Scraping Using Python - BeautifulSoup

## Project Description

**Web Scraping Using Python - BeautifulSoup** is a project that focuses on extracting data for **Sony Headphones** available on Amazon India. The project demonstrates the use of Python libraries such as `BeautifulSoup`, `requests`, and `pandas` to scrape and analyze e-commerce data effectively.

---

## Features

- **Data Extraction**:
  - Scrapes product details such as names, prices, and ratings for Sony headphones on Amazon India.
- **Dynamic Web Content Handling**:
  - Uses headers to simulate a browser request for accessing the data.
- **Data Storage**:
  - Stores the scraped data in a structured format using `pandas`.
- **Timestamping**:
  - Includes timestamps to keep track of when the data was scraped.

---

## Technologies Used

- **Python Libraries**:
  - `BeautifulSoup` for parsing HTML and extracting data.
  - `requests` for making HTTP requests.
  - `pandas` and `numpy` for data manipulation and storage.
  - `datetime` for timestamp management.

---

## Steps Performed

1. **Importing Libraries**:
   Essential libraries for web scraping and data manipulation are imported.

   ```python
   import pandas as pd
   from bs4 import BeautifulSoup
   import requests
   import time
   import datetime
   import numpy as np
   ```

2. **Connecting to Amazon and Pulling Data**:
   - The script connects to the Amazon website using the `requests` library and scrapes the webpage content.
   ```python
   URL = "https://www.amazon.in/s?k=headphones&rh=n%3A976419031%2Cp_123%3A237204&dc"
   Header = {"User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64)"}
   page = requests.get(URL, headers=Header)
   ```

3. **Parsing HTML with BeautifulSoup**:
   - HTML content is parsed to extract product names, prices, and ratings.
   ```python
   soup = BeautifulSoup(page.content, 'html.parser')
   ```

4. **Storing Data**:
   - Scraped data is cleaned, structured, and stored in a DataFrame using `pandas`.
   ```python
   data = pd.DataFrame({
       'Product Name': product_names,
       'Price': prices,
       'Rating': ratings
   })
   ```

5. **Exporting Data**:
   - The cleaned data is exported to a CSV file for further analysis.
   ```python
   data.to_csv('sony_headphones_data.csv', index=False)
   ```

---

## Installation and Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/jubiranka/Web-Scrapping-Using-Python---BeautifulSoup
   ```

2. Install required dependencies:
   Generate the `requirements.txt` file if it is not already included:
   ```bash
   pip freeze > requirements.txt
   ```
   Then install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the script:
   ```bash
   python Web scrapping Amazon Data.ipynb
   ```

---

## Screenshots

- **Scraped Data Example**:

  ![Sample Output](https://github.com/jubiranka/Web-Scrapping-Using-Python---BeautifulSoup/blob/main/Amazon%20Sony%20Headphones%20Scrapped%20Data.png)

---

## Limitations

- The script does not handle dynamic JavaScript-rendered content.
- Amazon's anti-scraping measures can occasionally block requests.
- Limited to publicly available product data.

---

## Future Enhancements

- Integrate dynamic content handling using Selenium or Playwright.
- Add functionality to scrape multiple product categories.
- Automate periodic scraping and analysis.

---



## Acknowledgments

Special thanks to the creators of BeautifulSoup, requests, and pandas for their powerful libraries that made this project possible.
