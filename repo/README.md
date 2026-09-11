# Data Analyst Assessment — Superstore Business Analysis

**Candidate:** Ansh Parashar
**Business context:** Assessment scenario — Data Analyst at a B2B technology company, asked to independently find a dataset, define a business problem, analyze it, and present findings to management.

This repository is the complete submission, restructured for GitHub (the original brief asked for a Google Drive folder; a public GitHub repo is used instead per instructions).

## What's in here

| Path | What it is | Maps to |
|---|---|---|
| `data/superstore_raw.csv` | Original dataset, unmodified | Worksheet: **Data** |
| `worksheets/Superstore_Assessment_Workbook.xlsx` | **All written answers**, one tab per question (Data, Q1, Q2, Processed Data, Q3–Q8, Q10) — open in Excel or upload to Google Sheets | The single "Google Sheet" deliverable |
| `data/superstore_processed.csv` | Cleaned dataset with engineered fields (Ship Days, Margin %, Discount Band, Year/Month, outlier flags) | Worksheet: **Processed Data** |
| `notebook/analysis.ipynb` | Executed Python/pandas notebook: cleaning, EDA, hypothesis checks, charts | **Code** deliverable |
| `charts/*.png` | Supporting chart images referenced in the notebook and presentation | **Analysis** deliverable |
| `dashboard/dashboard_data.csv` | Analysis-ready export to upload into Looker Studio | Input for **Q8 dashboard** |
| `dashboard/dashboard_mockup.png` | Static mockup of the intended dashboard layout (see note below) | **Q8 screenshot placeholder** |
| `presentation/Superstore_Management_Presentation.pptx` | 7-slide management presentation | **Presentation** deliverable |
| `README.md` | This file — methodology & AI-usage summary | **README / Methodology** |

## 1. Dataset

**Sample Superstore** — 9,994 US retail order lines (2014–2017), covering Region, Segment, Category/Sub-Category, Ship Mode, Discount, and Profit. Originally a Tableau training dataset; sourced here via a public GitHub mirror (full citation and URL in worksheet **Q1**). No predefined dataset was given, so this was selected independently for having enough real-world complexity (multiple categorical dimensions plus a full profitability trail) to support meaningful analysis without needing paid/API-gated access.

## 2. Business problem (full detail in worksheet Q2)

Revenue grew every year from 2014–2017, but about 1 in 5 order lines lost money. The analysis asks: where is profit leaking, does discounting help or hurt margin, which regions/segments/products deserve more or less investment, and does fulfillment speed matter?

## 3. Method

1. **Clean & type** — parsed dates, zero-padded ZIP codes, checked for duplicates/missing values (worksheet Q3 has the full change log with justification for each step).
2. **Engineer fields** — Margin %, Ship Days, Discount Band, Year/Month, per-sub-category outlier flags (kept and flagged, not deleted).
3. **Explore** — grouped by Region, Category, Sub-Category, Segment, Discount Band, Ship Mode; computed correlations (see notebook).
4. **Synthesize** — 5 management-facing insights (Q4), 1 surprising result (Q5), data-quality/limitations review (Q6), 4 prioritized recommendations (Q7).
5. **Communicate** — a 7-slide non-technical presentation (Slide 1–7 per the required structure) and a dashboard spec.

Full findings, evidence, and business impact for each insight/recommendation are written out in the workbook — this README intentionally doesn't duplicate them.

## 4. Dashboard (Q8) — important note

Looker Studio is a hosted Google product that requires a logged-in Google account to publish and share a link, which an AI assistant cannot do on the candidate's behalf. What's provided instead:
- `dashboard/dashboard_data.csv` — ready to upload directly into Looker Studio as a data source.
- `dashboard/dashboard_mockup.png` — a static mockup showing the intended KPI cards and 6 charts.
- Step-by-step build instructions and the rationale for each chart are written out in worksheet **Q8**.

**Action still needed:** publish the live dashboard in Looker Studio using the steps in Q8, then paste the shareable link into Q8 before final submission.

## 5. How AI was used

Full detail (tools, tasks, one example where AI helped, one example where its output had to be corrected) is in worksheet **Q10**, as required by the assessment brief.

## 6. Limitations

See worksheet **Q6** for the full list. Headline caveats: no cost/COGS data (Profit is taken as given), no customer demographics, and the data is historical (2014–2017) so conclusions should be validated against current transactions before being acted on.
