# Finance & Accounting
*Courses: Finance I · Finance II · Financial Accounting*

> Use this when valuing a project or company, reading financial statements, thinking about capital structure, or working with accounting data.

---

## Quick Reference

- **NPV rule** — invest when NPV > 0; cash flows at different times are not comparable without discounting
- **CAPM** — r = rᶠ + β(E[rₘ] − rᶠ); required return given risk
- **WACC** — blended cost of capital; use as discount rate for project evaluation
- **3 statements** — Income Statement (flow), Balance Sheet (snapshot), Cash Flow (sources & uses)
- **Net Income ≠ Cash Flow** — always check CFO; profitable companies can go bankrupt
- **Accounting identity** — Assets = Liabilities + Shareholders' Equity (always true)

---

## Frameworks

### Time Value of Money
- **FV = PV × (1 + r)ⁿ** — future value
- **PV = FV / (1 + r)ⁿ** — present value
- **Perpetuity:** PV = C / r
- **Annuity:** PV = C × [1 − (1+r)⁻ⁿ] / r

NPV = sum of discounted future cash flows − initial investment. Any spending with PV = X can be funded by any investment with PV = X.

---

### CAPM — Required Return
**r = rᶠ + β(E[rₘ] − rᶠ)**

| β | Meaning |
|---|---------|
| = 1 | Same risk as market |
| > 1 | More volatile than market |
| < 1 | Less volatile than market |

**Unlever/relever β** when capital structure changes: find comparable companies → unlever their β → relever at your D/E ratio → compute cost of equity.

---

### Capital Structure: Debt vs. Equity
Six factors: Flexibility · Priority · Control · Taxes · Risk · Maturity

- **Debt payoff:** capped at promised payment (flat then zero)
- **Equity payoff:** call option — worth zero if assets < debt, then rises linearly
- Equity holders bear more risk → demand more return → hold the upside

**WACC = (E/V) × rₑ + (D/V) × rᵈ × (1 − tax rate)**

Use WACC as discount rate when the project has the same risk profile as the firm.

---

### The Three Financial Statements

**Income Statement** (period):
```
Revenue − COGS = Gross Profit
Gross Profit − OpEx = EBIT
EBIT − Interest − Taxes = Net Income
```

**Balance Sheet** (point in time):
```
Assets = Liabilities + Shareholders' Equity
Current assets: Cash, AR, Inventory
Non-current: PP&E, Intangibles
Current liabilities: AP, Accrued expenses, Short-term debt
Non-current: Long-term debt
Equity: Common stock + Retained Earnings
```

**Cash Flow Statement:**
```
CFO (Operations) ± CFI (Investing) ± CFF (Financing) = Net change in cash
```

Retained Earnings = cumulative net income − dividends paid.

---

### Accounting: Accrual vs. Cash
- **Cash basis** — record when cash changes hands
- **Accrual basis** — record revenue when earned, expenses when incurred; more informative; better correlates with stock returns

Earnings quality signal: CFO ≈ Net Income = high quality. Large gap = red flag (aggressive recognition, deteriorating receivables).

---

### Journal Entry Rules
- Assets: ↑ Debit / ↓ Credit
- Liabilities: ↑ Credit / ↓ Debit
- Revenue: ↑ Credit (raises equity)
- Expenses: ↑ Debit (reduces equity)

Common entries: Revenue on credit → Dr. AR / Cr. Revenue · Collect cash → Dr. Cash / Cr. AR · Depreciation → Dr. Depreciation Expense / Cr. Accumulated Depreciation

---

### Key Ratios

**Liquidity:** Current ratio = Current Assets / Current Liabilities (>1 healthy)

**Profitability:** Gross margin · Operating margin · Net margin · ROE · ROA

**Efficiency:**
- DSO = AR / (Revenue/365) — days to collect from customers
- DIO = Inventory / (COGS/365) — days inventory sits
- DPO = AP / (COGS/365) — days before paying suppliers
- **CCC = DSO + DIO − DPO** — days cash is tied up (Amazon/Walmart run negative CCC — customers fund the business)

**Leverage:** Debt-to-equity · Interest coverage (EBIT / Interest; >3× healthy)

---

## Mental Models

**"Price is what you pay, value is what you get." (Buffett)** Market price and intrinsic value diverge — finance is the discipline of finding and using that gap.

**Shareholders are residual claimants.** They get paid last, bear the most risk, and hold the upside option. That's why they demand the highest return.

**Working capital is a strategic lever.** Negative CCC turns working capital from a cost into a funding source. Know where your business sits.

---

## My Notes & Updates
*Add new entries at the top. Format: [Month Year] — note*

[April 2026] — File created. Covers Finance I (Summer), Finance II (Spring), Financial Accounting (Summer).
