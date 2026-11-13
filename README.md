# Verdian Code Generator

Static website for creating cost codes (Product-Project-Category-CostCenter).

## Publish on GitHub Pages
1. Create a repository and upload `index.html` and the `data` folder.
2. Settings > Pages > Deploy from branch > `main` / root.

## Update the code table
Replace `data/Code_Generator.xlsx` with the new workbook (same file name) and commit.
The site reads it on every page load, so no rebuild is needed.
The workbook needs the sheets `Final` and `Dimensiones` with the same column headers as today.
Use the Data tab to check a new workbook before committing it.
