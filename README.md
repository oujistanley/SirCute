# Logic Gate Drawer

A single-page web app that turns a truth table (2 to 5 variables) into SOP and POS expressions and draws the matching two-level logic circuits.

## Features

- Click truth table outputs to cycle 0, 1, and X (don't care)
- Quick entry: `m(1,3,7)`, `M(0,2,5)`, and `d(5,9)` for don't cares
- Canonical SOP and POS (as lists and as full expressions)
- Simplified SOP and POS using Quine-McCluskey with a minimal cover search
- Circuit diagrams drawn as SVG, with vertical input rails, inverters, and AND/OR gates sized to their inputs
- Download each circuit as a PNG or SVG (black on white, ready for reports)
- Custom variable names, like X Y Z or W X Y Z

## Run it

No install or build step. Open `index.html` in a browser.

## Host it on GitHub Pages

1. Push this folder to a GitHub repository.
2. In the repo, go to Settings, then Pages.
3. Set the source to the main branch and the root folder, then save.
4. Your app will be live at `https://<your-username>.github.io/<repo-name>/`.

## How the code is organised

Everything is in `index.html`:

- **HTML:** the table, controls, and result panels
- **CSS:** theme, layout, and SVG styling
- **JavaScript:**
  - `qm()` finds prime implicants and the smallest cover
  - `sopText()` and `posText()` format expressions
  - `drawCircuit()` builds the SVG for a list of terms
  - `compute()` ties it together whenever the table changes

## Ideas for later

- Typing an expression to get its truth table
- Desktop version in C++ reusing the same algorithm
