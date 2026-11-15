# FINN architecture and data boundaries

## Current prototype

FINN is a static HTML, CSS, and JavaScript frontend hosted with GitHub Pages. Both assignment builds use the shared serverless API at `finn-ai-api` on Vercel.

```text
Mobile / desktop browser
  ├─ Market and company research ──> Vercel /api/market-data ──> NSE MCP
  └─ Ask FINN ─────────────────────> Vercel /api/ask-company ──> NSE disclosures + Gemini
```

- **Market data:** The API retrieves official NSE index, quote, end-of-day history, and market-mover data. It returns a dated end-of-day snapshot when live movers are unavailable. The UI does not substitute sample prices.
- **Company research:** Displays returned NSE quotes, historical closes, announcement metadata, and links to NSE filings. Revenue, profit, EBITDA, margins, and valuation metrics stay unavailable when the market feed does not supply them.
- **Calculations and charts:** Price changes use exchange-reported values or are calculated from actual current/previous closes. Chart ranges and points come from the returned price series; the app does not create synthetic observations.
- **AI:** Ask FINN uses Gemini through the server-side API. The server retrieves recent NSE announcement metadata, selects relevant records, and includes official source links. The model does not read the linked PDF contents, so responses must not be treated as verified financial-statement analysis. The API key stays in Vercel environment settings.
- **Workspace state:** Theme, portfolio symbols, and watchlist symbols are stored in browser local storage. A portfolio entry is a tracked company, not a position or return calculation.
- **Demo coverage:** On first visit, 16 real NSE symbols are added as a company coverage universe. The selection is demo setup; quotes, filings, and chart values are fetched from live endpoints. It can be edited and never implies holdings or returns.
- **Push / Signal Desk:** The AI Engineer version has the focused portfolio-monitoring workflow: actual returned NSE quote changes are checked against a user-set absolute percentage threshold, and recent NSE filing metadata is classified into material categories. Users can choose 24-hour, 7-day, or all-returned windows. It refreshes when opened or requested; no background notifications or unsupported volume alerts are claimed.
- **Pull / Ask FINN:** The server retrieves recent filing metadata and gives it to Gemini with official source links. The model does not read the linked filing PDFs, annual reports, or transcripts; the app therefore leaves fundamentals and management-guidance analysis unavailable.
- **No Network layer in this build:** The AI Engineer app uses its fifth navigation destination for Signal Desk. This matches the two-mode Push/Pull assignment and keeps the Network intelligence layer specific to the Founding AI Engineer version.
- **Liquid Glass:** The top bar, sidebar/mobile dock, market strip, and controls use layered translucent CSS, edge reflections, blur, and a progressive SVG displacement/specular filter where supported. Safari/iOS keeps the CSS glass fallback; dense chart and analysis panels remain more opaque for contrast.

## Service behavior and limits

The market endpoint caches successful responses briefly and applies upstream timeouts. The frontend prevents overlapping refreshes and keeps the last successful snapshot visible if a later refresh fails. NSE may delay intraday values by 1–3 minutes; historical prices are end-of-day.

Gemini uses the free-tier service where available. Quotas and availability depend on Google's current limits. Questions should contain no personal or confidential information. All claims should be checked against the linked NSE filing.

## Production considerations

A production service would need confirmed data-provider terms, durable storage, accounts and access controls, monitoring, and explicit consent before connecting personal network data. Keep provider credentials server-side, minimize retained data, and make the freshness and evidence period visible for every financial claim.
