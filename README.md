# ICSTSDG 2026 – Conference Website (Redesign Concept)

A responsive, royal-blue and white redesign of the website for the **2026 Second International Conference on Smart Technologies for Sustainable Development Goals (ICSTSDG)**, S.A. Engineering College (Autonomous), Chennai.

Built with plain HTML5, CSS3 and vanilla JavaScript. No frameworks, no build step.

> This is a student redesign concept. It is not an official website and has not been approved by S.A. Engineering College or IEEE.

## Folder structure

```
icstsdg-website/
├── index.html
├── css/style.css
├── js/script.js
├── assets/
│   ├── saec-campus.jpg    <- real SAEC campus photo (desktop)
│   ├── saec-campus-mobile.jpg <- portrait crop of the same photo (phones)
│   ├── saec-logo.png      <- real SAEC logo
│   └── sdg/               <- optional official SDG icons
└── README.md
```

## Run it in Visual Studio Code (Live Server)

1. Install [Visual Studio Code](https://code.visualstudio.com/).
2. Open the **Extensions** panel (Ctrl+Shift+X), search for **Live Server** (by Ritwick Dey) and install it.
3. Choose **File → Open Folder…** and select the `icstsdg-website` folder.
4. Right-click `index.html` and choose **Open with Live Server** (or click **Go Live** in the status bar).
5. The site opens in your browser and reloads when you save a file.

You can also just double-click `index.html`; everything uses relative paths.

## Where to put the campus photograph and logo

**Campus photo (hero background and About section)**

1. Get a genuine photograph of the S.A. Engineering College building from an authorised source: the college's own website or media team, or your own photo taken on campus. Ask permission if you are unsure about reuse.
2. Save it as **`assets/saec-campus.jpg`**, replacing the placeholder.
3. Recommended: landscape, at least 1920 × 1080, under about 400 KB (compress with squoosh.app). Put the building in the centre or centre-left; the dark blue overlay and the headline sit over the left side.
4. Optional mobile crop: in `css/style.css`, change `background-position` inside the `@media (max-width: 900px)` rule for `.hero-photo` until the building is framed well on a phone.

The project now ships with the supplied campus photograph and logo. Confirm you have permission to reuse them before publishing.

**Logo**

Save the logo as **`assets/saec-logo.png`** (square, transparent background, about 256 × 256). It is used in the header, footer and browser tab.

**Official SDG icons (optional)**

The SDG section uses the official SDG colours and numbers, with links to each goal on sdgs.un.org. To add the official pictograms, download the icon set from the UN communications materials page, follow its usage guidelines, and save the files in `assets/sdg/`. You will then need to add `<img>` tags in `renderSdgs()` in `js/script.js`.

## Content verification (checked against the official page)

Source: https://www.saec.ac.in/ieeeicstsdg2026/ (read when this project was built).

| Item | Status |
| --- | --- |
| Conference dates | Official page says **19–21 August 2026**. Your brief also mentioned 04–06 August 2027, which is **not** on the official page, so it was not used. |
| Important dates, fees, accommodation | Copied from the official page, labelled as historical. |
| Six tracks and topics | Official wording used (it differs slightly from the brief in a few topic names). |
| Committee | Founder, Chief Patrons, Patrons (institution and IEEE), Co-Patrons, General Chairs and Conference Chairs. |
| Not shown | Budget/registration, tutorial/workshop, website/publicity, local arrangements, hospitality chairs and the Technical Programme Committee. They were **not on the official page**, so nothing was invented. |
| Speakers | None published, so the section shows an empty state. |
| Submission link | Microsoft CMT link exactly as published on the official page. 2026 submissions are closed. |
| Contacts | Three conference contact names and phone numbers as published, plus the college phones and emails. |
| Accreditation | NAAC/NBA ‘A’ Grade and ISO 9001:2015 are quoted from the page. Confirm with the college before presenting them as current. |

## What is real and what is a demo

- **Real:** smooth scrolling, active-section highlighting, mobile menu, expandable tracks, committee accordions with search, clickable SDG tiles, back-to-top, reveal animations, animated statistics, reduced-motion support.
- **Date states:** the timeline and the hero badge compare the real current date with the 2026 dates. Everything shows as completed. There is no countdown.
- **Contact form:** the site has no backend. Pressing the button validates the fields and opens the visitor's email app with the message pre-filled for `ieeeicstsdg2026@saec.ac.in`. The page never claims a message was sent.
- **Registration:** the fee table is information only. There is no payment feature.

## Reusing the design for a future edition

Update only after the organisers confirm details:

1. Dates in `index.html` (hero panel, timeline `data-date` and `datetime` values, fee table headings) and in `CONFIG` at the top of `js/script.js`.
2. Tracks, SDG list and committee in the data arrays at the top of `js/script.js`.
3. Submission link, contacts and fees in `index.html`.

## Customising the look

Colours are CSS variables at the top of `css/style.css` (`--navy`, `--royal`, `--electric`, `--cyan`, and so on). Fonts are Manrope (headings) and Inter (body), loaded from Google Fonts with system-font fallbacks, so the site still works offline.

## Browser support

Current Chrome, Edge, Firefox and Safari. The track and committee panels use the `inert` attribute and CSS grid-row transitions, which need a reasonably recent browser.
