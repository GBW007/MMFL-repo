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


## How to use
Change yellow cells on `Model` (growth, margin, capex, working capital) and `DCF` (beta, cost of debt, g, RONIC). Flip `Model!B3` for scenarios. `Reverse_DCF_Grid` recalculates live. Run `python mmfl_dcf.py` after changing inputs in both places.


*Student valuation exercise – not investment advice. The author is not a SEBI-registered research analyst.*
