# Now Captures

**Screenshot evidence to Word & PDF — fast, private, in-house.**

A single-file, browser-based tool for QA testers to capture, annotate, organize, and export test evidence as polished Word (`.docx`) and PDF reports. No install, no accounts, no cloud — everything runs in your browser and stays on your machine.

> **Try it live:** _(GitHub Pages URL — fill in after publishing)_

---

## What it does

- **Persistent screen capture** — share your screen once, then snap as many shots as you want without re-prompting
- **Live Capture** — a floating capture window (Chrome/Edge) that stays on top of any app on any monitor, so you can capture while navigating multi-monitor setups
- **Inline annotation** — arrows, straight lines, boxes, freehand pen, and a translucent highlighter, all with a color picker; click any shape to select, move, or delete it
- **Test-case grouping** — organize screenshots into named test cases with Pass / Fail / Blocked / Untested status tags
- **Bulk copy or move** — select multiple screenshots with checkboxes and copy them to multiple test cases at once, or move them to a single case
- **Include / Exclude toggles** — tick which test cases go into the next export and which stay out
- **Status filter on export** — export only the failed shots, only pass, or everything
- **Short clip recording** (≤30 s) — for bugs that need motion; saves to disk as `.webm`
- **OCR suggestions** — the tool reads text off any screenshot and offers it as an editable suggestion you can insert, replace, or copy
- **Word and PDF export** — one click; the report includes a summary table and per-case breakdown
- **Auto-save** — everything lives in your browser's IndexedDB storage, so a crash doesn't lose your work

## Privacy

Your screenshots and notes **never leave your machine**. There is no server, no cloud, no account, no telemetry, no analytics. The tool is a single HTML file that runs entirely in your browser. When you export a Word or PDF report, that file downloads straight to your computer — no upload happens.

Three JavaScript libraries (`docx`, `pdf-lib`, and `Tesseract.js` for OCR) load on demand from public CDNs (jsdelivr, cdnjs, unpkg) with fallback across all three. Once loaded, the tool works offline.

## How to use

1. Open the tool in **Chrome, Edge, Safari, or Firefox** at the URL above.
2. Click **Capture full screen** or **Capture region**. Pick a screen the first time — after that, every capture is instant.
3. **Annotate** with the pen, arrow, or highlighter. Tag as Pass / Fail / Blocked. Group into test cases.
4. Click **Export Word** or **Export PDF** for a polished report.

For multi-monitor testing, click **Live Capture** to open a floating capture button you can drag onto any monitor.

## Requirements

- A modern browser: **Chrome, Edge, Safari, or Firefox** (recent version)
- For the floating Live Capture window and Document Picture-in-Picture: **Chrome or Edge**
- Screen capture requires HTTPS or localhost — served via GitHub Pages, this is automatic

## Tech stack

- **HTML, CSS, and vanilla JavaScript** — no framework, no build step, no server
- **Browser APIs** — `getDisplayMedia`, `IndexedDB`, `Canvas`, `MediaRecorder`, `Document Picture-in-Picture`
- **Libraries** (loaded on demand from CDN): `docx`, `pdf-lib`, `FileSaver.js`, `Tesseract.js`

The whole tool is one `index.html` file. No `node_modules`, no compilation, no dependencies to install. Open the file in a text editor and edit; refresh the browser and see the change.

## Development / self-host

To run locally (for editing or offline use), you need a local web server because browsers block screen capture on `file://` URLs.

```bash
# From the folder containing index.html:
python3 -m http.server 8765
# Then open http://localhost:8765/ in your browser
```

Any static server works — `npx http-server`, VS Code's Live Server extension, etc.

## Contributing / bug reports

Open an issue in this repository with:
- What you were doing
- What you expected to happen
- What actually happened
- Your browser and OS

Pull requests welcome for fixes and small improvements.

## License

MIT — see [LICENSE](LICENSE) for the full text. Free for personal and commercial use.

## Author

Built by Raghu, for QA teams who spend too much time formatting evidence.
