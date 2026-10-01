# M M Forgings (NSE: MMFL) – DCF, Reverse DCF and the Credit-vs-Equity Gap

Student valuation project. CARE rates MMFL **A (Stable)** – its debt is serviceable. Yet the equity trades at **14.3x EV/EBITDA and 3.0x book** while FY26 post-tax ROIC was **6.2% against a 12.95% WACC**. This project asks: what does the Rs612 price (29-Sep-2026) have to assume?

| Result | Value |
|---|---|
| Base-case DCF value | Rs118 per share (bear Rs4, bull Rs240) |
| Justified P/B cross-check | Rs167 |
| Exit EV/EBITDA the price needs in FY31 | ~12.1x (our assumptions imply 4.6x) |
| ROIC the price needs on today's capital | ~26% (FY26: 6.2%, best year FY23: 11%) |
| Return if you buy at today's EV (base cash flows) | +16.9% a year if 14.3x holds; +8.4% at 10x; -2.5% at 6x |

| File | What it is |
|---|---|
| `MMFL_Valuation_Model.xlsx` | Model (FY22–FY31E), DCF, reverse DCF, live sensitivities, XIRR check, scenarios, reverse-DCF grid, quarterly tracker (612 formulas) |
| `mmfl_dcf.py` | Independent Python replica; re-computes everything and checks the Excel file (difference: Rs0.00) |
| `MMFL_Valuation_Memo.pdf` / `.docx` | 4-page valuation memo |

## Concepts the model teaches
- **FCFF** = EBIT × (1 − tax) + D&A − capex − increase in working capital.
- **WACC** with a relevered beta: βL = βU × (1 + (1 − t) × D/E) (Hamada). Ke = 7.1% + 1.31 × 6.5% = 15.6%; WACC = 12.95%.
- **Mid-period discounting with a stub:** valuation date 30-Sep-2026, so only half of FY27E cash flow is counted, at 0.25 years.
- **Value-driver terminal value:** TV = NOPAT × (1 − g/RONIC) / (WACC − g). Growth adds value only if RONIC > WACC (see sensitivity 2: at RONIC 10%, higher growth lowers value).
- **Reverse DCF:** market EV − PV(forecast FCFF) = PV of the terminal value the market needs → implied exit multiple, implied NOPAT and implied ROIC.
- **XIRR return check:** buy the firm at today's EV, receive FCFF, sell at an exit multiple. Returns depend on the multiple more than on operations.
- **Justified P/B** = (ROE − g) / (Ke − g) as an independent cross-check.
- **Credit vs equity:** lenders need interest cover (EBITDA/interest 3.6x); shareholders need ROIC > WACC. Both views can be right.

## How to use
Change yellow cells on `Model` (growth, margin, capex, working capital) and `DCF` (beta, cost of debt, g, RONIC). Flip `Model!B3` for scenarios. `Reverse_DCF_Grid` recalculates live. Run `python mmfl_dcf.py` after changing inputs in both places.

## Verify before you use it
- **Cash:** Screener does not split out cash, so it sits inside working capital. Get the FY26 cash balance from the annual report.
- **Tax:** effective tax was 14% (FY26) and ~1% (Q1 FY27). The model uses 25.17%. Find out why in the tax note.
- **Capitalised interest:** Screener flags that interest may be capitalised into work-in-progress.
- **One-off:** Q1 FY27 includes Rs63cr of one-off other income.
- **Why did the stock double from Rs276?** Know the narrative (orders, new segments, exports) before you defend a DCF far below the price.

## Interview questions
1. Why is your DCF so far below the market price, and which assumption would you change first?
2. Explain the value-driver formula and why RONIC matters.
3. Why relever beta, and what D/E did you use?
4. What does a 12x exit multiple imply about long-run returns?
5. How can CARE rate the company A while you think the equity is expensive?

*Student valuation exercise – not investment advice. The author is not a SEBI-registered research analyst.*
# MMFL-repo
