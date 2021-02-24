#InteractiCrop

Steal figures from other people's slide PDFs, in vector form, easily.

Quick instructions:

* Run as `interacticrop some-slide-deck.pdf 15`.
* A window will pop up.
* You click twice, indicating the area you'd like cropped out, in no particular order.
* You get output like this:
  ```latex
  \includegraphics[
    viewport=10.89cm 3.62cm 24.19cm 11.52cm,clip=true,page=8
    ]{some-slide-deck.pdf}
  ```

* You copy that line to your LaTeX source and life is good.
* Optional: You specify `-o out.pdf` and a cropped output PDF is also written for you.

**OBVIOUSLY:** Don't forget to credit the folks that you steal from! Here's a bonus LaTeX+TikZ macro
to do that:

```latex
\newcommand{\creditto}[1]{
  \begin{tikzpicture}[overlay]
    \node [xshift=1cm,yshift=0.5cm]
      at (current page.south west)
      [font=\scriptsize,fill=gray!30,anchor=south west,opacity=0.5]
      {#1};
  \end{tikzpicture}
}
```

Dependencies:

* [poppler-python](https://launchpad.net/poppler-python)
* [Pillow](https://python-pillow.org/)
* [PyPDF2](https://github.com/knowah/PyPDF2) (optional, if you'd like cropped output)
* [matplotlib](http://matplotlib.org)

Just run these commands, perhaps with `sudo`:

* `aptitude install libpoppler-cpp-dev`
* `pip install python-poppler pillow matplotlib`
* `pip install http://github.com/knowah/PyPDF2/tarball/master` (optional)

Not using Linux, where installing this stuff is easy? I'm sure there's someone
on your friendly neighborhood app store ready to take your money.

## License

InteractiCrop is licensed to you under the terms of the [MIT license](http://en.m.wikipedia.org/wiki/MIT_License).

Copyright (C) 2012 Andreas Klöckner

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

NOTE: Some dependencies are licensed under LGPL.
