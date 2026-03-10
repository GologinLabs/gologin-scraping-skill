# Gologin Web Unlocker Skill

## Install This Skill

Install the skill with:

```bash
npx skills add GologinLabs/gologin-webunlocker-skill@gologin-webunlocker-skill
```

Standalone repo:

- [GologinLabs/gologin-webunlocker-skill](https://github.com/GologinLabs/gologin-webunlocker-skill)

## Required Package Or CLI

This skill is built around the `gologin-webunlocker-sdk` package.

Install the SDK in a Node.js project:

```bash
npm install gologin-webunlocker-sdk
```

If you want the CLI directly in your shell:

```bash
npm install -g gologin-webunlocker-sdk
```

Package:

- `gologin-webunlocker-sdk`

CLI command:

- `gologin-webunlocker`

## Overview

Gologin Web Unlocker Skill is a scraping-only skill for AI agents and developers who need read-only web access through Gologin Web Unlocker.

It is built for:

- rendered HTML retrieval
- text extraction
- markdown extraction
- structured metadata extraction
- client-side batch scraping helpers

It does not cover browser sessions, clicks, or login flows. For that, use `gologin-agent-browser-skill` or `gologin-web-access-skill`.

## Capabilities

- Raw HTML access with `scrape`
- Text extraction with `text`
- Markdown extraction with `markdown`
- Metadata extraction with `json`
- SDK methods for `scrapeRaw()`, `scrape()`, `scrapeText()`, `scrapeMarkdown()`, `scrapeJSON()`, `batchScrape()`, and `buildScrapeUrl()`
- Typed error handling for authentication, rate limits, API failures, timeouts, and network errors

## Setup

Set your API key:

```bash
export GOLOGIN_WEBUNLOCKER_API_KEY="your_web_unlocker_key"
```

You can also pass `--api-key` to the CLI directly.

## Quickstart

CLI:

```bash
gologin-webunlocker markdown https://example.com
```

SDK:

```ts
import { WebUnlocker } from "gologin-webunlocker-sdk";

const client = new WebUnlocker({
  apiKey: process.env.GOLOGIN_WEBUNLOCKER_API_KEY!
});

const result = await client.scrapeMarkdown("https://example.com");
console.log(result.markdown);
```

## When To Use This Skill

Use this skill when:

- the task is scraping-only
- no browser session is needed
- the target system is a Node.js app that should call the SDK directly
- you want a smaller, narrower skill than `gologin-web-access-skill`

## References

- [`SKILL.md`](./SKILL.md)
- [`tools.md`](./tools.md)
- [`examples/`](./examples)
- [`workflows/`](./workflows)
