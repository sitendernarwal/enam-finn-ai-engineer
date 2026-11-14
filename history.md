# FINN — AI Engineer

## AI-assisted project history

**Prepared:** 14 November 2026  
**Format:** Curated, reconstructed dialogue summary

> This is an edited account of the project decisions and work. It is not a verbatim transcript of the Codex conversation and does not reproduce exact prompts.

## Project conversation

### 1. Defining the assignment

**Project owner — What should the prototype help an investor do?**  
Connect a useful daily brief to a practical company-research view, with a focused workflow that can be demonstrated on a phone.

**AI — Recommended product shape**  
Build FINN around two flows: **Push** for a concise daily brief and **Pull** for company research. Keep the journey direct: an alert should open research for the company it concerns.

### 2. Choosing a build approach

**Project owner — How should the assignment be delivered?**  
Make a working prototype that is easy to inspect, run, and publish.

**AI — Implementation choice**  
Use static HTML, CSS, and JavaScript. Label sample market values and company figures as illustrative, and describe source links as discovery links rather than implying that they point to verified filings.

### 3. Building Push and Pull

**Project owner — What should the investor be able to do?**  
Filter a daily brief, search a portfolio and additional companies, and continue from an event to the right research view.

**AI — Interaction design**  
Build the 16-company mock portfolio and five research-only examples; make alert filters and demo thresholds work; allow a typed NSE ticker to open a source-discovery view; and connect each alert to its company research. Add a saved-research list and a “Continue research” action that resumes the most recently viewed company in the current browser tab.

### 4. Making calculations and labels clearer

**Project owner — Are the calculations and sample claims consistent?**  
Check the numeric inputs, movement thresholds, results copy, and financial metrics.

**AI — Quality improvements**  
Show formulas and sample inputs, handle missing values safely, use numeric price-movement data in alert filtering, and remove sample copy that conflicted with the financial series. Omit EBITDA for banks and lenders and identify missing bank-specific inputs. Mark ranking scores and calculations as demo-only.

### 5. Refining the phone experience

**Project owner — What should happen when a company is selected on a phone?**  
The selected company should open, or its detail should be brought into view.

**AI — Navigation fix**  
Scroll the selected company detail into view after a company chip, alert, saved item, or research-queue action is tapped. Keep the selected company visually and accessibly marked.

### 6. Reviewing and publishing

**Project owner — What should be checked before sharing the prototype?**  
Review the main flows, make the data limits clear, and deploy the site.

**AI — Review summary**  
Run JavaScript syntax checks and structural checks for duplicate HTML IDs and missing script files. Publish the static prototype to GitHub Pages and confirm the Pages workflow succeeds. The project owner reported checking the phone layout; a later screen recording identified the company-detail scroll gap, which was then fixed and redeployed.

## Delivered prototype

- Daily brief with sample event filters, relevance reasons, and editable demo thresholds
- Research for a 16-company mock portfolio and five research-only examples
- Search for listed companies and source discovery for typed NSE tickers
- Transparent calculations based on illustrative sample figures
- Saved research and a “Continue research” path for the last viewed company
- macOS 26 Liquid Glass visual treatment and interactive Sitender profile

## Validation and deployment

- JavaScript syntax checks passed for app.js and analysis.js.
- HTML structure checks found no duplicate IDs or missing local scripts.
- GitHub Pages deployments completed successfully.
- The owner reported completing a phone check. The latest company-selection scroll fix was verified through code checks and successful Pages deployment; no independent on-device retest is recorded here.

**Live prototype:** https://sitendernarwal.github.io/enam-finn-ai-engineer/  
**Public repository:** https://github.com/sitendernarwal/enam-finn-ai-engineer

## Known limits

- Prices, financial values, alerts, and events are illustrative; no live market feed, filing ingestion, or fundamentals pipeline is connected.
- The prototype uses a static source-discovery flow and does not call a language model.
- Saved research and preferences are stored in the current browser session, not in a signed-in account.
- The source links are discovery pages rather than links to the specific documents behind sample claims.

## AI-use note

AI assistance was used for product framing, UI and interaction implementation, code review, documentation, and deployment preparation. The project owner reviewed the output and provided product feedback. This file is a curated project record; use a separate Codex export or share link if a reviewer requires the complete conversation.
