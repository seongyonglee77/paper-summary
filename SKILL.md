---
name: paper-summary
description: Summarize academic papers from PDF, DOCX, Markdown, pasted text, or citation metadata into structured, evidence-grounded research notes. Use when the user wants a paper summary, contribution breakdown, methods/results synthesis, critical reading note, page-cited quotes, or comparison across one or more scholarly papers.
---

# Paper Summary

Use this skill for research papers, journal articles, conference papers, theses, and manuscript drafts. Do not use it for news, blogs, legal documents, or general nonfiction.

## Inputs

- local PDF, DOCX, MD, or TXT
- pasted paper text
- DOI, title, citation, or URL if the paper text can be located
- multiple papers for comparison

## Core Rules

- Read the paper itself when possible, not just metadata.
- Do not invent missing details.
- If text is incomplete or OCR-noisy, say so clearly.
- Distinguish paper content from interpretation.
- Use direct quotes sparingly and always include page numbers: `"..." (p. 12)` or `"..." (pp. 12-13)`.
- Prefer short page-cited quotes for definitions, key claims, and especially sharp wording.
- Do not just rewrite the abstract. Prioritize method, evidence, findings, limitations, and significance.

## Default Output

Unless the user asks otherwise, produce:

### Citation

- Title
- Authors
- Year
- Venue if available

### One-Sentence Takeaway

One sentence capturing the paper's central contribution.

### Structured Summary

- Research question
- Context/background
- Method
- Data/participants/materials
- Key findings
- Unique contribution
- Critical points
- Limitations
- Why it matters

### Quotes

- Include 1 to 3 short direct quotes with page numbers when useful.

## Summary Modes

### Quick

Use for fast screening. Return 5 to 8 bullets covering:

- topic
- research question
- method
- main findings
- unique contribution
- critical point or caution

### Standard

Default mode. Return a compact structured summary with the default output sections.

### Deep

Use when the user wants close reading, literature review support, or critique. Add:

- argument flow
- theoretical framing
- evidence strength
- critique
- notable quoted passages with pages

### Compare

For multiple papers, normalize each paper first, then compare:

- research focus
- method/data
- main findings
- unique contribution
- critical points
- limitations

Include a comparison table and a short synthesis paragraph.

## Required Extraction Targets

Always try to identify:

- research problem
- research question or objective
- method/design
- data, participants, corpus, or materials
- key findings
- unique contribution relative to prior work
- critical points the user should notice when reading, citing, or discussing the paper
- limitations or unanswered questions

## Critical Points

`Critical points` should highlight the most important issues a serious reader should notice, such as:

- a conceptual tension or ambiguity
- a methodological weakness
- a narrow sample or context
- overclaimed implications
- a key assumption
- a particularly important distinction or definition

Keep this section concise and useful for citation, discussion, or critique.

## Workflow

1. Identify file type and text quality.
2. Extract or read the paper text.
3. Capture citation metadata if available.
4. Locate high-value sections: abstract, introduction, method, results, discussion, conclusion, limitations.
5. Extract the required targets.
6. Draft the requested mode.
7. Self-check for unsupported claims, missing sections, and missing page markers on direct quotes.

## Fallback Behavior

- If only metadata is available, produce a brief provisional summary and mark it incomplete.
- If sections are missing, say `Not clearly available in the provided text`.
- If page numbers cannot be recovered reliably, do not fabricate them; say page markers were unavailable in the extracted text.

## Output Variants

Support these when requested:

- literature review paragraph
- annotated bibliography entry
- presentation notes
- critique memo
- classroom discussion brief
- multi-paper comparison matrix

## Minimal Folder Plan

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

## Recommended References

`references/output-templates.md`
- quick, standard, deep, compare templates

`references/quality-checklist.md`
- research question identified
- method and findings separated
- unique contribution stated
- critical points stated
- direct quotes page-cited
- uncertainty disclosed
- no hallucinated details

## Example Prompts

- Summarize this paper with page-cited quotes.
- Give me the unique contribution and critical points of this article.
- Compare these three papers and show methodological differences.
- Turn this paper into literature review notes.
- Summarize this study and include 2 direct quotes with page numbers.
