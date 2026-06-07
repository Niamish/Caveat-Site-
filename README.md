# Caveat — The Fine Print, Read for You

**Caveat** is a premium single-page landing page concept for a contract-intelligence product that reads agreements before users sign them. It highlights risky clauses, explains what they mean in plain English, and shows users what to negotiate before committing to a contract.

The page is designed like an annotated legal document: editorial typography, paper texture, margin notes, risk flags, clause navigation, a live clause checker, and a risk register. It presents Caveat as a tool for founders, operators, procurement teams, freelancers, and anyone reviewing contracts without a lawyer beside them.

---

## Description

Caveat is a refined contract-review landing page built around the idea of **“the fine print, read for you.”** The website demonstrates how a legal-intelligence product could scan agreements such as MSAs, NDAs, SaaS terms, leases, employment contracts, and vendor agreements, then flag clauses that transfer risk onto the signer.

The design uses a paper-like editorial aesthetic with serif typography, oxblood warning accents, sticky clause navigation, inline flagged phrases, margin explanations, and a pattern-based clause checker. It feels less like a normal SaaS website and more like a marked-up contract, making the product instantly understandable.

---

## Key Features

- **Editorial legal-document design**
  - Paper-toned background
  - Serif display typography
  - Fine-print inspired layout
  - Sticky top banner and document-like structure

- **Annotated contract specimen**
  - Sample Master Services Agreement
  - Clause-by-clause layout
  - Inline flagged risk phrases
  - Margin notes explaining each issue

- **Risk severity system**
  - `Bites` for high-risk clauses
  - `Watch` for clauses needing attention
  - `Standard` for market-standard terms

- **Interactive flag linking**
  - Clicking a flagged clause jumps to the matching Caveat note
  - Clicking a margin note jumps back to the related clause
  - Hover and keyboard states are included

- **Clause checker preview**
  - Users can paste a contract clause
  - The page checks for common risky patterns
  - Flags auto-renewals, liability caps, indemnity issues, data licenses, unilateral amendment clauses, and more

- **Risk register**
  - Table of common contract risks
  - Explains what Caveat watches for in each clause type

- **Request access / lead form**
  - Demo form for requesting a contract margin read
  - Client-side validation included
  - Ready to connect to a backend or form handler

- **Responsive design**
  - Desktop three-column contract layout
  - Mobile-friendly stacked layout
  - Accessible keyboard interactions and reduced-motion support

---

## Tech Stack

This project is built as a standalone HTML file.

- **HTML5**
- **CSS3**
- **Vanilla JavaScript**
- **Google Fonts**
  - Libre Caslon Display
  - Newsreader
  - IBM Plex Mono

No build tools, frameworks, or package managers are required.

---

## File Structure

```txt
caveat.html
README.md
```

---

## How to Run

Open the file directly in your browser:

```txt
caveat.html
```

Or, for a local development preview, use a simple local server:

```bash
python -m http.server 8000
```

Then open:

```txt
http://localhost:8000/caveat.html
```

---

## Deploying to GitHub Pages

For GitHub Pages, rename the main HTML file:

```txt
caveat.html → index.html
```

Your repository should look like this:

```txt
your-repo/
├── index.html
└── README.md
```

Then enable GitHub Pages from:

```txt
Settings → Pages → Deploy from branch → main → root
```

Your site will open at:

```txt
https://your-username.github.io/your-repo/
```

---

## Customization Guide

### Change the brand name

Search for:

```txt
Caveat
```

Replace it with your own product or startup name.

### Change colors

The main colors are defined in the `:root` section:

```css
--paper: #f4f0e5;
--ink: #181309;
--bite: #9c2a1d;
--caution: #825912;
--standard: #566b3f;
```

### Add new clause flags

Add a new `.flag-span` inside the contract text:

```html
<span class="flag-span" data-sev="bite" data-flag="f8">
  risky clause text
  <span class="marker">⚑</span>
</span>
```

Then add a matching `.flag-card` with the same `data-flag` value:

```html
<div class="flag-card" data-sev="bite" data-flag="f8">
  <div class="flag-top">
    <span class="sev">Bites</span>
    <span class="ref">§8</span>
  </div>
  <p><b>Risk title.</b> Plain-English explanation of the risk.</p>
</div>
```

### Add new checker rules

The clause checker rules are stored in the JavaScript `RULES` array. Add a new object with:

- severity
- label
- regex pattern
- explanation note

Example:

```js
{
  sev: 'bite',
  label: 'Unilateral termination',
  re: /may terminate.*at any time/i,
  note: 'This allows one side to terminate without meaningful protection. Ask for notice and cure rights.'
}
```

---

## Important Note

This is a demonstration interface. It does not provide legal advice and should not be used as a substitute for review by a qualified lawyer. The clause checker is pattern-based and only identifies familiar wording, not full legal context.

---

## Possible Future Improvements

- Connect the form to a backend or email handler
- Add real document upload support
- Add AI-powered contract analysis
- Export annotated contracts as PDF
- Save clause reports to a dashboard
- Add user accounts and contract history
- Add support for multiple contract types
- Integrate with DocuSign, Google Drive, or Dropbox

---

## License

This project is proprietary.

Copyright © 2026 Namish Gupta. All Rights Reserved.

You may not copy, modify, redistribute, resell, sublicense, or use this project
for commercial purposes without prior written permission from the owner.

This project is not open source. Public access to this repository or live website
does not grant permission to reuse the code, design, assets, or content.
---

## Credits

Designed as a premium landing page concept for a contract-intelligence product that turns complex legal agreements into clear, actionable margin notes.
