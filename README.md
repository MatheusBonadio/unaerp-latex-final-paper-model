# UNAERP LaTeX Final Paper Model

LaTeX template for undergraduate final papers (TCC) at the University of Ribeirão Preto (UNAERP), following ABNT standards and the UNAERP library manuals in `docs/`.

## Usage

1. Upload the project to [Overleaf](https://www.overleaf.com) (or use a local TeX distribution).
2. Set the compiler to **XeLaTeX** and the main document to `main.tex`.
3. Fill in your data in `config/metadata.tex` (authors, advisor, co-advisor, examining board, title, year, institution). The co-advisor is only printed when `\coadvisorName` is not empty, and the subtitle only when `\workSubtitle` (or `\workSubtitleEnglish`) is not empty.
4. Write your content in `chapters/` and compile twice so lists, references and split table marks are updated.
5. Remove the optional elements you do not need from `main.tex` (errata, dedication, acknowledgments, epigraph, lists, glossary, appendices, annexes and index).

## Structure

```
main.tex                 Entry point
config/
  packages.tex           Packages
  settings.tex           Layout, captions, lists and helper commands
  metadata.tex           Paper data (authors, title, year...)
pretextual/              Cover, title page, catalog card, errata, approval sheet, abstracts, lists
chapters/                Introduction, development and conclusion
postextual/              References, glossary, appendices, annexes and index
images/                  Figures
docs/
  manual.pdf             UNAERP manual for presenting scientific papers (formatting)
  citation-manual.pdf    UNAERP citation manual (ABNT NBR 10520)
  reference-manual.pdf   UNAERP reference manual (ABNT NBR 6023)
```

## Notes

- Page counting starts at the title page; the cover, the back of the title page and the errata are not counted, and page numbers are shown from the introduction on.
- The back of the title page holds the catalog card (mandatory), included from `pretextual/FichaCatalografica.pdf`, which is only an example. To use your own:
  1. Generate it at Aluno Online > Ferramentas > Ficha catalográfica (the file is generated as `.docx`).
  2. Export the `.docx` to PDF (for example, File > Save As > PDF in Word).
  3. Replace `pretextual/FichaCatalografica.pdf` with the exported PDF, keeping the same name. To use another name or folder, set its path in `\catalogCardFile` (`config/metadata.tex`).

  The page is included as generated. When `\catalogCardFile` is empty, a 12.5 cm × 7.5 cm placeholder box is shown.
- Primary and secondary section titles are converted to uppercase automatically; tertiary titles use initial capitals, quaternary titles use sentence case and quinary titles (`\paragraph`) are set in italics.
- Citations follow ABNT NBR 10520:2023: authors in parentheses use upper and lower case, e.g. `(Sobrenome, ano, p. 00)`.
- Figures, frames and tables use `[htbp]` so they are placed as close as possible to the text that cites them, as required by the UNAERP manual: `flafter` keeps them from appearing before their citation and `placeins` keeps them inside their section. Use `[H]` only to pin a specific float in place.
- Use a table (`tabela`) when numeric data is the central information, following the IBGE tabular presentation rules (open sides, rules only at the top, below the header and at the bottom). Use a frame (`table`, "Quadro") for textual information, with closed borders.
- Long entries in the table of contents and in the lists are set ragged right instead of justified.

## Helper commands

| Command | Description |
|---|---|
| `\authorssource` | Source note below figures and tables, with the text of `\sourceText` in `config/metadata.tex` |
| `\sourcenote{text}` | Custom source note |
| `\sourcerow{n}` | Source row for the last foot of a `longtable` |
| `\continuesmark` | Placed after the caption in `\endfirsthead`: prints "(continua)" when the table breaks; "(continuação)" and "(conclusão)" are added to the following pages automatically |
| `\begin{tabela}` / `\caption` | Tables (listed in "Lista de Tabelas"); `table` is used for frames (quadros) |
| `L{width}` | Left-aligned paragraph column for frames, used instead of `p{width}` to avoid stretched lines in narrow cells |
| `\begin{longquote}` | Direct quotation with more than three lines |
| `\begin{alineas}` / `\begin{subalineas}` | Lettered items `a)` and dashed subitems |
| `\unnumberedtitle{text}` | Centered unnumbered title |
| `\postextualtitle{text}` | Unnumbered post-textual title with table of contents entry |
| `\appendixtitle{letter}{title}` / `\annextitle{letter}{title}` | Appendix and annex headings with table of contents entry |
| `\examinerfield{name}{institution}{role}` | Signature line for the approval sheet |
| `\begin{indexentries}` | Index entries with `\item`, `\subitem` and `\subsubitem` |

## License

The template source is released under the [MIT License](LICENSE). The PDF manuals in `docs/` belong to the UNAERP library and are not covered by this license.
