# DB Template

This repository will be used as a template for the LaTeX document structure for the report for "Aktuelle DB Technologien".

This template will enable to generate a Book at the end of the studies with common layout.

## Usage

The main LaTeX file is `main.tex`.
To write your report you only have to edit `einstellungen.tex` and the following subfolders:

* `content/` All LaTeX files called `01.tex`, `02.tex` ... `99.tex` will be included in the final document, in numeric order
* `bib/` has a `bibliographie.bib` file for references. Other references can be included with a added `\addbibresource{filename}` in `einstellungen.tex`
* `images/` is for all your images
* `listings/` is for all your source-code listings

### Citations

Citations are in APA 6th Edition style if the commands `\parencite{key}` or  `\textcite{key}` are used.

The citation backend is [biber](https://ctan.org/pkg/biber?lang=en).
Therefore you have to use `biber` instead of `bibtex` / `biblatex` during compilation.

### Images

Images are included using the [graphicx](https://ctan.org/pkg/graphicx) package.

### Listings

Source-code listings are done with [listings](https://ctan.org/pkg/listings)

### Tikz

There is [tikz](https://www.ctan.org/pkg/pgf).

### Custom Commands

The following custom commands are defined:

* `\todo{}` to mark a Todo - all todo's should be removed in the final document
* `\tbd{}` to mark something as "to be determined" - all tbd's should be removed in the final document
* `\chapter{Chapter title}{subtitle}` is a custom commands for chapters - is only used by the template, you should not use/need it use `\section` and `\subsection`

## Custom Packages
If you need to use other TeX-Packages as provided, please message me. I will need the list of packages to combine the articles to a book. Please don't use any packages that alter the visual apperence of the article.


