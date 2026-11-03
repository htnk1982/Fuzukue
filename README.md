# Fuzukue (文机)

**A print-first Japanese word processor with the feel of a dedicated word-processing machine.**

Fuzukue (ふづくえ, *writing desk*) composes documents on a page defined by a fixed **number of characters × number of lines**. Instead of placing floating text boxes on a canvas, you write directly into a grid, draw rules, arrange headings and tables, and print the result. Its design brings the focused workflow of classic Japanese word processors to Windows.

> **Version:** `1.0.10c.1-alpha`  
> **Platform:** Windows 10 / 11  
> **Launch:** Edge or Chrome in application mode; optional standalone Windows executable

## Design principles

- **One screen, no modal dialogs.** Editing, formatting, searching and command selection stay in a single workspace. A command ribbon and status line provide context; help and outlines open in a side panel.
- **Typesetting by the grid.** Control paper size, characters per line, lines per page, alignment, indentation and page breaks. Documents remain focused on print layout.
- **Black, white and halftones.** The editor displays the printed appearance, including line work, shading and typographic emphasis.
- **Keyboard-first operation.** Ten function-key groups expose file operations, editing, character formatting, paragraphs, placement, insertion, rules, document format and view controls. Commands can also be clicked.
- **Readable source files.** The native `.fzk` format is UTF-8 text with explicit, human-readable layout instructions; it is suitable for inspection and use with AI tools.

## Features

### Editing and document structure

- Paragraphs, titles, numbered headings, symbol headings and nested lists, with configurable numbering systems.
- Bold, underline, emphasis dots, shading, reversed text, strikethrough, enlarged characters and links.
- Outlining, search and replace, table of contents, page numbering, headers and footers.
- Undo/redo, autosave and recovery data, plus a recent-version history.

### Page design

- Draw rules with the keyboard or mouse; add boxes, separators and decorative headline treatments.
- Create and restyle tables, including newspaper, statistical and financial-report styles.
- Insert images and flowcharts. Flowcharts can be exchanged with Mermaid diagrams in Markdown.
- Use a landscape **presentation-document** layout with a main text column and a separate figure area.

### Import and export

| Format | Support |
| --- | --- |
| `.fzk` | Native, human-readable UTF-8 document; preserves Fuzukue-specific structure and styling |
| `.md` (GitHub Flavored Markdown) | Open, paste, format and export; includes tables, lists, code, links and supported Mermaid flowcharts |
| `.txt` | Open and export plain text |
| `.docx` | Export Word documents with headings, numbering, tables and other supported formatting |
| `.pptx` | Export PowerPoint slides, including the presentation-document layout |
| PDF / paper | Print using the browser or system print dialog; choose **Save as PDF** to produce a PDF |

**Format note:** `.fzk` is the authoritative format for Fuzukue-specific page design. Markdown is useful for sharing document structure with other tools, but not every native layout or decoration has a Markdown equivalent.

## Getting started (no installation)

1. Extract the distribution ZIP to any directory. Japanese characters and spaces in the path are supported.
2. Double-click **`文机を起動.bat`**.
3. The application opens in Microsoft Edge application mode, or Chrome if Edge is unavailable, with a blank document.
4. Start typing. Press **F1** for the built-in guide or **Ctrl+K** to search commands.
5. Press **Ctrl+S** to save an `.fzk` file, or **Ctrl+P** to print or save as PDF.

The distribution uses fonts already installed on your PC. The defaults are **BIZ UD Mincho** and **BIZ UD Gothic**, with fallbacks if unavailable. You can change fonts under **F9 → F**.

## Quick command reference

| Key | Function |
| --- | --- |
| **F1** | Help and command reference |
| **F2** | Files, save, open, print, export |
| **F3** | Editing, undo/redo, search and replace |
| **F4** | Character formatting |
| **F5** | Paragraph type, headings and lists |
| **F6** | Alignment, indentation and pagination |
| **F7** | Insert tables, figures, diagrams and contents |
| **F8** | Draw rules and apply decorations |
| **F9** | Paper, grid, fonts and document formatting |
| **F10** | View, zoom, outline and command list |
| **Ctrl+S** | Save |
| **Ctrl+P** | Print / Save as PDF |
| **Ctrl+K** | Search commands |
| **Ctrl+Shift+O** | Show or hide the outline |

To execute a function-key command, press its group key (for example **F5**) and then the letter or number shown in the ribbon. Press **Esc** to cancel the current command selection. The menu tiles are also clickable.

## Optional: build a standalone `.exe`

The distribution includes a Go-based Windows host that can package the application as a single executable.

1. Install Go once (for example, from a terminal with `winget install GoLang.Go`).
2. Run **`host/build-windows.bat`**.
3. The build script places **`Fuzukue.exe`** in the parent folder (approximately 10 MB, according to the supplied documentation).

See **`host/README.md`** for host-specific details. The `.exe` version can also be registered to open `.fzk` files via the supplied **`文机を関連付け（exe版）.bat`** script.

## Sample documents and documentation

The distribution's **`samples/`** directory includes example `.fzk` documents, a Markdown example, and **`取扱説明書.fzk`**, a complete manual that also demonstrates Fuzukue's formatting features. Additional design details for the Markdown implementation are documented in **`GFM対応設計.md`**.

## Current scope

Fuzukue is designed around horizontal Japanese text and one-character-per-cell composition. It does **not** attempt to reproduce every desktop-publishing feature: vertical writing, text wrapping around photographs and newspaper-style column rules are outside the described design. PowerPoint and Word exports reproduce supported elements, but some details differ from the editor's printed appearance.

This is an **alpha release**. Keep a backup of important documents, and inspect exported files before sharing them.
