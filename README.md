# RideShare Financial Lab

An **interactive, mobile-friendly ride-sharing financial calculator** that you can deploy to Vercel as a static site. It uses the original 21 slider inputs and includes charts, driver payouts, corporate tax estimates, a 12-month forecast, CSV export, a shareable scenario link, and a downloadable Excel workbook.

## Deploy with the Vercel dashboard

1. Unzip `RideShare_Vercel_Ready.zip`.
2. Upload the **contents of `rideshare-vercel/`** to a GitHub repository (`index.html` must be at the repository root).
3. In [vercel.com/new](https://vercel.com/new), choose **Import Git Repository** and select that repository.
4. Choose **Framework Preset: Other**. Leave **Build Command** empty / disabled and **Output Directory** at the default (project root). This website does not need dependencies, environment variables or a server.
5. Click **Deploy**. Vercel will provide a public HTTPS URL you can send to friends.

## Deploy with Vercel CLI (alternative)

```bash
npm install -g vercel
cd rideshare-vercel
vercel login
vercel --prod
```

Follow the CLI prompts and use the current folder as the project root.

## Test locally

```bash
cd rideshare-vercel
python3 -m http.server 8000
```

Open `http://localhost:8000`.

## Sharing and downloads

- **Copy scenario link** creates a link with the current slider values stored in its URL query parameters, so a friend sees your exact assumptions. For this feature, use the URL of the deployed site rather than a local `file://` URL.
- **Download Excel** serves `files/RideShare_Profit_Tax_Calculator.xlsx` as a static file from the same website.
- **Export 12-month CSV** downloads forecast rows from the browser; no database or backend is required.

## Files

- `index.html`: Standalone simulator with all HTML, CSS and JavaScript (no external scripts).
- `files/RideShare_Profit_Tax_Calculator.xlsx`: Downloadable workbook.
- `favicon.svg`: Website icon.
- `vercel.json`: Vercel settings and basic security headers.

## Financial disclaimer

This is a *scenario planning* tool, not tax or legal advice. Corporate income tax, local transportation taxes, driver classification, payment fees and insurance vary by jurisdiction and agreements. The 2.6% + $0.15 card-processing starting assumption comes from the MSC partner deck, not a binding quote. The simplified corporate tax model does not calculate personal taxes or all local tax rules.
