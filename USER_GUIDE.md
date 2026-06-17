# FlowPie — User Guide

## 1. Introduction
FlowPie is a standalone desktop application for visualizing tabular data as pie charts, bar charts, and arc ring charts. It runs directly from `FlowPie.exe` with no installation, no Python, and no dependencies.

This guide covers every feature from first launch through saving and recovering projects.

---

## 2. First Launch
1. Unzip the downloaded archive. It contains:
   - `FlowPie.exe`
   - `QUICK_REFERENCE.md`
   - `USER_GUIDE.md`
2. Double-click `FlowPie.exe`. The app opens to the **drop zone** — a blank canvas waiting for data.
3. If the app detects a journal file from a previous session that wasn't cleanly saved, it will offer to **recover** that session before doing anything else. Accept to restore your last state, or decline to start fresh.

---

## 3. Importing Data

### Supported Formats
FlowPie reads the following file formats:
- **CSV** (`.csv`) — comma-separated
- **TSV** (`.tsv`) — tab-separated
- **Excel** (`.xlsx`, `.xls`)

### How to Import
- **Drag and drop** your file onto the drop zone in the center of the window.
- Or use **File → Open File** (`Ctrl+O`) to browse for a file.

Once loaded, FlowPie reads the column headers and asks you to select which columns to use for grouping and values.

---

## 4. The Main Window

### Layout
```
┌─────────────────────────────────────────────────┐
│  Menu Bar                                       │
├──────────────────────────────┬──────────────────┤
│  Chart Area (tabs)           │  Side Panel      │
│                              │                  │
│   [Drop Zone / Chart]        │  - Group axis    │
│                              │  - Series colors │
│                              │  - Labels        │
├──────────────────────────────┴──────────────────┤
│  Status Bar                                     │
└─────────────────────────────────────────────────┘
```

### Tab Bar
Each chart lives in its own tab. You can have multiple charts open at once — useful for comparing different views of the same data or different datasets side by side. Close a tab with `Ctrl+W` or the × button.

### Drop Zone
Visible when no data is loaded. Disappears once a file is imported and a chart is created.

### Status Bar
Shows the current application state (Ready, Loading, Dirty, etc.) and brief status messages.

---

## 5. The Side Panel
The side panel controls what the active chart displays and how it looks. Changes apply in real time.

| Control | What it does |
|---------|-------------|
| Group axis | Choose which column groups/segments the chart |
| Series | Choose which column provides the values |
| Colors / Palette | Assign colors to slices, bars, or rings |
| Labels | Toggle and format slice/bar labels |
| Legend | Show or hide the legend |

---

## 6. Chart Types

### Pie Chart
A standard segmented circle. Best for showing proportions of a whole.
- Create: `Ctrl+P` or the toolbar pie button.
- Customize slices via the side panel (colors, labels, grouping).

### Bar Chart
Horizontal or vertical bars. Best for comparing values across categories.
- Create: `Ctrl+B` or the toolbar bar button.
- The side panel controls grouping and series selection.

### Arc Ring Chart
Concentric rings where each ring represents a category or series. Good for multi-level proportion data.
- Create via the toolbar arc ring button.
- Color palette and ring order are configured in the side panel.

---

## 7. Zoom and Navigation
| Action | How |
|--------|-----|
| Zoom in | `Ctrl++` or toolbar |
| Zoom out | `Ctrl+-` or toolbar |
| Fit chart to window | `Ctrl+0` or toolbar |

---

## 8. Exporting
To save a chart as an image:
- **File → Export Image** or `Ctrl+E`.
- Supports PNG export. The exported image reflects the current zoom and layout.

---

## 9. Saving and Loading Projects

### Project Files (.fpie)
A `.fpie` file saves everything: all open tabs, chart types, column selections, colors, and labels. It's the only file you need to fully restore a session.

- **Save**: `Ctrl+S` — saves to the current `.fpie` file (or prompts for a location if unsaved).
- **Save As**: `Ctrl+Shift+S` — saves to a new file.
- **Open Project**: `Ctrl+Shift+O` — loads a previously saved `.fpie` file.

### Autosave Journal
FlowPie writes an append-only journal alongside your `.fpie` file as you work. If the app closes unexpectedly (crash, power loss, etc.), the journal preserves your unsaved changes.

On next launch, FlowPie detects the journal and offers to recover. If you accept, your session is restored to the last journaled state. If you decline, the journal is discarded and you start fresh.

---

## 10. Application States
FlowPie uses an internal state machine. The status bar reflects which state you're in:

| State | Meaning |
|-------|---------|
| **Ready** | No data loaded; drop zone is active |
| **Loading** | File or project is being read |
| **Loaded (Clean)** | Data loaded, no unsaved changes |
| **Loaded (Dirty)** | Changes made since last save |
| **Recovering** | Replaying journal from a previous session |

You cannot accidentally lose the dirty-state indicator — FlowPie will warn you if you try to close or open a new file with unsaved changes.

---

## 11. Troubleshooting

**The app won't open.**
Some systems require you to right-click `FlowPie.exe` and choose "Run as administrator" the first time, especially if Windows SmartScreen blocks the unsigned executable. Click "More info → Run anyway."

**My file won't import.**
Check that it's one of the supported formats (CSV, TSV, XLSX, XLS) and that the first row contains column headers.

**The chart looks wrong / blank.**
After importing, make sure you've selected the correct columns for grouping and values in the side panel. A mismatch (e.g., a text column as the value) will produce an empty or broken chart.

**The app crashed and I lost work.**
On next launch, FlowPie will automatically detect the journal and offer recovery. Accept the prompt to restore your session.

**The recovery prompt appeared but I dismissed it.**
The journal file (named `<yourproject>.fpie.journal`) is still on disk next to your `.fpie` file. Re-open FlowPie and it will prompt again, or you can open the `.fpie` file via `Ctrl+Shift+O` and the journal will be detected.
