# Submission readiness — AI Engineer

| Requirement | Status | Evidence / remaining work |
|---|---|---|
| Mobile-first working prototype | Ready for review | [Live prototype](https://sitendernarwal.github.io/enam-finn-ai-engineer/). Checked at a 390 px viewport: full-width content, fixed five-item bottom navigation, and both theme states. |
| Market brief and company research | Complete for available exchange data | Live NSE index/history data, searchable listed-company profiles, end-of-day history, and announcement metadata/linkouts are connected through the shared Vercel API. Intraday and mover availability depends on the exchange feed and market hours. |
| Portfolio and watchlist navigation | Complete as a company coverage universe | The first visit seeds 16 real NSE symbols as tracked coverage; users can add/remove companies and keep selections in browser storage. Quotes remain live-source values. The list does not represent holdings, quantities, or returns. |
| 3–5 ad-hoc research companies outside portfolio | Available on demand | Search NSE company names or symbols in Research; coverage depends on the exchange feed. |
| Generalize to any NSE ticker | Implemented with source limits | Direct NSE symbols load the company research view. A quote may be unavailable outside market hours or for symbols not covered by the feed. |
| Market data, announcements, company fundamentals | Partial, sourced | NSE index history, live movers plus the latest-session EOD movers fallback, stock history, and filing metadata are connected. The feed does not supply annual reports, transcripts, or verified quarterly financial statements; those remain unavailable rather than estimated. |
| Calculation and analysis | Partial, sourced | Price changes are calculated from exchange closes and the chart uses returned NSE history. Revenue, profit, EBITDA, margins, and valuation ratios need verified financial inputs. |
| Push and configurable signals | Working prototype; no background push | Signal Desk applies a saved ±% threshold to returned NSE quote changes and classifies selected material filing types inside a 24-hour, 7-day, or all-returned digest. It checks tracked companies when opened/refreshed; no background job or device notification is claimed. |
| Ask FINN AI research | Implemented and checked | Server-side Gemini summarizes recent NSE announcement metadata and returns official filing links. It does not read filing PDFs or annual reports/transcripts; free-tier quotas apply. |
| Dark/light theme and responsive navigation | Complete | Dark is the default; the toggle changes and remembers the theme. The five-item mobile dock is safe-area aware. The top bar and dock use progressive refraction with an iOS/Safari CSS fallback. |
| Deployment | Complete | GitHub Pages serves the frontend; the shared Vercel backend serves market data and Ask FINN. See [DEPLOYMENT.md](DEPLOYMENT.md). |
| Public repository | Complete | [GitHub repository](https://github.com/sitendernarwal/enam-finn-ai-engineer). |
| AI build history | Prepared | See [history.md](https://github.com/sitendernarwal/enam-finn-ai-engineer/blob/main/history.md). A full conversation link is only needed if the reviewer specifically asks for it. |
| Short covering note | Ready to send | See [COVERING_NOTE.md](COVERING_NOTE.md) for submission email text and project links. |

**Review note:** This prototype is live-data backed, but it is not a full financial terminal. NSE intraday data may be delayed 1–3 minutes; outside market hours the app may show the latest dated close and no movers. Signal rules run when the app is open and refreshed; no background push notifications are sent. Fundamentals require checking linked company filings. NSE data is for educational/informational use and is not investment advice.
