# QuickDiff

QuickDiff is a lightweight, dependency-free web-based diff checker that lets you compare two blocks of text and visualize line-by-line changes.

## Project Structure

```
/code
├── index.html            # Main single-file QuickDiff app (HTML+CSS+JS)
├── README.md             # This file — documentation, usage, testing summary
└── frontend_prototype/
    ├── index.html        # Early prototype UI (no clipboard/sample features)
    └── README.md         # Prototype docs
```

## Getting Started

You can run QuickDiff in two ways:

1. **Open Directly in Browser**
   - Double-click or open `index.html` in your browser.
   - Fully client-side; no server required.

2. **Serve via Local HTTP Server** (optional)
   ```bash
   npm run dev
   ```
   Open your browser to [http://localhost:3000](http://localhost:3000).

_Port 3000 must be free._

## Features

- **Dual Resizable Panes**: Original & Modified textareas, vertical resize enabled.
- **Run Diff**: Click **Run Diff** or press Ctrl+Enter to compute differences.
- **Ignore Whitespace**: Trim and collapse spaces/tabs before diffing.
- **Color-Coded Output**:
  - `+` added lines (light green background)
  - `-` removed lines (light red background)
  - Unchanged lines (white background)
- **Summary Bar**: Displays "X added, Y removed."
- **Copy Results**: Copy diff text (with `+`/`-` prefixes) to clipboard.
- **Load Sample**: Quickly populate with a hidden 10-line Lorem Ipsum pair for instant testing.

<img width="731" height="1115" alt="QuickDiff (2)" src="https://github.com/user-attachments/assets/078541b8-b0c1-44c1-9975-b6a71145dede" />

## Usage

1. Paste or type text into the **Original** and **Modified** panes.
2. Click **Run Diff** to generate the comparison.
3. Review the summary and color-coded diff output.
4. (Optional) Use **Copy Results** or **Load Sample** as needed.

## Testing Summary & Status

| Test Case                 | Status | Notes                                               |
|---------------------------|:------:|-----------------------------------------------------|
| Empty-input validation    | ❌     | Shows "No differences" instead of an input prompt.  |
| Identical texts           | ✅     | Displays "No differences found."                    |
| Special characters        | ✅     | Diff handles symbols correctly.                     |
| Whitespace toggle         | ✅     | Ignores or highlights whitespace as expected.       |
| Clipboard copy            | ✅     | Copies plain diff text with prefixes.               |
| Sample data load & diff   | ✅     | Lorem Ipsum sample shows 4 added, 4 removed.       |
| Textarea resizing         | ✅     | CSS allows vertical resize; manual drag works.     |
| Single-file constraint    | ✅     | All CSS & JS embedded in `index.html`.             |

Minor UX enhancement planned: empty-input validation prompt.

## Technical Details

- **Algorithm**: Myers line-by-line diff (~70 lines of vanilla JS).
- **Single-File Architecture**: `index.html` embeds CSS (≤40 lines) and JS (≤150 lines) with no external dependencies.
- **Styling**: Inline `<style>` for layout, color-coding, and diff-line classes.
- **Browser Compatibility**: Chrome 115+, Firefox 112+, Safari 16+ (Clipboard API supported).

## Additional Documentation

- **Frontend Prototype**: [frontend_prototype/README.md](frontend_prototype/README.md)

Feel free to file issues or contribute enhancements!
