# Web Scraper Project

This project contains Python scripts for web scraping using BeautifulSoup and Selenium.

## Setup

### 1. Virtual Environment
The project uses a Python virtual environment with Python 3.13.2:

```bash
# Activate the virtual environment
source venv/bin/activate

# Deactivate when done
deactivate
```

### 2. Installed Libraries
- `beautifulsoup4` (4.14.3) - HTML/XML parsing
- `requests` (2.32.5) - HTTP requests
- `lxml` (6.0.2) - Fast XML/HTML parser
- `html5lib` (1.1) - HTML5 parser

### 3. Optional: Selenium (for JavaScript-heavy sites)
```bash
pip install selenium webdriver-manager
```

## Files

### 1. `scraper.py` - Basic T-Mobile Scraper
Attempts to scrape T-Mobile reviews from ConsumerAffairs using requests.

**Note:** This site has anti-bot protection and may not work reliably.

```bash
python scraper.py
```

### 2. `scraper_selenium.py` - Advanced Selenium Scraper
Uses Selenium with Chrome WebDriver to handle JavaScript-rendered content.

**Requirements:**
```bash
pip install selenium webdriver-manager
```

**Usage:**
```bash
python scraper_selenium.py
```

### 3. `demo_scraper.py` - Working Demo
Scrapes from `quotes.toscrape.com` (a site that allows scraping) to demonstrate functionality.

```bash
python demo_scraper.py
```

## About ConsumerAffairs Anti-Bot Protection

The target website (https://www.consumeraffairs.com) has anti-bot protection that blocks automated scraping. Here are alternative approaches:

### Option 1: Use Selenium (Included)
The `scraper_selenium.py` file uses a browser automation approach that may work better.

### Option 2: Use Scraping API Services
- [ScrapingBee](https://www.scrapingbee.com/)
- [ScraperAPI](https://www.scraperapi.com/)
- [Bright Data](https://brightdata.com/)

### Option 3: Manual Data Collection
1. Open the page in your browser
2. Use browser DevTools to inspect the HTML
3. Copy the data manually
4. Format it as needed

### Option 4: Check for Official API
Visit ConsumerAffairs' developer documentation to see if they offer an official API.

## Output

All scrapers save data to CSV files:
- `tmobile_reviews.csv` - Basic scraper output
- `tmobile_reviews_selenium.csv` - Selenium scraper output
- `demo_quotes.csv` - Demo scraper output

## CSV Format

The output CSV files contain:
- `title` - Review title or quote
- `rating` - Star rating (if available)
- `author` - Review author or quote author
- `date` - Review date
- `content` - Full review text or quote

## Legal & Ethical Considerations

⚠️ **Important:**
1. Always check the website's `robots.txt` file
2. Review the site's Terms of Service
3. Respect rate limits and don't overload servers
4. Consider using official APIs when available
5. Some websites prohibit automated scraping

## Troubleshooting

### "Access Denied" or 403 Errors
The website is blocking automated requests. Try:
- Using Selenium instead of requests
- Adding delays between requests
- Using a scraping API service

### Chrome Driver Issues
If Selenium fails to find Chrome:
```bash
pip install --upgrade webdriver-manager
```

## Dependencies

See `requirements.txt` for all Python dependencies:
```bash
pip install -r requirements.txt
```
