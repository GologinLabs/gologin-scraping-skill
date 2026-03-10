# Tool Contracts

This skill is a scraping-only wrapper around the `gologin-webunlocker-sdk` package and `gologin-webunlocker` CLI.

## Summary

| Skill tool | Surface | Requires | Returns |
| --- | --- | --- | --- |
| `webunlocker_scrape` | `scrape` / `scrape()` | `GOLOGIN_WEBUNLOCKER_API_KEY` | Raw HTML or content |
| `webunlocker_text` | `text` / `scrapeText()` | `GOLOGIN_WEBUNLOCKER_API_KEY` | Plain text |
| `webunlocker_markdown` | `markdown` / `scrapeMarkdown()` | `GOLOGIN_WEBUNLOCKER_API_KEY` | Markdown |
| `webunlocker_json` | `json` / `scrapeJSON()` | `GOLOGIN_WEBUNLOCKER_API_KEY` | Structured metadata |
| `webunlocker_batch_scrape` | `batchScrape()` | `GOLOGIN_WEBUNLOCKER_API_KEY` | Array of scrape results |
| `webunlocker_scrape_raw` | `scrapeRaw()` | `GOLOGIN_WEBUNLOCKER_API_KEY` | Native `Response` |
| `webunlocker_build_scrape_url` | `buildScrapeUrl()` | Absolute target URL | Fully formed backend request URL |

## webunlocker_scrape

CLI:

```bash
gologin-webunlocker scrape "https://example.com"
```

SDK:

```ts
const result = await client.scrape("https://example.com");
```

Use when:
Raw HTML or the original returned page content is required.

## webunlocker_text

CLI:

```bash
gologin-webunlocker text "https://example.com"
```

SDK:

```ts
const result = await client.scrapeText("https://example.com");
```

Use when:
Plain text output is preferred over HTML.

## webunlocker_markdown

CLI:

```bash
gologin-webunlocker markdown "https://example.com"
```

SDK:

```ts
const result = await client.scrapeMarkdown("https://example.com");
```

Use when:
Readable markdown is needed for articles, docs, or LLM processing.

## webunlocker_json

CLI:

```bash
gologin-webunlocker json "https://example.com"
```

SDK:

```ts
const result = await client.scrapeJSON("https://example.com");
```

Returns a structured object with:

- `title`
- `description`
- `canonical`
- `meta`
- `headings`
- `links`

Use when:
Metadata and extracted links are enough.

## webunlocker_batch_scrape

SDK:

```ts
const results = await client.batchScrape(
  ["https://example.com", "https://gologin.com"],
  { concurrency: 2 }
);
```

Use when:
Multiple URLs should be fetched in one client-side helper flow.

## webunlocker_scrape_raw

SDK:

```ts
const response = await client.scrapeRaw("https://example.com");
const html = await response.text();
```

Use when:
The caller needs direct access to the native `Response`, status, or headers.

## webunlocker_build_scrape_url

SDK:

```ts
const requestUrl = client.buildScrapeUrl("https://example.com");
```

Use when:
The exact request URL sent to Web Unlocker should be inspected or logged.
