# Bundled Templates

This directory contains the self-contained drafting templates used by `ml-paper-copilot`.

## Policy
- use only these bundled templates during automatic drafting
- treat them as venue-compatible house templates rather than redistributed official kits
- each venue folder uses `main.tex` as the compile entrypoint
- each venue folder also contains a placeholder `references.bib`

## Available Bundles
- `iclr/`
- `neurips/`
- `icml/`
- `acl/`
- `aaai/`

## Compile Pattern
Run from the selected venue directory:

```text
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## Layout Defaults
- two-column layout
- 10pt conference-style body text
- left-aligned sans-serif section headings
- justified serif body text
