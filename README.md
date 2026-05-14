# Gologin Scraping Skill

## Install This Skill

Install the skill with:

```bash
npx skills add GologinLabs/gologin-scraping-skill
```

Monorepo install:

```bash
npx skills add GologinLabs/agent-skills@gologin-scraping-skill
```

## Required Package Or CLI

This skill is built around the `gologin-scraping-api` package.

Install the SDK in a Node.js project:

```bash
npm install gologin-scraping-api
```

If you want the CLI directly in your shell:

```bash
npm install -g gologin-scraping-api
```

Package:

- `gologin-scraping-api`

CLI command:

- `gologin-scraping-api`
- `gologin-webunlocker` legacy alias

Package repo:

- [GologinLabs/gologin-scraping-api](https://github.com/GologinLabs/gologin-scraping-api)

## Overview

Gologin Scraping Skill is a scraping-only skill for AI agents and developers who need read-only web access through the GoLogin Scraping API.

It is built for:

- raw HTML retrieval
- text extraction
- markdown extraction
- structured metadata extraction
- client-side batch scraping helpers

It does not cover browser sessions, clicks, screenshots, or login flows. For that, use `gologin-agent-browser-skill` or `gologin-web-access-skill`.

## Setup

Set your API key:

```bash
export GOLOGIN_SCRAPING_API_KEY="your_scraping_api_key"
```

Legacy env alias:

```bash
export GOLOGIN_WEBUNLOCKER_API_KEY="your_scraping_api_key"
```

You can also pass `--api-key` to the CLI directly.

## Quickstart

CLI:

```bash
gologin-scraping-api markdown https://example.com
```

SDK:

```ts
import { ScrapingApi } from "gologin-scraping-api";

const client = new ScrapingApi({
  apiKey: process.env.GOLOGIN_SCRAPING_API_KEY!
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
