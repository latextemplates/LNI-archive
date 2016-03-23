# Changelog
All notable changes to this project will be documented in this file.
This project **does not** adhere to [Semantic Versioning](http://semver.org/).
This file tries to follow the conventions proposed by [keepachangelog.com](http://keepachangelog.com/).
Here, the categories "Changed" for added and changed functionality,
"Fixed" for fixed functionality, and
"Removed" for removed functionality is used.

We refer to [GitHub issues](https://github.com/latextemplates/LNI/issues) by using `#NUM`.

## [Unreleased]

### Changed

#### paper.tex
* Renamed from lniguide.tex
* Move many text to comments
* Fix placing of `\label` (has to be placed outside of `\caption`)
* Fix spacing by using `\` after `.`
* Use \fancypagestyle to avoid multiple page style configurations within the document
* Make use of \iflnienglish to avoid configuration at different places
* Enable German spell check by TeXstudio
* Include helpful packages, see [README.md](README.md) for details

## 0.5 - 2014-12-18
This version and all versions before have been maintained outside of GitHub.
The commits leading to this version have not been reconstructed.

Änderungen des Layouts, generelle Vereinheitlichungen mit der Word Vorlage und inhaltliche Überarbeitung der Beispieldatei im März 2010 (Judith Michael, Alpen-Adria-Universität Klagenfurt)

* Titel linksbündig statt zentriert
* AutorInneninformation neu definiert in der Fußnote
* Abstract ohne Einzug
* Keywords neu hinzugefügt
* Einheitliche Seitennummerierung, neue Kopfzeile
* Diverse Abstände angepasst
* Verwendung der Pakete changepage und fancyhdr
* Anpassung der lstlisting und enumerate Befehle

### Ergänzung Dezember 2014:
Es wurden die Literaturverzeichnis-Stile `lnig.bst` (deutsch) Version 2.0 sowie `lni.bst` (englisch) Version 1.0 an die Vorgaben angepasst und weitere Beispielreferenzen eingefügt.

## 0.4
* Getrennte Bibliographiestile `lni.bst` und `lnig.bst`
* Dokumentenoption `english`

## 0.3
* Option `forInclusion`, Dank an Matthias Rust (mrust@rostock.zgdv.de) für den entsprechenden Hinweis und den Code

## 0.2
* Mehrsprachigkeit durch Einbinden von `english` unterstützt.
* Neue deutsche Trennmuster `ngerman` benutzt.

## 0.1
Ersteller der Dokumentenklasse: Robert Tolksdorf, Berlin (mail@robert-tolksdorf.de)

[Unreleased]: https://github.com/latex-templates/LNI/compare/v0.5...HEAD
