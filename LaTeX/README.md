# LaTeX

## Installing LaTeX on Mac

When installing LaTex, two following options are given to users.
  1. Install MacTeX with builtin editor(TexLive) - (2GB)
  2. Install BasicTeX only (100MB) + your personal LaTeX editor

### Option 1 (Full LaTeX installation with LaTeX editor):

Download [MacTex](http://www.tug.org/mactex/).
For more details about MaxTex: [Click Here](https://www.tug.org/mactex/What_Is_Installed.pdf).

Since MaxTex installs an LaTex editor ([TexMaker](http://www.xm1math.net/texmaker/download.html)) already, installing another LaTeX editor is unnecessary.

### Option 2 (BasicTeX + Custom LaTeX editor):

Download [BasicTeX](http://tug.org/mactex/morepackages.html).
For more details about BasicTex: [Click Here](http://pages.uoregon.edu/koch/BasicTeX.pdf).

Pick one of the following LaTeX editors:
LaTex Editor's:
  1. [TexMaker](http://www.xm1math.net/texmaker/)
  2. [TeXstudio](http://texstudio.sourceforge.net/)
  3. [TeXworks](https://github.com/TeXworks/texworks/releases)
  4. [TeXShop](http://pages.uoregon.edu/koch/texshop/)
  5. [LyX](http://www.lyx.org/)
  6. [TeXlipse](http://texlipse.sourceforge.net/)

### MacTeX vs BasicTeX

MacTeX includes additional programs such as an editor and a BibTeX reference manager that help users to work with TeX outside of the command line. BasicTeX does not include these GUI programs. The trade-off that comes with using BasicTeX is that you will have to download and install additional packages and programs as the need arises- and BasicTeX is so basic that the need will arise. So, after installing BasicTeX you will be faced with the tasks of installing additional programs and installing missing packages.

### Bibliography

### betterbib
[betterbib] (https://github.com/nschloe/betterbib)


##### Installation of betterbib

To install simply type
```
pip install -U betterbib
```
If you have installed Anaconda then create a link of BetterBib by the following command
```
$ ln -s /Users/doha420du/anaconda3/bin/betterbib /usr/local/bin/betterbib
```

##### Usage

```
$ betterbib in.bib out.bib
```
the input BibTeX
```
@article {krylov,
  author = {Liesen and Gaul and Nabben},
  title = {Framework Deflation Krylov Augmented}
}
```
is converted into
```
@article{krylov,
  author = {Gaul, André and Gutknecht, Martin H. and Liesen, Jörg and Nabben, Reinhard},
  publisher = {Society for Industrial & Applied Mathematics (SIAM)},
  doi = {10.1137/110820713},
  title = {A Framework for Deflated and Augmented {Krylov} Subspace Methods},
  url = {https://doi.org/10.1137/110820713},
  journal = {SIAM J. Matrix Anal. & Appl.},
  number = {2},
  month = jan,
  volume = {34},
  source = {Crossref},
  year = {2013},
  pages = {495-518}
}
```
(If you prefer long journal names, add the option `--long-journal-name`/`-l`.)

betterbib fetches data from

   * [Crossref](http://www.crossref.org/) (default) or
   * [DBLP](http://dblp.uni-trier.de/) (`--source dblp`).

All betterbib command-line options are explained in `betterbib -h`.

### bibulous
[bibulous] (https://github.com/nzhagen/bibulous)


##### Installation of bibulous
```
$ pip install bibulous
```
Then download the bibulous.py file from github and copy that to the /usr/local/bin/ directory by the following command
```
$ cp ~/Downloads/bibulous.py /usr/local/bin/bibulous.py
```
Then go to TexMaker->Preferences->Commands->Bib(la)tex and peast the following line & save it
```
python /usr/local/bin/bibulous.py %.aux
```


