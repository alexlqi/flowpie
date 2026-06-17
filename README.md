# FlowPie

A portable desktop app for turning spreadsheets and CSV files into pie charts, bar charts, and arc ring charts — no installation, no dependencies.

![Platform: Windows](https://img.shields.io/badge/platform-Windows-blue) ![License: EULA](https://img.shields.io/badge/license-Proprietary%20EULA-lightgrey)

---

## Features

- **Three chart types** — pie, bar, and arc ring (concentric rings)
- **Drag-and-drop import** — drop a file onto the window and start charting immediately
- **Multi-tab workspace** — open as many charts as you need at once
- **Real-time side panel** — change grouping, colors, labels, and series; the chart updates instantly
- **PNG export** — save any chart as an image with one keystroke
- **Project files** (`.fpie`) — save and restore your full session, including all tabs and styling
- **Crash recovery** — an append-only journal lets you pick up right where you left off after an unexpected close
- **Zero install** — ships as a single `FlowPie.exe`; just unzip and run

---

## Supported Formats

| Format | Extensions |
|--------|-----------|
| Comma-separated | `.csv` |
| Tab-separated | `.tsv` |
| Excel | `.xlsx`, `.xls` |

The first row of your file must contain column headers.

---

## Quick Start

1. Unzip the downloaded archive.
2. Double-click `FlowPie.exe`.
3. Drag a data file onto the drop zone, or use **File → Open File** (`Ctrl+O`).
4. Select which column to group by and which column to use as values in the side panel.
5. A chart appears. Pick a chart type from the toolbar or a keyboard shortcut.

> **First-run note:** Windows SmartScreen may block an unsigned executable. Click **More info → Run anyway**, or right-click the `.exe` and choose **Run as administrator**.

---

## Keyboard Shortcuts

| Action | Shortcut |
|--------|---------|
| Open data file | `Ctrl+O` |
| Open project | `Ctrl+Shift+O` |
| Save project | `Ctrl+S` |
| Save project as | `Ctrl+Shift+S` |
| Close tab | `Ctrl+W` |
| New pie chart | `Ctrl+P` |
| New bar chart | `Ctrl+B` |
| Zoom in | `Ctrl++` |
| Zoom out | `Ctrl+-` |
| Fit to window | `Ctrl+0` |
| Export image | `Ctrl+E` |

---

## Saving Your Work

**Projects** are saved as `.fpie` files and preserve all open tabs, chart types, column selections, colors, and labels.

**Crash recovery:** FlowPie keeps a journal file (`.fpie.journal`) alongside your project as you work. If the app closes unexpectedly, the journal is detected on next launch and you're offered the option to recover your last session.

---

## Documentation

- [`QUICK_REFERENCE.md`](QUICK_REFERENCE.md) — one-page summary of every key feature
- [`USER_GUIDE.md`](USER_GUIDE.md) — full walkthrough: importing, charting, exporting, recovery, troubleshooting
- [`LICENSE.md`](LICENSE.md) — end-user license agreement (English / Español)

---

## License

FlowPie is free to use for personal, academic, and research purposes under a proprietary EULA. You may not modify, reverse-engineer, or resell it. See [`LICENSE.md`](LICENSE.md) for full terms.

Copyright © 2026 Alejandro Andrade ([@alexlqi](https://github.com/alexlqi))
