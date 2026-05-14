# Tool Contracts

This skill is a scraping-only wrapper around the `gologin-scraping-api` package and `gologin-scraping-api` CLI.

## Summary

| Skill tool | Surface | Requires | Returns |
| --- | --- | --- | --- |
| `scraping_api_scrape` | `scrape` / `scrape()` | `GOLOGIN_SCRAPING_API_KEY` | Raw HTML or content |
| `scraping_api_text` | `text` / `scrapeText()` | `GOLOGIN_SCRAPING_API_KEY` | Plain text |
| `scraping_api_markdown` | `markdown` / `scrapeMarkdown()` | `GOLOGIN_SCRAPING_API_KEY` | Markdown |
| `scraping_api_json` | `json` / `scrapeJSON()` | `GOLOGIN_SCRAPING_API_KEY` | Structured metadata |
| `scraping_api_batch_scrape` | `batchScrape()` | `GOLOGIN_SCRAPING_API_KEY` | Array of scrape results |
| `scraping_api_scrape_raw` | `scrapeRaw()` | `GOLOGIN_SCRAPING_API_KEY` | Native `Response` |
| `scraping_api_build_scrape_url` | `buildScrapeUrl()` | Absolute target URL | Fully formed backend request URL |

## scraping_api_scrape

CLI:

```bash
gologin-scraping-api scrape "https://example.com"
```

SDK:

```ts
const result = await client.scrape("https://example.com");
```

Use when:
Raw HTML or the original returned page content is required.

## scraping_api_text

CLI:

```bash
gologin-scraping-api text "https://example.com"
```

SDK:

```ts
const result = await client.scrapeText("https://example.com");
```

Use when:
Plain text output is preferred over HTML.

## scraping_api_markdown

CLI:

```bash
gologin-scraping-api markdown "https://example.com"
```

SDK:

```ts
const result = await client.scrapeMarkdown("https://example.com");
```

Use when:
Readable markdown is needed for articles, docs, or LLM processing.

## scraping_api_json

CLI:

```bash
gologin-scraping-api json "https://example.com"
```

SDK:

```ts
const result = await client.scrapeJSON("https://example.com");
```

Use when:
Metadata and extracted links are enough.
