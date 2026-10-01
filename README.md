# ReadBridge Scraper - Books to Scrape Capstone

This script scrapes the first 10 pages (200 books) from https://books.toscrape.com

### What it does:
1. Loops through pages 1-10 using `requests` with a `safe_get()` function for error handling.
2. Parses book Title, Price, Star Rating, Availability, and URL using BeautifulSoup.
3. Builds a raw DataFrame (200 x 5).
4. Cleans data: Price to NUMERIC, Rating word to INTEGER, adds `page_number` and `scraped_at`.
5. Loads data to PostgreSQL table `books_catalogue` using SQLAlchemy and verifies row count.

### How to run it:
```bash
pip install requests beautifulsoup4 lxml sqlalchemy psycopg2-binary pandas
jupyter notebook scraper.ipynb
