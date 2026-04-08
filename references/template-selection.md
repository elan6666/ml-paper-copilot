# Template Selection

Use only the bundled templates in `templates/`.

## Built-In Template Map
- ICLR -> `templates/iclr/main.tex`
- NeurIPS -> `templates/neurips/main.tex`
- ICML -> `templates/icml/main.tex`
- ACL, EMNLP, NAACL -> `templates/acl/main.tex`
- AAAI -> `templates/aaai/main.tex`

## Template Policy
- these bundled templates are venue-compatible house templates designed for drafting and compilation inside this skill
- prefer them over freehand LaTeX
- if the user later supplies an official template, adapt the manuscript into that template without changing the scientific content

## Fallback Policy
- if the venue is not mapped, default to the closest bundled two-column template and state the fallback in QA
- do not reference external template folders

## Bibliography Notes
- the bundled templates assume a local `references.bib`
- keep bibliography wiring simple and compatible with the selected template
- cite only keys present in the provided `.bib`

## Layout Defaults
Unless the user overrides them, use these defaults:
- double-column layout
- 10pt body size for conference-style templates
- sans-serif section headings and serif body text when the template permits
- left-aligned headings and justified body text

## Compile Entry Points
Every bundled venue template uses `main.tex` as the entrypoint.
