# 🌍 Global News Intelligence Dashboard

An AI-powered daily news briefing dashboard that fetches and summarizes global headlines across every major industry — powered by Claude AI with live web search.

**[→ View Live Demo](https://your-username.github.io/global-news-dashboard)**

---

## Features

- **8 Industry categories** — Technology, Finance, Healthcare, Energy, Geopolitics, Retail, Manufacturing
- **Sub-filters** — AI, Regulatory, Markets, M&A, Climate, Crypto, and more
- **AI summaries** — 2-3 sentence plain-English digest of each story
- **Source links** — Direct link to the original article
- **Live web search** — Powered by Claude claude-sonnet-4-20250514 with real-time web search
- **Dark mode** — Automatic based on system preference
- **Daily auto-refresh** — GitHub Actions refreshes a static cache every day

---

## Deploy in 5 Minutes

### Step 1 — Fork this repository

Click **Fork** at the top right of this page.

### Step 2 — Add your Anthropic API key

1. Go to **Settings → Secrets and variables → Actions**
2. Click **New repository secret**
3. Name: `ANTHROPIC_API_KEY`
4. Value: your key from [console.anthropic.com](https://console.anthropic.com)

> Get a free API key at https://console.anthropic.com

### Step 3 — Enable GitHub Pages

1. Go to **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `main`, folder: `/ (root)`
4. Click **Save**

### Step 4 — Done!

Your dashboard will be live at:
```
https://your-username.github.io/global-news-dashboard
```

---

## How it works

The dashboard calls the Anthropic API directly from the browser using your API key. Claude uses its built-in web search tool to find real, current news stories and returns structured JSON with title, summary, source, URL, and category tags.

The GitHub Action (`.github/workflows/daily-refresh.yml`) runs every day at 6:00 AM UTC and triggers a cache warm-up so the first page load is fast.

---

## Project structure

```
global-news-dashboard/
├── index.html                        # Main dashboard (single file, no build step)
├── README.md                         # This file
└── .github/
    └── workflows/
        └── daily-refresh.yml         # GitHub Action for daily updates
```

---

## Customization

Open `index.html` and edit the `INDUSTRIES` and `SUBFILTERS` objects to add your own categories:

```js
const INDUSTRIES = [
  { id: 'myindustry', label: 'My Industry', icon: 'ti-building' },
  // ...
];

const SUBFILTERS = {
  myindustry: ['Sub A', 'Sub B', 'Sub C'],
};
```

Icons come from [Tabler Icons](https://tabler.io/icons) — search for any icon name and use it as `ti-icon-name`.

---

## License

MIT — free to use, share, and modify.
