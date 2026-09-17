# The Ledger — Budget Planner
 
A single-page budgeting app built around the 50/30/20 rule (50% needs, 30% wants, 20% combined savings + debt). Track spending by category, project retirement savings, plan debt payoff, set a savings goal, and get an AI-generated budget health report — all in one self-contained HTML file with no install and no backend.
 
## Features
 
- **Budget tracker** — four categories (Needs, Wants, Savings, Debt), each with editable line items and a live comparison against its 50/30/20 target
- **Spreadsheet view** — every line item across all categories in one table, with amount and % of income per row
- **Pie chart** — a donut chart showing the share of your budget going to each category
- **401(k) projection** — estimates your retirement balance from a monthly contribution, optional employer match, years contributing, and an assumed average annual return (5% / 7% / 9%), with a growth chart
- **Debt payoff estimate** — enter your total balance and average APR to see roughly how long payoff will take at your current payments
- **Savings goal tracker** — name a goal, set a target and current amount, add a monthly contribution, and see a progress bar with a time-to-goal estimate
- **AI budget report** — generates a structured report covering:
  1. A budget health score (1–10) with reasoning
  2. Category-by-category analysis
  3. Your savings goal timeline and whether it's realistic
  4. Three specific cost changes with estimated dollar savings
  5. A next-month action plan
  6. A caution flag if cash flow, debt, or emergency savings look risky
  7. General recommendations for improving the budget
All data autosaves to your browser's local storage, so it's there next time you open the page. Nothing is sent anywhere except the anonymized budget summary sent to Claude when you press "Get budget report."
 
## Tech stack
 
- **React 18** + **ReactDOM 18** (UMD builds, loaded via `<script>` tag — no npm, no build step)
- **Babel Standalone** — transforms the JSX in-browser at load time
- Plain **JavaScript** for all calculations (compound interest, amortization, goal math)
- **Native SVG** and CSS `conic-gradient` for the charts (no charting library)
- **CSS custom properties** for theming, with automatic light/dark mode support via `prefers-color-scheme`
- **Google Fonts**: Fraunces (serif, for numbers and headings) and IBM Plex Sans (body text)
- **`window.claude.use("sample")`** — the runtime capability that lets the page ask Claude directly for the budget report
## Running it
 
Just open the HTML file in a browser. Everything is self-contained — no server, no dependencies to install.
 
## Disclaimers
 
- The 401(k) projection is a rough estimate using a fixed average return. It is not a promise of future performance.
- Nothing in this app is investment, legal, or financial advice. For decisions about where to put your money, talk to a licensed financial advisor.
## Customizing
 
- Default category line items live in the `DEFAULT_ITEMS` object near the top of the script.
- Category colors, targets, and descriptions live in `CATEGORY_CONFIG`.
- Color tokens (backgrounds, text, borders) are CSS variables in `:root` — edit these to restyle the whole app at once.
