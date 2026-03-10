# Batch Scrape

Use this workflow when multiple URLs should be fetched inside one SDK-driven pass.

1. Initialize `WebUnlocker` once.
2. Call `batchScrape(urls, { concurrency })`.
3. Handle typed errors at the application boundary if retries or fallback logic matter.
