# SDK Basic

Goal:
Use the Node.js SDK directly inside application code.

```ts
import { ScrapingApi } from "gologin-webunlocker";

const client = new ScrapingApi({
  apiKey: process.env.GOLOGIN_SCRAPING_API_KEY!
});

const html = await client.scrape("https://example.com");
const text = await client.scrapeText("https://example.com");
const data = await client.scrapeJSON("https://example.com");
```
