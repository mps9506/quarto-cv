# Quarto-cv Format

This is a work in progress. It should work, but install and use at your own risk! :)

A Quarto template for generating a CV in pdf format. The template is based entirely
on [Steven Miller's R Markdown templates](https://github.com/svmiller/stevetemplates).

## Installing

```bash
quarto install template mps9506/quarto-cv
```

This will install the template for use with existing Quarto projects or documents.

*or* To install the extension and create an example qmd file and project (easiest way to start):

```bash
quarto use template mps9506/quarto-cv
```


## Usage

To use with with quarto in the cli:

```bash
quarto render your_cv.qmd --to quarto-cv.pdf
```

or specify in the document yaml:

```yaml
format:
  quarto-cv-pdf: default
```

## Format Options

### Contact Block

The contact block at the top of the CV is rendered using the following metadata:

```yaml
author: First Name Last Name
address: Street, City, State, Country
# The following are optional
phone: your contact number
email: you@email.com
github: github account
orcid: orcid identfier
osf: five character osf id
twitter: twitter handle
web: web address (no `https://`)
```

### Bibliographies

The template includes a lua filter to easily incorporate multiple bibliographies using `.bib` files if you choose to manage publications this way. This is a good option for separating out book/chapter, journal articles, white papers, datasets, and software.

In the document yaml header simply point to your `.bib` files and provide a unique name:

```yaml
bibliography_peer: peer.bib
bibliography_reports: reports.bib
bibliography_books: books.bib
bibliography_software: software.bib
```

Then create different bibliographies for each one:

```
# Journal Articles

::: {#refs_peer}
:::

# Software

::: {#refs_software}
:::
```

You can specify the bibliographic style using the csl variable. By default it points to an APA style sorted by descending date. Other styles can be found [here](https://www.zotero.org/styles).


## Example

Here is the source code for a minimal sample document: [template.qmd](template.qmd).

# License

The template is based entirely
on [Steven Miller's R Markdown templates](https://github.com/svmiller/stevetemplates)
licensed under GPL-2. A copy of the pandoc 
[multiple-bibliographies](https://github.com/pandoc/lua-filters) lua filter 
licensed under MIT is included as part of this template.
