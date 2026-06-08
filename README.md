# Mortgage Payoff Planner
 
An interactive, single-page app for planning your mortgage payoff timeline. Adjust your extra monthly principal payment and instantly see how it affects your payoff date, total interest paid, and interest saved.
 
**Live site:** https://kelley12.github.io/mortgage-payoff-planner
 
## Features
 
- **Editable loan settings** — balance, balance date, interest rate, regular payment, and escrow
- **Extra payment slider** — drag or type any extra monthly principal amount
- **Live projections** — payoff date, months remaining, total interest, and interest saved vs. minimum payments
- **Balance chart** — visualizes your payoff curve vs. the minimum-payment baseline
- **Scenario table** — side-by-side comparison across common extra payment amounts ($0–$3,000/mo)
## Usage
 
Just open `index.html` in any browser — no build step, no dependencies to install. Everything runs client-side.
 
To update your loan details, edit the **Loan Settings** fields at the top of the page. The P&I (principal & interest) amount is derived automatically from your regular payment minus escrow.
 
## How the math works
 
Each month's projection follows standard amortization:
 
```
interest         = balance × (annual_rate / 12)
principal        = P&I_payment − interest + extra_payment
new_balance      = balance − principal
```
 
This repeats until the balance reaches zero. The baseline (no extra payment) uses the same formula with `extra_payment = 0`, allowing apples-to-apples interest savings comparisons.
 
## Tech
 
Plain HTML, CSS, and JavaScript — no framework or build tooling. Uses [Chart.js](https://www.chartjs.org/) (loaded from CDN) for the balance chart.
 
## Deploying updates
 
Edit `index.html`, then push to `main`:
 
```bash
git add index.html
git commit -m "Update planner"
git push
```
 
GitHub Pages redeploys automatically within ~1 minute.
 