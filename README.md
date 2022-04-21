# Pandoc to Markdown Bridge

This repository contains a proof of concept for an upcoming package for TeX
that will enable the use of [Pandoc][1] together with the [Markdown package][2]
for TeX. For more information, see [the article in the CSTUG Bulletin 31:1–4][3]
(in Slovak, [here is a machine translation to English][7]).

 [1]: https://github.com/jgm/pandoc
 [2]: https://github.com/witiko/markdown
 [3]: https://www.cstug.cz/bulletin/pdf/2021-1-4.pdf#page=85
 [7]: https://translate.google.com/translate?sl=auto&tl=en&u=https://www.fi.muni.cz/~xnovot32/bulletin/2021-1-4/06-rehak-pandoc/&client=webapp

To typeset the example documents, execute the following command on a system with
an up-to-date installation of TeX Live and Pandoc:

    $ make examples

Alternatively, you can use [the witiko/markdown Docker image][4], which includes
both TeX Live and Pandoc:

    $ docker run --rm -it -v "$PWD":/workdir -w /workdir witiko/markdown \
    > latexmk -shell-escape -pdf example-man-pandoc.tex

 [4]: https://hub.docker.com/r/witiko/markdown/tags

Here are the expected results:

- [`example-man-pandoc.pandoc.tex`][5] – the generic TeX output of Pandoc's conversion
- [`example-man-pandoc.pdf`][6] – the result of typesetting `example-man-pandoc.pandoc.tex` using the Markdown package for TeX

 [5]: https://github.com/drehak/pandoc-to-markdown/releases/download/latest/example-man-pandoc.pandoc.tex
 [6]: https://github.com/drehak/pandoc-to-markdown/releases/download/latest/example-man-pandoc.pdf

The development of this package has been funded by the research project
[MUNI/33/1784/2020 (Extension of the input formats of the Markdown tool)][7]
funded by the Faculty of Informatics, Masaryk University.

 [7]: https://www.fi.muni.cz/app/projects?project=58488
