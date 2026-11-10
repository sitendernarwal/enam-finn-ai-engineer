# FINN — AI Engineer build challenge

A responsive prototype for two investor workflows: a prioritized Push brief and Pull company research grounded in primary-source discovery links.

**Live demo:** https://sitendernarwal.github.io/enam-finn-ai-engineer/  
**Public repository:** https://github.com/sitendernarwal/enam-finn-ai-engineer

## Run locally

Open `index.html` in a browser, or serve this folder with `python3 -m http.server 8000` and visit `http://localhost:8000`.

## Demo flows

- Filter a four-item daily brief by filings or market moves; open an item to continue into company research.
- Search the sample companies, review business snapshots, illustrative financial trends, and bull/bear cases.
- Follow a company and adjust the demo alert thresholds.
- Use `⌘K` / `Ctrl+K` to jump to research.

## Data and limitations

The mock portfolio contains 16 companies; six have illustrative research figures and ten are watchlist placeholders. This is a static front-end demo with no backend or live market feed. Displayed prices, financial values, and alerts are illustrative. The sample Push/Pull content is not verified market research. Source links lead to public exchange, market data, or company-document discovery pages rather than specific filings. Do not treat the prototype as investment advice.

## Architecture

Use deterministic code for calculations and thresholds. In a production version, ingest end-of-day market prices and volume, NSE/BSE announcements, and company fundamentals from primary documents. Keep source URLs and reporting periods with each claim; use an LLM only to summarize retrieved evidence, never as the source of a financial figure. The prototype makes no model calls and needs no paid services to run.

See [DEPLOYMENT.md](DEPLOYMENT.md) for static-host steps. See [SUBMISSION_CHECKLIST.md](SUBMISSION_CHECKLIST.md) for an honest status of each assignment checkpoint, plus [COVERING_NOTE.md](COVERING_NOTE.md) and [AI_BUILD_HISTORY.md](AI_BUILD_HISTORY.md) drafts.
