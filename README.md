# Brunel University Dissertation Template

This is a LaTeX template for undergraduate Computer Science dissertations.

## Depenedencies

* A TeX distrbution ([MacTeX](www.tug.org/mactex/) on Mac OS X and
  [proTeXt](http://www.tug.org/protext/) on Windows are good choices)
* A good text editor
* (Optional) [Pygments](http://pygments.org/), for source code highlighting if
  you need it

## Basic usage

After installing the dependencies, cloning this repository and navigating to
it, you can compile to PDF using the following command:

    pdflatex -shell-escape ./main.tex

Providing the command terminates successfully, you should see a new PDF file in
the folder names `main.pdf`, but it won't display the table of contents
correctly, or anything else that is referenced across the document. This is
because the compiler creates auxilliary files that contain these references
whilst it's passing over the files, but because the table of contents is at the
beginning of the document, these files have not been reached yet. Hence, you'll
often need to run the above command twice in succession.

Whenever altering a bibliographic reference or the `references.bib` file, you
will also need to rerun Biber:

    biber ./main

Therefore, to a correctly formatted document, run the commands as so
(particularly before you submit!):

    pdflatex -shell-escape ./main.tex
    biber ./main
    pdflatex -shell-escape ./main.tex

# Template structure

Data pertaining to you, such as the title of your dissertation and your student
ID number, are in the `config/metadata.tex` file. You will need to edit this to
have them show up in the outputted PDF file. Otherwise, the files you will
typically edit are the files in the `chapters` and `appendices` folders. Add
any figures and images you use to the `figures` and `images` folders
respectively. Vector graphics are supported and their use is encouraged!

If you want to edit any global formatting options, visit the `config` folder.
Word count is calculated automatically but relies on the chapter files keeping
their current names. You can change the names but you will have to edit the
word command regex command in the `config/core_preamble.tex` file for the word
count command to work again.

# Need a primer on LaTeX?

[LaTeX on Wikibooks](http://en.wikibooks.org/wiki/LaTeX) and
[ShareLaTeX](https://www.sharelatex.com/learn/Main_Page) are both fantastic
resources and should answer any questions you have.
