# Decisions

Newest first. Each entry records what was decided and why.

## 2026-11-22 — Initial scope

- **Separate tool that hands off to Writer.** Converter is a file in, `.ptrn` out. The designer opens the result in Writer to fix it.
- **No AI.** The result doesn't need to be perfect. The goal is getting the `.ptrn` file started as well as possible.
- **Text first, then PDF and .docx.** All formats become text and share one parser, so plain text is built first and the other formats are text extractors added in front of it.
- **Shared row format.** Rows are rewritten into the format defined in `ptrn-js`, so Writer can read them.
- **Browser-first,** with a server only if a format requires it.
- **Crochet and knitting first,** because those are what the CYC standards and Ravelry cover.
