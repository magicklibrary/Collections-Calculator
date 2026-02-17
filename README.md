# Late Payment & Collections Calculator

**Live tool:** [https://magicklibrary.github.io/Collections-Calculator/](https://magicklibrary.github.io/Collections-Calculator/)

A browser-based calculator for computing compounded interest, late fees, and collections charges on delinquent invoices. Produces a formatted Excel report suitable for clients and collections agents. No installation required — runs entirely from a single HTML file.

---

## Calculation Rules

| Charge | Rule |
|---|---|
| Interest | `Principal × (1.015)^(Days Delinquent ÷ 30) − Principal` |
| Interest Rate | 1.5% per month / 18% annually, compounded monthly |
| Late Fee | $75.00 one-time charge, applied when Days Delinquent > 45 |
| Collections Fee | 15% of (Principal + Interest + Late Fee) |
| Admin Fee | 5% of the Collections Fee |
| **Total Due** | Principal + Interest + Late Fee + Collections Fee + Admin Fee |

---

## Usage

1. Enter the **Client Name** — it copies automatically to any additional invoices added
2. Fill in the **Invoice Number** and **Invoice Date**
3. Set **Payment Terms** — options are Net 0, 10, 14, 30 (default), or 45 days
4. Enter the **Invoice Amount** and **Days Delinquent**
5. All charges calculate in real time — interest, late fee, collections fee, admin fee, and total due update as you type
6. Click **Export to Excel** to download the report

---

## Excel Export

The exported `.xlsx` file contains two sheets:

**Invoice Detail** — one row per invoice including client name, invoice number, invoice date, payment terms, invoice amount, days delinquent, accrued interest, late fee, subtotal, collections fee, admin fee, and total due. A totals row summarizes all invoices.

**Summary** — grand totals across all invoices with calculation methodology notes and export timestamp.

---

## Deployment

The application is a single file (`index.html`) with no external dependencies beyond a CDN-loaded Excel library. To self-host:

1. Ensure `index.html` is in the root of the `main` branch
2. Ensure `.nojekyll` is in the root of the `main` branch
3. In **Settings → Pages**, set Source to **Deploy from a branch**, branch to `main`, folder to `/ (root)`
4. Confirm deployment completed via the **Actions** tab before testing the URL

---

## File Structure

```
Collections-Calculator/
├── index.html      — Full application (single file)
├── .nojekyll       — Disables Jekyll processing on GitHub Pages
└── README.md       — This file
```

---

## License

MIT
