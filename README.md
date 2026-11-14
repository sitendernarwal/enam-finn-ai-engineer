# FINN — AI Engineer build challenge

A responsive prototype for two investor workflows: a prioritized Push brief and Pull company research grounded in primary-source discovery links.

**Live demo:** https://sitendernarwal.github.io/enam-finn-ai-engineer/  
**Public repository:** https://github.com/sitendernarwal/enam-finn-ai-engineer

## Run locally

Open `index.html` in a browser, or serve this folder with `python3 -m http.server 8000` and visit `http://localhost:8000`.

The phone layout includes persistent bottom navigation. Dark mode is the default, with a remembered light-mode option. Charts display illustrative data only; no live market feed is connected.

## AI research assistant

The Research view includes Ask FINN. Its shared server-side API runs on Vercel; GitHub Pages serves only the static interface. The API retrieves recent official NSE disclosures and uses Gemini 3.5 Flash-Lite with URL Context to summarize the linked filing documents. The API key stays in Vercel. See [AI_IMPLEMENTATION_ROADMAP.md](AI_IMPLEMENTATION_ROADMAP.md) for the phases and free-tier setup.

## Demo flows

- Filter a four-item daily brief by filings or market moves; open an item to continue into company research.
- Search the sample companies, review the quarterly revenue chart, illustrative calculations, and bull/bear cases.
- Browse the 16-company Portfolio, search by name or sector, and add or remove companies from a device-local Watchlist.
- Follow a company from research and adjust the demo alert thresholds.
- Use `⌘K` / `Ctrl+K` to jump to research.
- Review the simulated NIFTY 50 pulse and synchronized dashboard quotes.

## Data and limitations

The mock portfolio contains 16 tracked companies; six have illustrative research figures and ten remain source-lookup placeholders. No live market feed is connected. Displayed prices, financial values, and alerts are illustrative; Ask FINN searches the web and displays only validated NSE/BSE citations, but may not find a relevant official filing for every question. Portfolio quantities, purchase prices, value, and returns are not provided. Watchlist choices are saved in this browser on this device, not synced to an account. Existing source links lead to public exchange, market data, or company-document discovery pages rather than specific filings. Do not treat the prototype as investment advice.

## Architecture

Use deterministic code for calculations and thresholds. Ask FINN uses Gemini 3.5 Flash-Lite with URL Context to read specific official NSE filings returned for the selected ticker. In a production version, ingest company fundamentals from primary documents. Keep source URLs and reporting periods with each claim; use an LLM only to summarize retrieved evidence, never as the source of a financial figure.

See [DEPLOYMENT.md](DEPLOYMENT.md) for static-host steps. See [SUBMISSION_CHECKLIST.md](SUBMISSION_CHECKLIST.md) for an honest status of each assignment checkpoint. The [COVERING_NOTE.md](COVERING_NOTE.md) and [AI_BUILD_HISTORY.md](AI_BUILD_HISTORY.md) are ready to include with the submission.
