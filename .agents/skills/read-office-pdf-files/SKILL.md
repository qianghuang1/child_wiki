---
name: read-office-pdf-files
description: "Use only for local Office files and PDFs that need to be read, summarized, extracted, converted, compared, or answered from. Triggers: .pdf, .docx, .pptx, .xlsx, .xlsm, .csv, .rtf, Word document, PowerPoint, Excel workbook, spreadsheet, deck, slides, report, contract, invoice, or resume. Convert with local markitdown before reasoning over the contents."
---

# Read Office and PDF Files

Use `markitdown` to convert **local** Office files and PDFs into Markdown before reading, summarizing, extracting, or answering questions about them. This skill is not for remote URLs, SharePoint/OneDrive files that are not downloaded locally, or cloud extraction workflows.

Basic syntax:

```sh
markitdown <file>
markitdown <file> -o <output.md>
```

On Windows, quote paths that contain spaces:

```powershell
markitdown "C:\path\Quarterly Report.pdf" -o "C:\path\Quarterly Report.md"
```

## Workflow

1. Confirm the file exists on the local filesystem.
2. Convert it with `markitdown`, preferably to `original-name.converted.md` for large files.
3. Read the converted Markdown with normal text tools.
4. Answer from the converted text and mention any obvious conversion limits.

## Failure handling

If the file is password-protected, encrypted, corrupted, inaccessible, scanned without extractable text, or `markitdown` fails or returns empty/useless output, stop and notify the user plainly: `markitdown` cannot read this file. Do not invent content or keep trying unrelated extraction methods unless the user asks for another approach.

## Guardrails

- Do not inspect binary Office/PDF files directly with plain-text readers.
- Do not use Document Intelligence or other cloud services from this skill.
- Do not claim conversion is perfect; formatting, images, charts, comments, formulas, and layout may be missing.
- For structured editing or deep analysis of spreadsheets, decks, or Word files, use a file-type-specific workflow instead.
