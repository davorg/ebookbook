# Overview of the Process

In this chapter I'll give a brief overflow of the process I use to
create ebooks from Markdown files. The other chapters in the book will
describe the process in more details, but this chapter will contain
all of the information that you need to get you up and running
quickly.

## Tools

There are three piece of software that you need in order to use this
process. All of them are easily available for most common platforms.

*  **Pandoc** is a universal document format converter. If you're
   converting documents between different formats then you will find
   Pandoc to be an incredibly useful tool. In particular, we will use
   Pandoc to convert our Markdown files to an epub file.

    You can get more details about Pandoc from the project web site at
    http://pandoc.org.

*  **Kindlegen** is a program which produces ebooks in Amazon's
   favoured ebook format - mobi. It takes a number of different input
   formats including epub.

    You can get more details about Kindlegen from Amazon's web site at
    http://bit.ly/kindgen.

*  **Calibre** is a program with multiple uses in managing a
   collection of ebooks. Specifically, we will be using a program
   called `ebook_convert` to make PDF copies of our books.

    You can get more details about Calibre from the project web site at
    https://calibre-ebook.com/.

## Inputs

Your input files will be a set of Markdown files. I find it convenient
to have a file for each chapter in the book and I keep all of those
files in a subdirectory called "chapters". I also like to have a file
called "chapters.txt" which contains a list of the chapter files in
the order that they will appear in the book. This makes it easy to
re-order the chapters while I am writing the book.

You will also need three more files which are used to create the
ebook.

* **title.txt** is a very simple text file which is used to create the
title page of your book.

* **metadata.xml** is a file which contains various items of metadata
  for your book (title, author, publication name - things like
  that). While this data is usually stored in a XML format, Pandoc
  will also accept the information as YAML.

* **cover.png** is an image which will be used as the front cover of
  your book. 

## Outputs

We will create our ebook in three different formats. These formats
have been chosen to cover a wide range of reading environments.

* **epub** is an industry standard format for ebooks. It is used by a
number of ebook platforms.

* **mobi** is the ebook format used by Amazon.

* **pdf** isn't an ebook format, but it is a convenient format for sharing
draft copies of your book with reviewers and other readers.

## The Process

The process can be summarised in four steps.

1. You create Markdown files containing the contents of your book.

2. You use Pandoc to turn those files into an epub.

3. You use Kindlegen to turn your epub into a mobi.

4. You use Calibre (actually ebook_convert) to turn your epub into a
pdf.

![The Ebook Creation Process](converters.png "The Ebook Creation Process")

## The Commands

Here are the commands you will use to create your book.

    $ pandoc -o yourbook.epub [list of files] \
        --ebook-cover-image=cover.png

This command uses Pandoc to take a set of Markdown files and creates
an epub. The list of files that you use can be as long as you like. If
you are following my earlier recommendations, then you will have a
`title.txt`, a `metadata.xml` and a `chapters.txt` which contains a
list of the actual chapters. Your command will therefore look like
this:

    $ pandoc -o yourbook.epub title.txt \
        metadata.xml `cat chapters.txt` \
        --ebook-cover-image=cover.png

After running this command, you will end up with a file called
`yourbook.epub`.

You can create a mobi using Kindlegen.

    $ kindlegen yourbook.epub

This will give you a file called `yourbook.mobi` which you could
upload to Amazon to sell.

You can create a PDF of your book using Calibre.

    $ ebook-convert yourbook.epub yourbook.pdf
