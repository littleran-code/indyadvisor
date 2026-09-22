# Getting indyadvisor.ca live on GitHub Pages — no command line needed

## 1. Create the repository
1. Sign in to GitHub, click **New repository**.
2. Name it whatever you like (e.g. `indyadvisor-site`). Set it to **Public** — GitHub Pages on a free account requires the repo to be public, and there's nothing sensitive in these files.
3. Don't add a README/license at this step — just create it empty.

## 2. Upload the files
1. On the repo's main page, click **Add file → Upload files**.
2. Drag in every file from this folder, **including the `assets` folder** (it holds the logo images): `index.html`, `process.html`, `about.html`, `contact.html`, `privacy-policy.html`, `styles.css`, `CNAME`, and `assets/`.
3. Commit directly to the `main` branch.

## 3. Turn on Pages
1. In the repo, go to **Settings → Pages**.
2. Under "Build and deployment," set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**. Save.
3. GitHub will give you a temporary `https://<yourusername>.github.io/<reponame>/` URL — that confirms it's live before the custom domain is connected.

## 4. Point indyadvisor.ca at it
1. Still in **Settings → Pages**, under "Custom domain," enter `indyadvisor.ca` and save. (The `CNAME` file already in this folder does the same thing — the two should match.)
2. In GoDaddy, go to your domain's **DNS** management for indyadvisor.ca and add these records (GitHub's current values — double-check against **Settings → Pages → your repo's guidance** or GitHub's own DNS docs before entering them, since IPs occasionally change):
   - Four **A** records on the root (`@`), pointing to:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One **CNAME** record for `www`, pointing to `<yourusername>.github.io`
3. Back in GitHub's Pages settings, once DNS has propagated (usually under an hour), check **Enforce HTTPS** — GitHub issues a free SSL certificate automatically once it verifies the domain.

## 5. Updating content later
No command line required. Edit the file, then in the repo click the file → the pencil (edit) icon → make the change → **Commit changes**. It republishes automatically within a minute or two. If you'd rather send me the change and have me hand back an updated file, that works too — just re-upload what I give you the same way as step 2.

## For compliance review
The on-page yellow draft notes are gone now that this is going to review, but these are the specific open questions behind them — worth flagging to your reviewer directly rather than assuming they'll spot them:

- **About page bio** ("They tell me I listen well... nobody has explained things in 'that way' before") is paraphrased client-feedback language. That's testimonial-adjacent content, which typically carries its own disclosure/consent requirements separate from the standard trademark and licensing lines — flag it specifically rather than reviewing it as ordinary marketing copy.
- **"Choose Simple" tagline** — added to the footer of every page under the logo row. Worth a compliance glance too, mainly to confirm it isn't itself a piece of registered/reviewed messaging.
- **Contact page map embed** — uses Google's free no-API-key embed trick, keyed to a verified Google Place ID for the building, with a "View larger map" link as backup if the embed itself doesn't render for some visitor. This is a technical note, not a compliance one — nothing for a reviewer to weigh in on.
- Double check the booking link on the Contact page — it's currently the `sfl.ca`-domain Outlook Bookings link you gave earlier; confirm that's still the right one given the SFL/DFSIN naming mix-up you mentioned.

**Resolved since the last review pass:**
- Footer disclosures were updated (2026-09-22) with the wording you sent: an updated mutual funds/securities line (naming Worldsource Wealth Management Inc. as the trade name holder), an updated trademark line, two new site-ownership/liability lines for Desjardins Insurance and DFSIN, and the existing insurance-licensing line kept alongside all of it. Two stray, undefined footnote markers in what you sent (a leading `*` and a superscript-looking `1` after "Desjardins Insurance") were dropped at your instruction — if compliance's source document has footnote text for either, send it over and I'll add it back in properly.
- The Privacy Policy page now has the real "Legal, Privacy, Copyright and Trademark Information" text you sent, with "Owner" filled in as Indyadvisor Management Inc. throughout. One small wording fix from what you pasted: "This site may contains links" → "This site may contain links" (grammar only, no substantive change). The draft warning banner is removed now that this is real content — have your reviewer confirm the generic template language (e.g. "the province in which the Owner resides") is fine as-is rather than naming Ontario explicitly.

## From the DFSIN brand guide you sent
- The trademark attribution line is now in the footer of every page, since the guide says it must accompany the Desjardins/DFSIN/DFSI logos "at all times, unless an exception was authorized by Compliance."
- The guide covers visual identity only — it doesn't state the required wording for the mutual-fund/insurance disclosure lines themselves, so that question above is still open.
- If you ever want questions about logo use answered directly rather than through me, the guide lists dfsin_marketing@dfs.ca as the contact.

## About the logo files
Both logos are now live in the footer, from two different sources:

- **DFSI (Investments)** — the two `.ai` files you sent (`file.ai`, color; `file (1).ai`, white) were actually PDF-compatible under the hood, so I rendered them at full vector quality — crisp at any size. In `assets/` as `dfsi-logo.png` (in use) and `dfsi-logo-white.png` (saved for later, in case you ever put it on a dark background).
- **DFSIN (Independent Network)** — the six `.eps` files you originally sent (7 through 12) are plain PostScript, and rendering those needs Ghostscript, which isn't in my environment and I couldn't install (the package registry that would supply it is blocked here). The two screenshots you pasted afterward solved it instead — clean, transparent-background renders at 619×229px, plenty sharp for how it's displayed here (about 48px tall). In `assets/` as `dfsin-logo.png` (color, in use) and `dfsin-logo-black.png` (black, saved for later).

One caveat on the DFSIN logo specifically: it's a raster screenshot, not a vector file, so it's fine at web sizes like this footer but would look soft if someone tried to blow it up for print or large signage. If DFSIN ever needs to go anywhere beyond this website at larger size, get the vector version (PDF-compatible `.ai`, `.pdf`, or `.svg` — same fix as what worked for DFSI) rather than reusing this PNG.

For reference, in case you need the other EPS variants for something later (best guess from their tiny embedded thumbnails, not confirmed): file 7 looked like DFSIN color, file 8 DFSIN black, file 10 DFSIN white, file 11 DFSI black with "Investments Inc." spelled out (unlike the DFSI files you sent, which omit "Inc."), and files 9/12 were unclear — cut off before showing a subsidiary line, so possibly plain parent "Desjardins" marks rather than DFSIN/DFSI-specific ones.
