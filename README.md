# CarryFast Global Services — website

A single-page site for a CHA (Customs House Agent) and logistics business, covering services, process, and a quote request form.

## Files

- `index.html` — page structure and content
- `styles.css` — all styling
- `logo.png` — your logo (add this yourself; see below)

## Editing your company details

Open `index.html` and scroll to the bottom `<script>` block. All the details that appear across the header, footer, and contact section are set in one place:

```js
const COMPANY = {
  logoSrc: "logo.png",
  name: "CarryFast Global",
  legalName: "CarryFast Global Services Pvt. Ltd.",
  tagline: "Services Pvt. Ltd. · CHA",
  phone: "+91 12345 67890",
  phoneHref: "tel:+911234567890",
  email: "ops@carryfastglobal.example",
  address: "Plot 000, Logistics Park Road, Near JNPT, Navi Mumbai, Maharashtra 400000",
  cin: "U00000MH2026PTC000000",
  gstin: "27XXXXX0000X1ZX",
  iec: "0000000000"
};
```

Change the values, save, and every place that detail appears on the page updates automatically.

## Adding your logo

Drop a logo file into this same folder and name it `logo.png` (or update `logoSrc` above to match whatever filename/extension you use, e.g. `logo.svg`). Until you add one, a placeholder icon shows automatically.

## Connecting the quote form

The quote form currently posts to Formspree but needs a real endpoint. In `index.html`, find:

```js
const FORM_ENDPOINT = "https://formspree.io/f/YOUR_FORMSPREE_ENDPOINT_HERE";
```

To set it up:
1. Go to [formspree.io](https://formspree.io) and sign up with your real email.
2. Create a new form and verify the confirmation email.
3. Copy the endpoint URL (looks like `https://formspree.io/f/abcdwxyz`).
4. Paste it in place of `YOUR_FORMSPREE_ENDPOINT_HERE`.

Until this is set, the form will show a message saying it isn't connected yet, instead of silently failing.

## Publishing with GitHub Pages

1. Create a new GitHub repository and push these files to it (see commands below).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

### Pushing this folder to a new repo

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## Local preview

No build step needed — just open `index.html` directly in a browser, or serve the folder locally:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.
