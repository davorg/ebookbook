# Introduction to Markdown

Markdown is a text-based format that we can use to write quite complicated documents. As such, it meets all of the requirements we discussed in the previous chapter.

Markdown is a less visually noisy version of HTML. That is, anything that you write in Markdown can be easily converted to HTML. And if you want to use HTML features that aren't supported in Markdown, then you can simply include the raw HTML in you Markdown document.

In this chapter we will cover the most commonly used Markdown features. In the next chapter, we will talk about some more advanced corners of Markdown.

## Plain text

For most books, most of the writing time will be spent writing plain text. By which I mean paragraphs like this one. There is nothing complicated going on here at all. I just want to type characters and have them appear in the output - typeset in the standard font used in the book.

As this is our most common requirement, it makes sense for this to be the easiest effect to achieve. If you type text in a Markdown document, it will be rendered as a standard paragraph.

You mark paragraph breaks by adding an empty line between two pieces of text. So in file that I'm currently editing, the start of this section looks like this:

    For most, books, most of the writing time
    [ ... text omitted ...]

    As this is out most common requirement,

Within a paragraph, it doesn't matter where (or, indeed, if) you break lines. Any single line breaks will be ignored by the program that produces our output.

## Emphasis

The next step up in complexity is to add *italic* and **bold** characters to our text. This is achieved by adding asterisks before and after the text that you want to emphasise. One asterisk produces *italic text*, two produce **bold text** and three produce ***bold italic text***. So the input that produced the previous sentence, looked like this:

    One asterisk produces *italic* text,
    two produce **bold text** and
    three produce ***bold italic text***.

If you want to use an asterisk without it producing one of these effects (as I did in the example above), you can switch off its special meaning by putting a backslash (`\`) in front of it.

## Fixed-Width

Most text is displayed as a proportional width font - that is, the characters are all of different widths. The 'i' will be much narrower than the 'm'. Occasionally, you will want to override that and display text in a `fixed-width font`. For example, as a programmer I often write articles that include example code and that looks better in a fixed-width font, as it better mirrors how that code would appear in my code editor.

There are two ways to display text in a fixed-width font. If you want to display a snippet of `fixed-width text` within another paragraph, then you can surround the text with back-tick characters (the back-tick is the '\`' that you find on the key to the left of the '1' on your keyboard). So the input that produced the effect in this paragraph looked like this:

    If you want to display a snippet of
    `fixed-width text` within another paragraph

The other method is used when you want to display a whole paragraph in a fixed-width font. In this method, you include four (or more) spaces at the start of the line. This will have two effects on your output. Firstly, the text will be displayed in a fixed-width font and secondly, no more formatting will be carried out on that section of text. The Markdown processor will simply remove four spaces from every line and display the rest of the line unchanged. I often find myself using this to insert code extracts in my articles like this:

    if ($player->lives_remaining) {
      $game->play_turn($player);
    } else {
      print "Game over\n";
      exit;
    }

All of the examples of Markdown in this chapter have been produced by putting four spaces at the start of the line.

## Headings

You can insert headings in your text using a short paragraph starting with one or more '#' symbols. One '#' is a top-level "level 1" heading, two is a slightly less-important "level 2" heading, and so on, down to level 6. These levels mirror the &lt;h1> to &lt;h6> tags used in HTML.

In this book, I am using level 1 headings for chapter titles, so the start of this chapter looks like this:

    # Introduction to Markdown

And the second-level heading for this section looks like this:

    ## Headings

**TODO:** Underline headings

## Quotations

## Links

## Images
