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

## Benefits in comparison to GI e.V.'s version
In addition to the [official LNI template], it offers following features:

 * Enables most recent hyphenation patterns for German text
 * Clean copy and paste of ligatures (e.g., "workflow" stays "workflow" after copying from the PDF).
 * Automatic setting of "Fig." and "Section"/"Sect." according to the LNI style. Just use `\Cref{sec:xy}` at the beginning of a sentence and `\cref{sec:xy}` in the middle of a sentence. Thanx to [cleveref].
 * [microtypographic extensions](https://www.ctan.org/pkg/microtype) for a better look of the paper.
 * Support of `\powerset`.
 * Support of hyperlinked references without extra color thanx to [hyperref].
 * Better breaking of URLs.
 * Removed `sty` files: These are provided by all modern LaTeX distributions.
 * Adds modern packages such as [csquotes], [hypcap], [booktabs].
 * Provides a skeletal [paper.tex](paper.tex) file.

## Tool hints
Grammar and spell checking is available at [TeXstudio].
Please download [LanguageTool] and [configure Texstudio to use it](http://wiki.languagetool.org/checking-la-tex-with-languagetool#toc4).
Note that it is enough to point to `languagetool.jar`.
Use [JabRef] to manage your bibliography.

If TeXstudio doesn't fit your needs, check [the list of all available LaTeX Editors](http://tex.stackexchange.com/questions/339/latex-editors-ides).

## Using the template with your git repository

### Initialization
This howto assumes that you don't have a git repository for your paper yet.
If you have, just add https://github.com/latextemplates/LNI.git as upstream and merge the branch `template` into your `master` branch.

1. Open command line
1. `git clone https://github.com/latextemplates/LNI.git`
1. `cd LNI`
1. `git remote rename origin upstream`
1. `git checkout -b master`

After that you can use and push the `master` branch as usual.
Notes on syncing with the upstream repository [are available from GitHub](https://help.github.com/articles/syncing-a-fork/).
Note that we decided to call the upstream branch `template` to have a clear distinction between the real content (maintained in your `master` branch) and the template (maintained in the `template` branch).

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
