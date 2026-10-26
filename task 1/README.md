# HanuAI Task 1 - BestBuy.ca Reviews: Sentiment Analysis

Product analysed: Samsung Essential F320 27" monitor (BestBuy.ca SKU 19277986), 55 unique public reviews.

## 1. One-time setup (VS Code)
1. Install Python 3.10+, Google Chrome, VS Code + the **Python** and **Jupyter** extensions.
2. Open this folder in VS Code, then in the terminal:
   ```
   python -m venv venv
   venv\Scripts\activate          (Mac/Linux: source venv/bin/activate)
   pip install -r requirements.txt
   ```
3. Open `task1_scrape_sentiment.ipynb` -> top-right **Select Kernel** -> choose the `venv` interpreter.

## 2. Run it
1. Make sure the saved review page (`.html`) is in the `saved_pages/` folder.
2. Click **Restart**, then **Run All**. No edits and no browser are needed.

## 3. How the reviews were collected
- BestBuy's bot protection returned "Access Denied" to the automated Selenium browser. This was respected and not bypassed.
- The public review pages were opened in a normal browser session, every review was loaded with "Show more", and each page was saved (Ctrl+S -> Webpage, Complete) into `saved_pages/`.
- The notebook parses the saved pages with BeautifulSoup. The Selenium and JSON-endpoint code (Parts 2 and 3) is kept as the intended automated method.
- Only public review content is used. robots.txt was checked, and the only personal data is the public display name.

## 4. Files
| File | What it is |
|---|---|
| `task1_scrape_sentiment.ipynb` | Code with explanations, outputs saved |
| `task1_scrape_sentiment.html` | Same notebook as a web page, outputs included |
| `data/bestbuy_reviews_sentiment.csv` / `.xlsx` | Deliverable: scraped fields + sentiment categorisation |
| `data/bestbuy_reviews_raw.csv` | Parsed reviews before cleaning |
| `charts/*.png` | Figures used in the report |
| `Task 1 Report.pdf` | Scraping challenges, insights, recommendations |

## 5. Method in brief
- **Cleaning:** primary key (hash of title/text/reviewer/date/rating), dates as YYYY-MM-DD, duplicates removed (110 cards -> 55 reviews).
- **Sentiment:** VADER score averaged with the star rating, plus aspect tags (for example `Display & Picture Quality (Pos)`).
- **Data notes:** 42 reviews have written text and 13 are rating-only (`HAS_TEXT = False`); 7 are promotional (`PROMOTED = True`).
- **Validation:** text-only sentiment agrees with the stars on 83% of the 42 reviews with text; 28 of 33 checkable aspect tags were correct in a 20-review hand check.

## 6. If something fails
| Symptom | Fix |
|---|---|
| `ModuleNotFoundError` | Wrong kernel: re-select the `venv` kernel, or run `pip install -r requirements.txt` |
| "No reviews parsed" | Put the saved `.html` page in `saved_pages/`; run `inspect_saved_html()` to check the class names |
| Garbled characters in Excel | Files are saved as `utf-8-sig`; open the `.xlsx` instead |