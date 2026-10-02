---
name: markitdown
description: Convert files (PDF, Word, PowerPoint, Excel, HTML, CSV, JSON, XML, images, audio, ZIP, YouTube URLs) to Markdown with Microsoft's markitdown, installing `markitdown[all]` first if it is missing. Use when the user asks to convert a document to Markdown or to extract its text (e.g. "轉成 Markdown", "把這個 PDF 轉 md").
argument-hint: <file-or-url> [output.md]
---

# markitdown

Convert `$ARGUMENTS` to Markdown.

## 1. Ensure markitdown is installed

```bash
command -v markitdown >/dev/null || pip install "markitdown[all]"
```

## 2. Convert

- Save to a file: `markitdown <input> -o <output.md>`
- Print to stdout: `markitdown <input>`
- From stdin: `cat <input> | markitdown -x <extension>`

If no output path is given, write `<input basename>.md` next to the input file,
then show the user the output path and a short preview (first ~40 lines).

## Notes

- Scanned PDFs or images without a text layer may produce little or no text; say so instead of guessing at content.
- Azure Document Intelligence (`-d -e <endpoint>`) is only used when the user supplies an endpoint.
