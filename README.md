# ST342 - Mathematics of Random Events: Lecure Notes

Lecture notes for the ST342 Mathematics of Random Events module taught at the University of Warwick in the academic year of 2021/2022.

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


## Issues and workarounds
- In fenced `Div` blocks such as `:::{.proof}` compiled with book down `0.22` extra blank lines are insterted inside the corresponding latex environments. Correct output is produced when using book down `0.22.17`
- `\mathds` is not supported by MathJax. For the double struck one 𝟙 symbol we define a new command \dsone which for the PDF output is defined as `\mathds{1}` and for the HTML we use the unicode character `\unicode{x1D7D9}`
- `pdflatex` is preferred over `xelatex` because of the unexpected look of `\mathcal` and `\mathbb` fonts in the PDF output
- In the Postponed Proofs Appendix `:::{.proof name="Proof of Theorem \@ref(label)}` blocks are used to write the proofs. This produces expected results in the PDF output while in the HTML the proofs begin with *Proof. (Proof of Thoerem)*
- In custom `div` block environments markdown lists (unnumbered and numbered) are not generated in the PDF output is the list is the last element of the environment. If the list is followed by a regular text, then it is generated properly. To omit this issue numbers of the list are put in mathinline style using the `$` symbols
- the `xymatrix` pacakge cannot be used for the HTML output, it is not supported by MathJax. Any diagram using `xymatrix` is therefore not rendered in the HTML otput and the message directing to the PDF version of the notes is displayed.

