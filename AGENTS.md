# Agent Instructions

- This workspace contains Chinese Markdown files. When reading them in PowerShell, use UTF-8 explicitly to avoid mojibake:
  ```powershell
  [Console]::OutputEncoding = [System.Text.UTF8Encoding]::new(); Get-Content -Raw -Encoding UTF8 -LiteralPath 'path'
  ```

## Service Campaign Markdown Cleanup

When the user asks to make a PDF-extracted service campaign Markdown file more readable, keep the source facts intact and reorganize the document for workshop use.

- Preserve the original source metadata near the top, including source PDF path, page count, publication date, case number, ElsaPro procedure number, fault number, and campaign end date when available.
- Remove PDF extraction noise such as page headers/footers, page numbers, repeated table-of-contents blocks, repeated "return to index" lines, and broken line wraps.
- Do not invent technical conclusions. Rephrase only enough to make the extracted text readable and keep campaign codes, part numbers, APOS numbers, dates, quantities, and diagnostic labels exact.
- Prefer this structure for cleaned campaign files:
  1. Title with campaign code and subject.
  2. Document summary.
  3. Vehicle/basic data.
  4. Prerequisites or related campaigns that must be checked first.
  5. Workshop procedure as numbered steps.
  6. Parts and tools.
  7. Customer contact guidance.
  8. Claim/reporting method and labor tables.
  9. Removed-parts handling.
  10. Identification/record entry instructions.
  11. Assistance/contact note.
- Convert dense key-value blocks and labor/parts data into Markdown tables.
- Use bullets for campaign-code lists and short operational notes.
- Use blockquotes for warnings/cautions.
- Use fenced code blocks for exact text that must be entered in a record, such as `19PA performed`.
- If another cleaned campaign file already exists, match its style before introducing a new layout.
