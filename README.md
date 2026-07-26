# Web Scraper — Books & Quotes

Two Python web scrapers built with `requests` and `BeautifulSoup` that extract structured data from paginated websites and export it to CSV.

## Projects

### 1. Books Scraper (`books_scraper.ipynb`)
Scrapes all 1,000 books from [books.toscrape.com](https://books.toscrape.com) across 50 catalogue pages.

- Downloads and caches raw HTML locally before parsing (so a failed request doesn't force a full re-scrape)
- Extracts title, price, and star rating for each book
- Exports to `data1.csv`

### 2. Quotes Scraper (`quotes_scraper.ipynb`)
Scrapes quotes, authors, and tags from [quotes.toscrape.com](https://quotes.toscrape.com) across 10 pages.

- Extracts quote text, author, and tag list for each quote
- Exports to `data2.csv`

## Design notes
- **Fetch/parse separation**: HTML is downloaded once and cached to disk, then parsed independently — this avoids hammering the server on repeated runs and makes the parsing step easy to debug offline.
- **Error handling**: failed requests and malformed entries are caught and logged rather than crashing the whole run.

## Setup

```bash
pip install -r requirements.txt
```

Then run either notebook top to bottom.

## Tech stack
Python · requests · BeautifulSoup4 · pandas
