# Simplified LNI Template

This repository aims to provide a quick start for modern LaTeXing with [LNI].

This version does not require biblatex, but still suffers from a broken `lni.bst`.
This is a known issue (https://github.com/latextemplates/LNI/issues/1).
The current fix is to switch to biber and to use [biblatex-lni].
In case, your LaTeX installation is uptodate, it is recommended to switch to https://github.com/latextemplates/LNI.

## Quick start

 * Click on `Download ZIP` or [here](https://github.com/latextemplates/LNI/archive/lni-bibtex.zip).
 * Extract lni-bibtex.zip in the folder where you want to write your paper.
 * Edit [paper.tex](paper.tex).
 * Run `pdflatex -synctex=1 paper`.
 * Run `bibtex paper`.
 * Run `pdflatex -synctex=1 paper`.

[latexmk] currently does not work, because of https://github.com/latextemplates/LNI/issues/1.

## Trouble shooting

* `! pdfTeX error (font expansion): auto expansion is only possible with scalable fonts.` -> Install the `cm-super` package using the MiKTeX package manager. Then, run `initexmf --mkmaps` on the command line. (Long description: http://tex.stackexchange.com/a/324972/9075)
* `! LaTeX Error: Command \openbox already defined.`: Insert `\let\openbox\relax` beore `\usepackage{amsthm}`
* `! Undefined control sequence. l.84 \ulp@afterend`. Remove `paper.aux` and recompile.
* `! Package xkeyval Error: `family_i' undefined in families `blx@opt@namepart'.`: You switched from bibtex to biblatex. Remove `paper.bbl` and rempile.

## Benefits in comparison to GI e.V.'s version

The [official LNI template] is updated at <https://github.com/sieversMartin/LNI/>, which is approved by GI and offers following benefits:

 * Enables most recent hyphenation patterns for German text
 * Clean copy and paste of ligatures (e.g., "workflow" stays "workflow" after copying from the PDF).
 * [microtypographic extensions](https://www.ctan.org/pkg/microtype) for a better look of the paper.
 * Support of `\powerset`.
 * Support of hyperlinked references without extra color thanx to [hyperref].
 * Better breaking of URLs.
 * Removed `sty` files: These are provided by all modern LaTeX distributions.
 * Adds modern packages such as [hypcap].
 * Provides a skeletal [lni-author-template.tex](https://github.com/sieversMartin/LNI/blob/master/lni-author-template.tex) file demonstrating the template.

In addition, this template offers following benefits:

 * Automatic setting of "Fig." and "Section"/"Sect." according to the LNI style. Just use `\Cref{sec:xy}` at the beginning of a sentence and `\cref{sec:xy}` in the middle of a sentence. Thanx to [cleveref].
 * Adds modern packages such as [csquotes] and [booktabs].
 * Provides a skeletal [paper.tex](paper.tex) file demonstrating cleveref and booktabs.

## Tool hints

Grammar and spell checking is available at [TeXstudio].
Please download [LanguageTool] and [configure Texstudio to use it](http://wiki.languagetool.org/checking-la-tex-with-languagetool#toc4).
Note that it is enough to point to `languagetool.jar`.
Use [JabRef] to manage your bibliography.

If TeXstudio doesn't fit your needs, check [the list of all available LaTeX Editors](http://tex.stackexchange.com/questions/339/latex-editors-ides).

## Using the template with your git repository

### Initialization

1. Initialize a git repository for your paper
2. `git remote add template https://github.com/latextemplates/LNI.git`

## Updating

Just execute `git pull -Xtheirs template lni-bibtex`

## Space saving techniques

**These are not officially approved!**

```
\newlength{\bibitemsep}\setlength{\bibitemsep}{.2\baselineskip plus .05\baselineskip minus .05\baselineskip}
\newlength{\bibparskip}\setlength{\bibparskip}{0pt}
\let\oldthebibliography\thebibliography
\renewcommand\thebibliography[1]{%
  \oldthebibliography{#1}
  \setlength{\parskip}{\bibitemsep}%
  \setlength{\itemsep}{\bibparskip}%
}
```


## Links

 * Other templates: http://latextemplates.github.io/
 * German: Hinweise zu Ausarbeitungen: http://wiki.flupp.de/studium/ausarbeitungen

  [LNI]: https://www.gi.de/service/publikationen/lni/autorenrichtlinien.html
  [official LNI template]: https://www.gi.de/fileadmin/redaktion/Autorenrichtlinien/LNI-LaTeX-Vorlage.zip

  [biblatex-lni]: https://github.com/latextemplates/biblatex-lni
  [booktabs]: https://www.ctan.org/pkg/booktabs
  [cleveref]: https://ctan.org/pkg/cleveref
  [csquotes]: https://www.ctan.org/pkg/csquotes
  [hypcap]: https://www.ctan.org/pkg/hypcap
  [hyperref]: https://ctan.org/pkg/hyperref
  [microtype]: https://ctan.org/pkg/microtype
  
  [latexmk]: https://www.ctan.org/pkg/latexmk/

  [JabRef]: http://www.jabref.org
  [LanguageTool]: https://languagetool.org/
  [TeXstudio]: http://texstudio.sourceforge.net/
