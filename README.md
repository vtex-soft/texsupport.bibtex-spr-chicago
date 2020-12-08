# texsupport.bibtex-spr-chicago

## About

This package provides Chicago BibTeX reference style 
(`spr-chicago.bst`) for Springer journals. There are also included few example files 
(`.tex`, `.bib`, `.pdf`) showing how to use BibTeX style file and how it would look like.

## Contents

The following files are given in the repository (or directly in `.zip` archive):

-   `chicago-bibstyle.sty` - LaTeX macro commands for Chicago bibliography; 
-   `spr-chicago.bst` - BibTeX style for author-year (see [below](#comments)) citations; 
-   `template.tex`  - template file; 
-   `template.pdf` - journal sample article with APS bibliography;
-   `example.bib` - BibTeX database file.

## Setup

-   Clone the repository or download the `.zip` archive;
-   Install `spr-chicago.bst` and `chicago-bibstyle.sty` in your LaTeX system or 
    place them in the same directory where your `.tex` file is;
-   use the file `template.tex` to start your article as a template;
-   **Important**: `template.tex` uses `svjour3.cls` LaTeX style file which you should download from 
    [Springer site](http://static.springer.com/sgw/documents/468198/application/zip/LaTeX_DL_468198.zip).

## Comments

Default citation style is author-year (i.e. `nameyear` option).
But there is also a possibility to choose other citation style.
You can select it by writing an entry `@settings` to the `.bib` file. 
That entry should have a field - `options`, with a value of citation style.

Available options:

*   `alpha`    -- alphanumerical citation style (e.g., `[Ru01]`)
*   `number`   -- number citation style (e.g., `[5]`)
*   `nameyear` -- author-year citation style (e.g., `(Rudin, 2001)` or `Rudin (2001)`)
*   `unsort`   -- turn off sorting (reference list is sorted by default) 
*   `nodoi`    -- do not print DOI (DOI is printed by default)

**Example 1**: Choosing a number citation style.

```
@settings{label,
    options = "number"
}
```

**Example 2**: Choosing an alphanumerical citation style and not sorting references.

```
@settings{label,
    options = "alpha,unsort"
}
```

`label` can be any word, but all references labels have to be unique!

**Important**: you need to write `\nocite{label}` in your `.tex` file, 
otherwise  `@settings` will not become effective (unless you use
`\nocite{*}`, which will make a list of all the references appearing in `.bib` file(s)).

**Example 3**: Turning on `@settings` via `.tex` file.

```
bibfile.bib
  @settings{some_label, ....}

texfile.tex
  ....
  \nocite{some_label}
  \bibliographystyle{spr-chicago}
  \bibliography{bibfile}
```

## Bug reports

Please submit bug reports and/or feature requests
at [GitHub page](https://github.com/vtex-soft/texsupport.svjour-aps-nameyear/issues) or 
[latex-support@vtex.lt](mailto:latex-support@vtex.lt).

