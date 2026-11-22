# Converter

Turn an existing pattern file into the best `.ptrn` file it can, as a starting point for the designer to finish in [Writer](https://github.com/ptrnformat/writer).

Planned home: [convert.ptrnformat.org](https://convert.ptrnformat.org) · Status: **planning**

## What it does

- Takes a pattern file and outputs a `.ptrn` file.
- Pulls out what it can recognise: title, materials, gauge, sizes, abbreviations, sections and rows.
- Rewrites rows into the shared row format from [`ptrn-js`](https://github.com/ptrnformat/ptrn-js), the same format Writer uses.
- Keeps anything it can't recognise as text instead of dropping it, so the designer can fix it in Writer.

It won't be perfect, and it doesn't need to be. The aim is to save the designer from starting with a blank file.

## Input formats

Every format gets turned into text, which then goes through one shared parser. Adding a format just means adding a text extractor in front of the parser.

1. **Plain text** first, because it's the core the other formats rely on.
2. **PDF**, the format most patterns are in today. It's also the hardest to get clean text from (columns, page breaks, charts as images).
3. **.docx**, because many designers write in Word or Google Docs.

More formats can be added later.

## What it doesn't do

- **No AI.** The conversion is rule-based.
- **No editing.** The output is opened in Writer for review and fixes.
- **No promise of a perfect result.**

## How it works

- Browser-first. Files are read in the browser and not uploaded, where possible. A server is added only if a format can't be handled in the browser.
- Crochet and knitting first. Specialty forms come later.

## Open questions

- **Scanned PDFs.** Reading them needs OCR, which is machine learning. Decide whether that fits the no-AI rule or whether scanned PDFs are out of scope.
- **Charts.** Charts in PDFs are usually images, so they probably carry over as images for the designer to rebuild in Writer.
- **Draft flag.** Whether Converter's output should be marked as a draft in the file itself (see Writer).
- **Optional graph in the spec.** Converter output usually won't have a stitch graph, so the spec needs to allow files without one.

## Decisions

Decisions and the reasons behind them are logged in [DECISIONS.md](DECISIONS.md).

## License

[Apache 2.0](LICENSE)
