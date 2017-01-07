# Simplified LNI Template

This repository aims to provide a quick start for modern LaTeXing with [LNI].

This version requires:
  * [biblatex](https://github.com/plk/biblatex#overview) (at least 3.5),
  * [biber](https://github.com/plk/biber#overview) (at least 2.6), and
  * [biblatex-lni](https://github.com/latextemplates/biblatex-lni/blob/master/README.md#biblatex-lni) for the bibliography

In case you cannot update to the latest version of bibtex (instruction are given below), you find a version using bibtex at https://github.com/latextemplates/LNI/tree/lni-bibtex. Be aware that lni.bst is broken (https://github.com/latextemplates/LNI/issues/1), but still produces a correct bibliography.

## Quick start

 * Click on `Download ZIP` or [here](https://github.com/latextemplates/LNI/archive/master.zip).
 * Extract master.zip in the folder where you want to write your paper.
 * Edit [paper.tex](paper.tex).
 * `latexmk paper`. See [latexmk] for more information.

If you want to have continuous preview, execute `latexmk -pvc paper`.

## Trouble shooting

* biber/biblatex too old -> see installation hints of how to update them at different systems
* `! pdfTeX error (font expansion): auto expansion is only possible with scalable fonts.` -> Install the `cm-super` package using the MiKTeX package manager. Then, run `initexmf --mkmaps` on the command line. (Long description: http://tex.stackexchange.com/a/324972/9075)

## Installation hints for Windows

* Install [MiKTeX] by following the steps provided at https://github.com/latextemplates/uni-stuttgart-computer-science-template#recommended-setup-of-miktex
* The default installation of MiKTeX ships with incompatible biblatex and biber packages. You have to keep your MiKTeX up to date. In case you followed the linked installation steps, you only have to run "Update MiKTeX". If you installed MiKTeX other ways, you have to run "Update MiKTeX (Admin)" and "Update MiKTeX" and check in both tools for updates (see http://tex.stackexchange.com/a/108490/9075)
* Install other tools using [Chocolatey]: `choco install texstudio sumatrapdf.install latexmk strawberryperl jabref jre8`. This allows you to run `choco upgrade all` to keep the software updated.
* Ensure that in the "MiKTeX Package Manager" "biber" and "biblatex-lni" are installed

## Installation hints for Ubuntu

Ubuntu currently [ships biber 2.4](https://bugs.launchpad.net/ubuntu/+source/biber/+bug/1589644), so you have to upgrade your texlive distribution.
The easiest way is to uninstall the ubuntu package and use [install-tl-ubuntu](https://github.com/scottkosty/install-tl-ubuntu).
Then, you can follow the instructions given at http://tex.stackexchange.com/a/55459/9075 to update your tex live distribution.
If you do not want to have an updated installation, but fiddle around with dirty patching your installation, please follow  http://tex.stackexchange.com/questions/84624/how-to-upgrade-biblatex-properly.

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
 * Support of [biblatex].

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

  [Chocolatey]: https://chocolatey.org/
  [JabRef]: https://www.jabref.org
  [LanguageTool]: https://languagetool.org/
  [MiKTeX]: http://miktex.org/
  [TeXstudio]: http://texstudio.sourceforge.net/
