# Code Generator

Static website for creating and decoding cost codes (Product-Project-Category-CostCenter).
Everything is in one file, `index.html`. The data comes from `data/Code_Generator.xlsx`.

## Update the data (no website changes needed)
Replace `data/Code_Generator.xlsx` with the new workbook (same file name) and commit.
The site reads it on every page load.

The workbook needs these sheets and column headers:

| Sheet | Columns the site reads |
|---|---|
| Final | Proyecto, Número, País, Tecnología, Código SPV, Código Proyecto, Producto, Product name, Dimension 3, Dimensión 2, Código Dim 2, Cost-Center, Final Code |
| Dimensiones | Dimensión 1, Dimensión 2, Dimensión 4, Dimensión 5, Código, Nombre |
| Cost Centers | Cost Center, Cost center name (Budget Line is read but not shown) |

What you can change in Excel alone:
- New project, product or code: add rows in `Final` (and the project in `Dimensiones`).
- Cost center description shown in box 3: edit `Cost center name` in `Cost Centers`.
- A name for CC00: add a row `CC00` in `Cost Centers` (otherwise "Project cost (default)" is used).

Use the Data tab on the site to check a new workbook before committing it.

## Change the website itself
Open `index.html` in GitHub, click the pencil icon, edit, and commit. Search (Ctrl+F) for:

| To change | Search for |
|---|---|
| Dimension labels | `DIM_LABELS` |
| Default name for CC00 | `CC_DEFAULT_NAMES` |
| Headlines and intro texts | the text itself, e.g. `Create a cost code.` |
| Colours | `:root {` at the top (`--brand`, `--teal`, `--navy`, `--card-bg`) |
| Data tab password | `DATA_PW_HASH` (replace with the SHA-256 hash of the new password) |
| Browse table columns | `function renderBrowse` and the `<thead>` in the Browse section |

Keep a copy of the previous `index.html` before editing. GitHub also keeps every version
under History, so a change can always be undone.
