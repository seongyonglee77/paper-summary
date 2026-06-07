# paper-summary

`paper-summary` is a Codex skill for turning scholarly papers into structured, evidence-grounded notes. It is designed for PDFs, DOCX files, Markdown, pasted text, citation metadata, and multi-paper comparisons.

## What It Does

- Summarizes the paper's research question, method, findings, and contribution
- Highlights critical points and limitations for citation or discussion
- Supports quick, standard, deep, and compare-style outputs
- Encourages page-cited quotations when the source text supports them

## Structure

```text
paper-summary/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── output-templates.md
    └── quality-checklist.md
```

## Usage

Use this skill when you need:

- a compact paper summary
- a literature review note
- a critique memo
- a classroom discussion brief
- a comparison across multiple papers

## Reference Files

- `references/output-templates.md` contains ready-to-use output shapes for quick, standard, deep, and compare modes.
- `references/quality-checklist.md` provides a short self-check for evidence, completeness, and quote handling.

## Example Prompts

- Summarize this paper with page-cited quotes.
- Give me the unique contribution and critical points.
- Compare these three papers and show methodological differences.
- Turn this paper into literature review notes.
