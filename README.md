# UNAERP LaTeX Final Paper Model

LaTeX template for undergraduate final papers (TCC) at the University of Ribeirão Preto (UNAERP), following ABNT standards and the UNAERP library reference manual.

## Usage

1. Upload the project to [Overleaf](https://www.overleaf.com) (or use a local TeX distribution).
2. Set the compiler to **XeLaTeX** and the main document to `main.tex`.
3. Fill in your data in `config/metadata.tex` (authors, advisor, title, year, institution).
4. Write your content in `chapters/` and compile twice so lists and references are updated.

## Structure

```
main.tex                 Entry point
config/
  packages.tex           Packages
  settings.tex           Layout, captions, lists and helper commands
  metadata.tex           Paper data (authors, title, year...)
pretextual/              Cover, title page, approval sheet, abstracts, lists
chapters/                Main content
postextual/              References and appendices
images/                  Figures
reference-manual.pdf     UNAERP reference manual (ABNT NBR 6023)
```

## Helper commands

| Command | Description |
|---|---|
| `\authorssource` | "Fonte: Elaborado pelos autores (year)." below figures and tables |
| `\sourcenote{text}` | Custom source note |
| `\sourcerow{n}` / `\continuedrow{n}` | Source and "continued" rows for `longtable` |
| `\captionof{tabela}{title}` | Caption for tables (listed in "Lista de Tabelas") |
| `\unnumberedtitle{text}` | Centered unnumbered title |
| `\appendixtitle{letter}{title}` | Appendix heading with table of contents entry |

## License

The template source is released under the [MIT License](LICENSE). `reference-manual.pdf` belongs to the UNAERP library and is not covered by this license.
