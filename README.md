# ST-342 - Mathematics of Random Events: Lecure Notes

Lecture notes for the ST-342 Mathematics of Random Events module taught at the University of Warwick in the academic year of 2021/2022.

## Top-level directory layout

```
ST342-bookdown/
├──  index.Rmd
├── 01-intro.Rmd
├── 02-references.Rmd
├── _bookdown.yml
├── _output.yml
├──  references.bib
├──  preamble.tex
├──  mathjax_header.html
├──  README.md
└──  style.css
```

- `index.Rmd`: contains the first chapter and the YAML metadata
- .Rmd files: contatin the content of each individual chapted, merged with the `index.Rmd` to render the book. By default, bookdown merges all .Rmd files by the order of filenames, e.g., `01-xxx.Rmd` will appear before `02-xxx.Rmd`
- `_bookdown.yml` : Configuration file for bookdown, allows you to specify optional settings to build the book
- The `_output.yml`: Specifies the formatting of the HTML, LaTeX/PDF, and other formats
- `preamble.tex`: Used to specify the document settings and declare LaTeX commands for the LateX/PDF output
- `mathjax_header.html`: Used to declare LaTeX commands for the HTML output
- `style.css`: Used to adjust the appearance and styles of the HTML output
- `references.bib`: Bibliographic data used with the `natbib` package to render the citations

After rendering the book all outputs and are stored in the `_book` folder.

## Software version

This book compiles fine with the following software configuration:
`R_4.1.1
bookdown_0.24.1
knitr_1.33
rmarkdown_2.10
xfun_0.25
Pandoc_2.14.1`

## Boookdown issues and workarounds

- In the Postponed Proofs Appendix `:::{.proof name="Proof of Theorem \@ref(label)}` blocks are used to write the proofs. This produces expected results in the PDF output while in the HTML the proofs begin with *Proof. (Proof of Thoerem)*
- Mathematical symbols cannot be used inside theorem (and proof, definition etc.) names. Solution: write the name of a theorem in bold separately.
- remark, proofs and solutions cannot be numbered and referenced in HTML. Solution: avoid referencing remarks, proofs, solutions
- `pdflatex` is preferred over `xelatex` because of the unexpected look of `\mathcal` and `\mathbb` fonts in the PDF output and some versions of `xelatex` define `\C` internally which can cause errors.
- Bookdown `0.22` added spurious lines at the end of proofs and other environments. Bookdown `0.22.17` failed to render theorems and other environments if they ended with a list. Bookdown `0.24.1` fixed both issues.

## MathJax limitations and workaraounds

- `\mathds` is not supported by MathJax. For the double struck one "𝟙" symbol we define a new command `\dsone` which for the PDF output is defined as `\mathds{1}` and for the HTML we use the unicode character `\unicode{x1D7D9}`
- The `xymatrix` pacakge is not supported by MathJax. We have redefined the `xymatrix` command to issue a note about the missing diagram and referring the reader to the PDF version.

