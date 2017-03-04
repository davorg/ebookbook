# Text Formats



## Why Use Text Formats?

There are a large number of books about creating ebooks. Most of them
seem to be ebooks that are available in Amazon's Kindle Store. And, as
far as I can tell, all of them assume that you are going to write your
book in using a word processor and that when creating your ebook you
will be starting from a .doc file.

As a self-confessed geek, this makes me very uncomfortable. A word
processor stores your writing in a binary file. And a binary file is
going to be largely inpenetrable to the tools that geeks like to
use. It's true that many word processor files are zipped-up bundles of
XML files. And XML is text. But that zipping-up turns the text into a
nasty binary format.

Most geeks will be working on a Unix-based computer. These days, that
is likely to be something (like Linux or OSX) which isn't actually
Unix, but still includes all of the tools that have been an integral
part of Unix for over forty years.

Ask a geek for the number of words in a file and she'll reach for
`wc`. If she wants to find the files which contain a particular
phrase, she'll use `grep` (or, more recently, `ack`). When she wants
to know the differences between two versions of a file, `diff` is
there to help. All of those tools become next to useless when given
binary files to work with. Binary files probably don't have the white
space that `wc` uses. It's likely that `grep` will find the text that
you're interested in - but in a file with no recognisable line
endings, it will struggle to show you any useful information. When
given two binary files, `diff` will happily tell you whether they are
the same or different - but it won't be able to show you what the
differences are as it would with a text file.

And then there's revision control. Geeks like to keep track of their
work. Which means that we love revision control systems like
Git. Revision control systems give us "checkpoints" that we can go
back to if we make changes to code that end up being
unsuccessful. When problems emerge in code, revision control systems
give us the ability to compare older, working, code with the newer,
broken, version and work out how it was broken and (more importantly)
how we can fix it. It also means that we can roll back the code to an
earlier, known good, state while we fix the problems that have been
inadvertantly introduced.

Given the way that geeks live their lives inside revision control
systems while writing code, it shouldn't be a surprise that they would
like to do the same when they are writing books. It's possible to
store binary word processor files in a revision control system, but
it's not going to be as useful as storing text files. You'll be able
to roll back to a known-good version, but the system won't be able to
show you what changed between versions in any useful format.

I realise that most word processors have features that will do most of
this. They will track changes and show you what changed, when it
changed and who made the change. But it's all tied into the word
processor itself. I can't, for example, set up a nightly job which
emails all of the contributors summarising what has changed during the
day. With text files in a revision control system that kind of thing
is easy.

Given all of these advantages, it's no surprise that most geeks will
far prefer storing their work in text files. The next question
becomes - which text format to choose.

## Which Text Format?

Having established that text formats meet our needs better than binary
formats do, we now have to work out which text format we are going to
use.

Plain text doesn't, in itself, have the ability to denote things like
chapter heading and emphasised text. And, by definition, it doesn't
support the use of images. These are all things that we are likely to
want in our books, so we actually want to use some kind of mark-up
language that can be represented in plain text.

Here is a list of some common mark-up languages, along with some
thoughts about their suitability for this task.

### POD

I'm mainly a Perl programmer and POD (Plain Old Documentation) is what
Perl programmers use to document their code. It's a simple, but
effective, mark-up language and I have successfully used it to write a
book in the past.

However, it has some disadvantages. In order to write a book in it, I
had to use an enhanced version of it which had been developed by the
publisher as POD doesn't support all of the features that you need to
write a book. It's also rather verbose in some areas (lists are a
particular annoyance) and it's not used at all outside of the Perl
community, so it wouldn't encourage collaboration.

### HTML

One of POD's disadvantages is that not many people know it. HTML, of
course, doesn't have that problem at all. HTML has become one of the
most ubiquitous mark-up languages on the planet. Sometimes it seems
that everyone knows HTML.

And HTML is good format to choose. Its only downside for me is that it
can be rather verbose. All of those angle brackets need to be typed.

It's good, but I think there are better options available.

### Docbook

I considered Docbook for about five seconds.

It has the same negatives as HTML (it's very verbose), but none of the
positives (almost no-one knows it). It has some useful tools
available, but ultimately you end up storing a text format that people
find quite difficult to read.

### Markdown

Markdown is effectively a distillation of HTML down to its simplest
form. It does away with the need for most of the angle brackets and
replaces them with simple mark-up that anyone can pick up in a few
minutes.

And if there's something particularly clever that you can do in HTML
but not in Markdown then you can just fall back to using the HTML
mark-up in your document.

Many people are already using Markdown every day as it is often used
as a light-weight HTML alternative when writing text on a web site
(StackOverflow and Reddit both use it, for example).

So I really think we have a winner. Of course, if you don't agree with
my choice you can still use the processes described in this book -
just as long as you choose one of the other (many) input formats
supported by Pandoc.
