# Simplified LNI Template

This repository aims to provide a quick start for modern LaTeXing with [LNI].
In addition to the [official LNI template], it offers following features:

 * enable the most recent hyphenation patterns for German text
 * clean copy and paste of ligatures (e.g., "workflow" stays "workflow" after copying from the PDF).
 * automatic setting of "Fig." and "Section"/"Sect." according to the LNCS style. Just use `\Cref{sec:xy}` at the beginning of a sentence and `\cref{sec:xy}` in the middle of a sentence. Thanx to [cleveref](https://www.ctan.org/pkg/cleveref).
 * [microtypographic extensions](https://www.ctan.org/pkg/microtype) for a better look of the paper.
 * support of `\powerset`.
 * support of hyperlinked references without extra color thanx to [hyperref](https://www.ctan.org/pkg/hyperref).
 * better breaking of URLs.
 * sharper font.
 * removed `sty` files: These are provided by all modern LaTeX distributions.

The official template is available at https://www.gi.de/fileadmin/redaktion/Autorenrichtlinien/LNI-LaTeX-Vorlage.zip.

## Quick start

 * Click on `Download ZIP` or [here](https://github.com/latextemplates/LNI/archive/template.zip).
 * Extract template.zip in the folder where you want to write your paper.
 * Edit [paper.tex](paper.tex).
 * `latexmk paper`.

## Benefits in comparison to GI e.V.'s version

* Provides a skeletal [paper.tex](paper.tex) file
* Adds modern packages such as [microtype], [cleveref], [csquotes], [hyperref], [hypcap], [booktabs]
* Support of copy and paste from the generated PDF: Glyphs are encoded using unicode characters.
* Support for `\powerset` command
* Generated PDF allows for copy and paste of text without getting words with ligatures such as "workflow" destroyed

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
1. `cd LNCS`
1. `git remote rename origin upstream`
1. `git checkout -b master`

After that you can use and push the `master` branch as usual.
Notes on syncing with the upstream repository [are available from GitHub](https://help.github.com/articles/syncing-a-fork/).
Note that we decided to call the upstream branch `template` to have a clear distinction between the real content (maintained in your `master` branch) and the template (maintained in the `template` branch).

  [LNI]: https://www.gi.de/service/publikationen/lni/autorenrichtlinien.html
  [official LNI template]: https://www.gi.de/fileadmin/redaktion/Autorenrichtlinien/LNI-LaTeX-Vorlage.zip

  [booktabs]: https://www.ctan.org/pkg/booktabs
  [cleveref]: https://ctan.org/pkg/cleveref
  [csquotes]: https://www.ctan.org/pkg/csquotes
  [hypcap]: https://www.ctan.org/pkg/hypcap
  [hyperref]: https://ctan.org/pkg/hyperref
  [microtype]: https://ctan.org/pkg/microtype

  [JabRef]: http://www.jabref.org
  [LanguageTool]: https://languagetool.org/
  [TeXstudio]: http://texstudio.sourceforge.net/
