# Word Cloud Studio — Free Word Cloud Generator

Turn text, documents and datasets into beautiful, customisable word clouds — real frequency analysis with two-word phrase detection, seven shapes plus your own image silhouette, live design controls, and exports up to 4K. **100% in your browser**: every file is parsed on your device and nothing is uploaded.

**▶ Live on Asif SaaS Studio:** open the tools catalogue and choose *Word Cloud Studio* (slug `word-cloud-studio`).

By **Dr. Asif Ahmad** — Asif SaaS Studio

Category **Design** · Version **1.0** · MIT License

## Run it
Open `index.html` in any modern browser — or from this repo via any static host. No build step, no dependencies, no server, no account.

## What it does
1. **Intake** — paste or type text, or upload **.txt, .md, .csv, .docx, .pdf, .xlsx** — DOCX, PDF and XLSX are parsed by real readers inside the page (scanned/subset-font PDFs get a clear "paste the text instead" message, never garbage).
2. **Analyse** — Unicode tokenising (English, Urdu, Arabic and other scripts), word-frequency counting, stop-word lists for EN/UR/AR, number and minimum-length filters, and two-word phrase detection ("food safety" stays one entry).
3. **Design live** — a collision-free spiral layout engine; 7 shapes (rectangle, circle, heart, star, cloud, lightbulb, tree) or a custom silhouette from your own image; 6 fonts, orientation, 7 colour palettes or custom colours, backgrounds including transparent, word spacing.
4. **Edit & inspect** — highlight, boost, remove or add individual words; a full frequency table; click any word in the cloud to see its exact count and share.
5. **Export** — PNG, JPG, SVG (real text elements) and PDF at 960 / 1920 / 2560 / 3840 px, transparent PNG, and the frequency data as CSV.

## An honest note
Version 1.0 is **frequency analysis, not AI extraction** — counting words is not the same as understanding them, and a cloud shows what was said most often, not what mattered most: frequency is not a validated qualitative theme. Genuine AI keyword extraction and sentiment need a model; the documentation (Chapter 11) lays out the staged plan — an optional serverless backend proxy holding the API key (text sent only on explicit opt-in), or an on-device model in the standalone hosted version, plus a clearly-labelled lexicon sentiment tint. Save-projects needs IndexedDB, which conflicts with the sandboxed no-storage rule, so it is staged for the standalone version only; comparison mode and batch generation are pure front-end and planned for v1.1.

## Files
- `index.html` — the complete app, self-contained: all CSS and JavaScript inline, 47.9 KB. No localStorage, no service workers, no browser permissions, no parent-window access — safe in a sandboxed iframe; files are processed locally and never uploaded.
- `word-cloud-studio-test-report.md` — the full test report and the Wix catalogue listing.
- Documentation (PDF) → `docs/word-cloud-studio-docs.pdf` — user guide & technical documentation, with the shipped cores in the appendices.

## Testing
45/45 automated checks against the shipped cores — frequency and phrase detection, multilingual tokenising (Urdu/Arabic), shape-mask point tests, layout with zero overlapping boxes, and real DOCX/XLSX/PDF fixtures extracted by the app's own parsers; the zlib and image-PDF export writers verified against standard readers. Full report: `word-cloud-studio-test-report.md`.

## Documentation
Complete documentation: `docs/word-cloud-studio-docs.pdf` (17 pages — workflow, analysis engine, layout and shapes, design controls, exports, the AI roadmap & deployment plan, research-honesty notes, verification, and the verbatim cores).

Created by Dr. Asif Ahmad · Asif SaaS Studio · v1.0
