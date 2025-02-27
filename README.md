# intERPrise Documentation

Published at [doc.i-nterprise.org](https://doc.i-nterprise.org/).

## Design Principals

Our tooling decisions were based on the following considerations:

- Choice of markup language:
    - Prefer plain text over binary source formats
    - Prefer maximum choice in tooling over being bound to a single / small choice of tools
- Integrated version control
- Prefer publishing static HTML over rendering at runtime (think MediaWiki)
- Our chosen markup language: [Markdown](https://daringfireball.net/projects/markdown/)
    - Note that MkDocs uses the [Python-Markdown](https://python-markdown.github.io/) library to render Markdown documents to HTML. It is almost completely compliant with the [reference implementation](https://daringfireball.net/projects/markdown/), although there are a few very minor [differences](https://python-markdown.github.io/#differences).
- Our chosen rendering tools:
    - [MkDocs](https://www.mkdocs.org/)
    - [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

Useful resources:

- [How to write a good design document](https://grantslatton.com/how-to-design-document)

## Contents

Key files:

- `mkdocs.yml`: Configuration file
- `docs/`: Source documents (Markdown)
- `site/`: Output (HTML - not committed to git)
