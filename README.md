# LaTeX Template for GI-Edition Lecture Notes in Informatics (LNI)

This repository aims to provide a quick start for modern LaTeXing with [LNI].
This README is best viewed in a markdown viewer or [on GitHub](https://github.com/latextemplates/LNI/blob/master/README.md).

## Three starting options

* **Option A**: Use biblatex and a template with examples. This is the most modern.
  * [biblatex](https://github.com/plk/biblatex#overview) (at least 3.5),
  * [biber](https://github.com/plk/biber#overview) (at least 2.6), and
  * [biblatex-lni](https://github.com/latextemplates/biblatex-lni/blob/master/README.md#biblatex-lni) for the bibliography
* **Option B**: Use bibtex and a template with examples.
  This is recommended in case you cannot update to the latest version of bibtex (instruction are given below).
  Be aware that lni.bst is broken (https://github.com/latextemplates/LNI/issues/1), but still produces a correct bibliography.
* **Option C**: Use bibtex and a template without content.
  This is the default distributed with the LNI style.

All three options produce valid results to be submitted to conferences and workshops requring LNI.
It is proven with the proceedings of [BTW 2017](http://btw2017.informatik.uni-stuttgart.de/).

## Quick start

* Click on `Download ZIP` or [here](https://github.com/latextemplates/LNI/archive/master.zip).
* Extract master.zip in the folder where you want to write your paper.
* Edit the paper
  * Option A: Edit [paper.tex](paper.tex).
  * Option B: Edit [paper-bibtex.tex](paper-bibtex.tex).
  * Option C: Edit [lni-author-template.tex](lni-author-template.tex).
* Make the paper. You can use your usual build system.
  * Option A: `latexmk paper`. See [latexmk] for more information.
    If you want to have continuous preview, execute `latexmk -pvc paper`.
  * Option B: `pdflatex paper-bibtex`, `bibtex paper-bibtex`, ignore the errors,  `pdflatex paper-bibtex`,  `pdflatex paper-bibtex`
  * Option B: `pdflatex lni-author-template`, `bibtex lni-author-template`, ignore the errors,  `pdflatex lni-author-template`,  `pdflatex lni-author-template`.

## Trouble shooting

* `! pdfTeX error (font expansion): auto expansion is only possible with scalable fonts.` -> Install the [cm-super] package using the MiKTeX package manager. Then, run `initexmf --mkmaps` on the command line. (Long description: http://tex.stackexchange.com/a/324972/9075)
* `! LaTeX Error: Command \openbox already defined.`: Insert `\let\openbox\relax` beore `\usepackage{amsthm}`
* `! Undefined control sequence. l.84 \ulp@afterend`. Remove `paper.aux` and recompile.
* `! Package xkeyval Error: `family_i' undefined in families `blx@opt@namepart'.`: You switched from bibtex to biblatex. Remove `paper.bbl` and rempile.
* Option A: biber/biblatex too old -> see installation hints of how to update them at different systems

## Installation hints for Windows

### Installing MiKTeX
* Download the [MiKTeX] basic installer from http://miktex.org/download
* Start it
* First screen: Read the license condiditions and be sure that you really agree.
* Second screen: "Shared Installation": Install MiKTeX for: "Only for: `username`"
* Third screen: "Installation Directory": Install MiKTeX to: `C:\MiKTeX`. This enabled browsing for documentation at `C:\MiKTeX29\doc\latex`
* Fourth screen: "Settings": Preferred paper: A4 and Install missing packages on the fly: `Yes`
* Fifth screen: Press "Start"
* After the installation:
  1. Open `cmd.exe`
  2. Execute `mpm --update-db`
  3. Execute `mpm --update`
  4. Execute `mpm --install=cm-super`
  5. Execute `initexmf --update-fndb`

### Further hints

* The default installation of MiKTeX ships with incompatible biblatex and biber packages. You have to keep your MiKTeX up to date. In case you followed the linked installation steps, you only have to run "Update MiKTeX". If you installed MiKTeX other ways, you have to run "Update MiKTeX (Admin)" and "Update MiKTeX" and check in both tools for updates (see http://tex.stackexchange.com/a/108490/9075)
* Install the [cm-super] package.
* Install other tools using [Chocolatey]: `choco install texstudio sumatrapdf.install latexmk strawberryperl jabref jre8`. This allows you to run `choco upgrade all` to keep the software updated.
* Option A: Ensure that in the "MiKTeX Package Manager" "biber" and "biblatex-lni" are installed

## Installation hints for Ubuntu

Option A: Ubuntu currently [ships biber 2.4](https://bugs.launchpad.net/ubuntu/+source/biber/+bug/1589644), so you have to upgrade your texlive distribution.
The easiest way is to uninstall the ubuntu package and use [install-tl-ubuntu](https://github.com/scottkosty/install-tl-ubuntu).
Then, you can follow the instructions given at http://tex.stackexchange.com/a/55459/9075 to update your tex live distribution.
If you do not want to have an updated installation, but fiddle around with dirty patching your installation, please follow  http://tex.stackexchange.com/questions/84624/how-to-upgrade-biblatex-properly.

## Benefits of Option B in comparison to Option C

 * Automatic setting of "Fig." and "Section"/"Sect." according to the LNI style. Just use `\Cref{sec:xy}` at the beginning of a sentence and `\cref{sec:xy}` in the middle of a sentence. Thanx to [cleveref].
 * Adds modern packages such as [csquotes] and [booktabs].
 * Provides a skeletal [paper.tex](paper.tex) file demonstrating cleveref and booktabs.

## Benefits of Option A in comparison to Option B:

 * No compilation erros when running `bibtex` (because biblatex is used).
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

  [LNI]: https://www.gi.de/service/publikationen/lni/autorenrichtlinien.html
  [official LNI template]: https://www.gi.de/fileadmin/redaktion/Autorenrichtlinien/LNI-LaTeX-Vorlage.zip

  [biblatex]: https://www.ctan.org/pkg/biblatex?lang=de
  [booktabs]: https://www.ctan.org/pkg/booktabs
  [cleveref]: https://ctan.org/pkg/cleveref
  [cm-super]: https://www.ctan.org/pkg/cm-super
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
