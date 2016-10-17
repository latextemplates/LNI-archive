# Simplified LNI Template

This repository aims to provide a quick start for modern LaTeXing with [LNI].

This version requires:
  * [biblatex](https://github.com/plk/biblatex#overview) and
  * [biblatex-lni](https://github.com/latextemplates/biblatex-lni/blob/master/README.md#biblatex-lni) for the bibliography

## Quick start

 * Click on `Download ZIP` or [here](https://github.com/latextemplates/LNI/archive/master.zip).
 * Extract master.zip in the folder where you want to write your paper.
 * Edit [paper.tex](paper.tex).
 * `latexmk paper`. See [latexmk] for more information.

If you want to have continuous preview, execute `latexmk -pvc paper`.


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
 * Support of [biblatex]


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

Just execute `git pull -Xtheirs template master`


## Links

 * Other templates: http://latextemplates.github.io/
 * German: Hinweise zu Ausarbeitungen: http://wiki.flupp.de/studium/ausarbeitungen

  [LNI]: https://www.gi.de/service/publikationen/lni/autorenrichtlinien.html
  [official LNI template]: https://www.gi.de/fileadmin/redaktion/Autorenrichtlinien/LNI-LaTeX-Vorlage.zip

  [biblatex]: https://www.ctan.org/pkg/biblatex?lang=de
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
