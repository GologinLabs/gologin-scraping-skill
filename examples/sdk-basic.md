# SDK Basic

Goal:
Use the Node.js SDK directly inside application code.

```ts
import { WebUnlocker } from "gologin-webunlocker-sdk";

const client = new WebUnlocker({
  apiKey: process.env.GOLOGIN_WEBUNLOCKER_API_KEY!
});

const html = await client.scrape("https://example.com");
const text = await client.scrapeText("https://example.com");
const data = await client.scrapeJSON("https://example.com");
```
