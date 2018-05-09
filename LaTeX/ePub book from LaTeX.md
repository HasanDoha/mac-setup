# ePub book from LaTeX

## Contents

### 1  What is ePub?
### 2  Mathematics
### 3  Translation to XHTML
### 4  Constructing the ePub from XHTML


TeX and LaTeX are well suited to producing electronically publishable documents. What is likely to be a continuing need is to translate LaTeX documents into standard electronic book format, notably ePub, which is the format adopted by most electronic reader publishers except the biggest one (you know who).

### 1  What is ePub?

You don't really want to know what the ePub standard is. And you are not going to find out much here. In short, though, an ePub book is a XHTML1 version of the book packaged together with its figures and other resources into a zip file. It has a couple of files of metadata. One describes the contents of the zip file and the other is the table of contents of the book, giving navigation links to chapters and sections.
Converting a LaTeX book to ePub is basically a two step process:
(1) translate it to XHTML;
(2) package up the XHTML into an ePub file.
If you are to be satisfied with your ePub version, you need to realize the difference between logical mark-up and page layout. I suggest you consult my brief discussion Should I translate to HTML or not at http://hutchinson.belmont.ma.us/tth/shouldi.html. The ePub format is XHTML; so you don't have a choice.

### 2  Mathematics

Mathematics is problematic in ePub. The natural solution is to use MathML. Unfortunately that is not yet part of the official ePub format. Stay tuned.

### 3  Translation to XHTML
There are several quite capable LaTeX to HTML translators. I wrote TtH so I recommend it, and I'm interested to hear about ways TtH output can be optimized for ePub. Because TtH uses HTML to represent equations, many simple equations will translate correctly. But complex equations probably won't, and that can be fixed only when MathML is adopted by ePub. You can get TtH free from http://hutchinson.belmont.ma.us/tth/
Once you have TtH installed, translation is as simple as issuing the command:
tth -w2 -e2 mybook.tex
This will create a file mybook.html in the directory you are working in. The switch -w2 tells TtH to use XHTML output, and -e2 tells it to include figures inline in the text. That's it. You are done with step 1.
Generally TtH will emit a variety of informational and warning messages for unusual LaTeX constructs. As long as TtH ends by saying "Number of lines processed approximately ..." it has probably translated the whole of your document and you should proceed. If not, or if there's something unsatisfactory about the translation, you need to dig into your TeX code and read the TtH manual.

### 4  Constructing the ePub from XHTML

There are a couple of open source applications that can construct the ePub zip file for you, and construct the required metadata. One is called Calibre, but the one I like best is Sigil. It can be a little tricky to get going on linux operating systems that are older than a year or so, because it depends upon recent Qt libraries, but there's a way to get a newer library and make it work. Windows you ask? Sorry, I don't do windows (but someone else probably can give advice).
To create the ePub file, just open Sigil, and do File->Open and choose your mybook.html. It will suck in your XHTML file, and also all the figures that are referred to in it, and construct the complete ePub format file. You can then save it and you would be done.

Actually you are not quite done because you have to generate a table of contents and fix some metadata before this is really a valid ePub file. (And by the way publishers and booksellers are very picky about ePub books having to validate against the standard, before they accept them.) There are many more details about getting HTML into Sigil at http://code.google.com/p/sigil/wiki/BasicTutorial, but here's a brief summary of essentials.

Table of Contents.   Your LaTeX file contains an automatic table of contents, right? If so and you made it in the standard LaTeX way, TtH will have translated it and put it in your XHTML file. But still the ePub navigation TOC must be created. So first, in Sigil click on Generate TOC from headings. It will give you the chance to include or not various headings. Go ahead.
ePub Validation   Now do Tools->Validate ePub. Unfortunately, you'll get two errors: "The < language > element is missing" and "The < title > element is missing". You can enter the title and language metadata can be by using Tools->Meta data... This pops up an entry form where you can type the title and author in. Then you should be fine.
Those errors refer to the file content.opf which Sigil generated. If you prefer you can edit it directly by hand. Double click on that file in the Sigil column that shows the content of your archive. It will protest that this is for experts only. Be brave and say ok. You'll then see a mess of markup, and near the top will be something like
<dc:identifier id="BookId" 
opf:scheme="UUID">urn:uuid:bb3f2792-ead3-42bb-80fd-727934819cec
</dc:identifier>

You need to enter either immediately before or immediately afterward two new markup elements as follows:
<dc:title>My Book's Title</dc:title>
<dc:language>en</dc:language>

Don't do anything else in the content.opf file unless you really are an expert.
Then validate again; you should see the report: "No problems found". You can save the mybook.epub file and you are done.
It is possible that on validation you will discover XHTML errors that arise from unusual LaTeX. If so, then you might have to dig back into your LaTeX source and find out why. Actually Sigil usually does quite a decent job of cleaning up XHTML code so that it satisfies the tight 1.1 standard.
There are other requirements (beyond the ePub standard) for title page and other stuff that publishers usually demand. They require you to do further editing. But that's between you and Sigil (or Calibre).
