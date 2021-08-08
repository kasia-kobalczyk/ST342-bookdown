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
