# Jobs Scrapping

A bot that scrapes job positions from a specific website and standardizes the data.

## Functional Requirements (FR):

-   **FR01 (Target)**: Scrape a specific job board or aggregator (e.g., a "Who is hiring" thread, a specific company's career page, or a generic board like LinkedIn/Indeed - *respecting robots.txt*).
-   **FR02 (Extraction)**: Extract key details: Job Title, Company, Location, Salary (if available), and Link.
-   **FR03 (Storage)**: Save the scraped jobs into a structured format (Database or CSV/JSON file).
-   **FR04 (Filtering)**: Allow basic filtering (e.g., only "Remote" jobs or "Junior" positions).

## Non-Functional Requirements (NFR):

-   **NFR01 (Ethical Scrapping)**: Respect rate limits and `robots.txt`. Do not DDOS the target site.
-   **NFR02 (Headless Browser)**: Use tools like Puppeteer, Playwright, or Selenium if the site requires JavaScript rendering. Otherwise, use standard HTTP libraries (axios/requests) + HTML parsers (cheerio/BeautifulSoup) for speed.
-   **NFR03 (Scheduling)**: The bot should be able to run on a schedule (e.g., every 6 hours) via cron or an internal timer.
