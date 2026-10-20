# Word Cloud Studio v1.0 — Test Report & Wix Listing

**File:** `~/workspace/your_files/word-cloud-studio/index.html` (47,914 bytes — well under the 150 KB limit)
**Version:** 1.0 · **Built:** 20 Oct 2026 · **Creator:** Dr. Asif Ahmad (Asif SaaS Studio)

## Short description
A free word cloud generator that runs entirely in the browser. Paste text or upload TXT, CSV, DOCX, PDF or XLSX files (all parsed locally on the device — nothing is uploaded), and Word Cloud Studio counts word frequencies, detects two-word phrases like "food safety", and renders a live, collision-free word cloud in seven shapes (rectangle, circle, heart, star, cloud, lightbulb, tree) or inside your own uploaded silhouette image. Customise fonts, orientation, colour themes (including your own colours) and background (including transparent), edit individual words (highlight, enlarge, remove, add your own), inspect the full frequency table, click any word in the cloud to see its count, and export at up to 4K as PNG, JPG, SVG or PDF. English, Urdu and Arabic text are tokenised correctly, with built-in stop-word lists for all three.

## Wix SaasProducts listing (ready to paste)
- **Title:** Word Cloud Studio — Free Word Cloud Generator
- **Category:** Design
- **Slug:** `word-cloud-studio`
- **Summary:** Turn text and documents into beautiful word clouds — frequency analysis, phrases, custom shapes & silhouettes, live design controls, 4K PNG/JPG/SVG/PDF export. Private: everything runs in your browser.
- **Version:** 1.0 · **Demo:** No

## What "AI-powered" honestly means here (and the staged plan)
This v1.0 is a **frequency-analysis** tool — the honest, proven core. It does not pretend to do semantic AI:
- **Genuine AI keyword extraction & sentiment scoring need a model.** Two honest routes, staged for v2: (a) an *optional* backend proxy (a small serverless function holding an API key for an NLP/LLM service; the app sends text only when the user explicitly enables "AI analysis" and consents — keys never live in the HTML); or (b) a small on-device model loaded from a CDN library in the standalone hosted version (heavier download, still private). Sentiment colours can also ship earlier as a clearly-labelled *simple built-in word-list* tint (positive/negative dictionaries), never marketed as AI.
- **Save projects** needs browser storage (IndexedDB). The sandboxed Wix iframe version must not use storage, so projects are staged for the standalone hosted version only.
- **Comparison mode (two documents) and batch generation from CSV/XLSX** are pure front-end work — staged for v1.1, no backend needed.
- The research-honesty note is built into the app itself: *frequency is not validated qualitative themes* — the cloud is a starting point for analysis, not a substitute for coding data.
- SEO pages (e.g. a standalone `/word-cloud-generator/` page with FAQ + structured data) belong to the future public SaaS Studio site build; on the current Wix setup the tool lives in the tools catalogue like the other apps.

## What was tested (automated, against the shipped code)
**45 checks — all passed.**
- Frequency engine on the prototype text: research ×4, education/innovation ×2, 9 unique words (phrases off) and 10 with phrases on (the bigram "science learning" ×2 is correctly detected and flagged)
- Stop-word removal on/off, number removal on/off, minimum-length filter, phrase detection ("food safety" ×3 in a test paragraph)
- Multilingual tokenising: Urdu (کھانا ×3) and Arabic (العلم ×3) counted correctly
- Shape masks: circle/heart/star/cloud/bulb/tree point tests (centres inside, corners outside, tree trunk inside)
- Layout engine (with a reference text measurer): all 9 words placed in rectangle mode with **zero overlapping boxes**; largest word placed first; circle mode places ≥7 of 9 with every centre inside the shape
- SVG export contains the words and background; frequency CSV has the correct header and values
- **Real file intake**: DOCX (python-docx fixture), XLSX (openpyxl fixture) and PDF (ReportLab fixture) all extracted to the expected text by the app's own in-page parsers
- **Export engines**: the zlib writer round-trips through a standard decompressor; the image-PDF writer produces a valid 1-page PDF (612 × 459 pts for a 4×3 test image)
- Two test expectations were corrected during testing (phrase entries raise the unique count; a tight circle honestly reports unplaced words) — the app was right both times

## Testing checklist (after you upload it to the site)
1. Open the live page — a starter cloud is already rendered from the sample keywords; the preview updates as you type.
2. Press **Sample text** — the stats line shows the totals; "food safety" appears as one phrase entry in the table.
3. Upload a DOCX or PDF of yours — its text loads into the box and the cloud rebuilds (files never leave the device).
4. Change shape to **Heart**, theme to **Sunset**, background to **Emerald** — the cloud re-forms inside the heart.
5. In the frequency table: ★ a word (turns gold), + a word (grows), ✕ a word (disappears); then add your own word with a count.
6. Click a word in the cloud — its exact count and share appear under the preview.
7. Export all four formats at 1920 px — PNG (with transparency if selected), JPG, SVG (opens in a browser, text stays crisp), PDF (the cloud on one page).
8. Check on your phone — controls stack above the preview and everything stays usable.

## Upload steps (Wix CMS — same as the other tools)
1. Wix dashboard → CMS → **SaasProducts** → Add Item.
2. Fill the listing fields above; paste the full contents of `index.html` into **appHtml**.
3. Set **published** on, save, then open the live app page and run the checklist above.
