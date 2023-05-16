title: dirt authoring guide

## Concept

A website conceptually consists of content, structure, and navigation,
and a SSG simply morphs one representation of these into HTML for web
browsers. Websites are built from "source representation" (directories
of markdown and other content) that corresponds to our mental
conception, and a library that does the transformation.

To create a website with dirt, simply collect content files in a directory.

* Write text in markup files named *something*.**md**
* Write links to other files changing the suffix to *something*.**html**
* Create subdirectories containing groups of files to structure large sites

## Markdown

Most of the website will consist of text and images created as markdown
text files, with names ending `.md`. For example, you edit words and
formatting in the file `sample.md` and that appears in the website as
the page `sample.html`.

Files named "index" are special: they are shown as the content of
directories. That is, the top level "index.md" file is the contents of the
website home page. In the same way, "index" files in subdirectories
become the contents of those directories.

Markdown files may have metadata lines at the top as shown below, with a
named parameter followed by a colon, then the value of that parameter.
These lines do not directly appear in the website content.

    title: This is a sample Title
    date: 2023/07/24

In this example, the page is given a five word title (shown in the top
of its browser window or tab) and dated July 24, 2023 (for purposes of
ordering posts such as a blog). If no date is specified, the date of the
file creation is used.

The following is a mini-introduction to writing markdown; learn more at
[Markdown Cheat Sheet](https://daringfireball.net/projects/markdown/syntax)
or other resources. 
With dirt you can edit and with every save get a preview in the browser
of what you have created so it's easy to learn by trial and error.

Use section headings as shown below to organize your document.
One `#` makes a top level (H1) heading; use two or more for nested subsections.
For referencing HTML ids will be assigned (hover over section to see its id).

    # Section Heading

Just write words in plain text, or like \*this\* for *italics*;
\*\*this\*\* for **bold**; \-\-this\-\- for --strikeout-- (a dirt feature);
\`this\` for `code` or any monospaced font text. 
Break lines anywhere in the sentence, and separate paragraphs by blank lines.
A line of just three or more hyphens is a horizontal rule.

Hyperlinks are written with brackets around the text portion, followed
by the link (URL) in parentheses; links within the same website can omit
the site name (e.g. `"/about"`).

This is an example of a [hyperlink to example.com](https://example.com):

    [hyperlink to example.com](https://example.com).

Images can be included by the same syntax preceded by exclamation point,
with the bracketed text portion used as "alt text" (only displayed
when for some reason the image itself cannot be). 

    ![Sample image alt text](/images/sample.png)

Here are a few more handy tricks for markdown:

-   Block quotations are written with "> " at the beginning of each
    line (lines of just ">" separate paragraphs within a long quotation).

-   Bullet lists are written with "- " at the beginning of each line.
    Long bullet entries can be broken into separate indented lines.

-   Numbered lists are lines beginning "1. First" and "2. Second"
    and so forth, or just write ones at the beginning of all lines and
    markdown will number them for you.

-   If markdown is getting in the way, add a backslash (\\) in front of
    any character to "hide" it.

Take a look at the markdown source for this page as a quick cheatsheet.

Markdown has many more features, but dirt is all about making simple
websites so generally it's best to use these text enhancement features
minimally --- it's easier and the results look clean.
(Read on for more complete details if you want a deeper dive.)

You can use HTML fragments mixed in with markdown to do fancier things,
test it in preview mode to make sure it interacts as expected.

### Markdown differences

There are a few dirt extensions to standard markdown for more expressive
content authoring without getting into raw HTML. 
Use these extensions in dirt markdown to make long dashes or other features.

* Convert three dashes `---` to a long dash "—".
* Apply an inline HTML tag to a span of *text* with `{tag}text{}`.
* Use this syntax with a double quote enclosed string to apply HTML *styling*
to a span of *text* with `{"styling"}text{}`.

For example, the following shows you the markdown content
using the features listed above, followed by how it renders in a web page.

    Water is H{sub}2{}O --- Energy is E = mc{sup}2{}

Water is H{sub}2{}O --- Energy is E = mc{sup}2{}

Chunks of text can be included in a box (sometimes called a sidebar)
by putting "!!!!" lines before and after the constituent text content.
This is an example of how it looks (a haiku written by Bard the LLM).

!!!!
*Markdown: simple yet*

*Elegant, a powerful tool*

*For the web, a gift.*
!!!!

The python library implementation differs slightly
(see [the documentation](https://python-markdown.github.io/#differences)
for full details) from the original markdown as defined by its creator
([syntax summary](https://daringfireball.net/projects/markdown/syntax)).

We also support the python extensions 'footnotes', 'meta', 'tables'.
(The 'meta' extension is what allows page title and other attributes
to be noted at the top of the markdown file, as described in the next section.)

### Footnotes

Here is an example of a footnote. Use any unique matching name 
("1" in this case) and it will be assigned numbering by order of usage.

    Footnotes appear like this[^1] in markdown text (followed by the note).
    [^1]: This is the footnote content which displays at the page bottom.

*Here is the example above as rendered...* Footnotes appear like this[^1]
in markdown text (followed by the note).
[^1]: This is the footnote content which displays at the page bottom.

For complete details please see
the [documentation](https://python-markdown.github.io/extensions/tables/).

### Tables

Here is a simple example of a table. It's very hard in our experience to
make a nice looking table, but there may be a way (let us know if you know).

Header 1      | Header 2
------------- | -------------
Row 1, Col 1  | Row 1, Col 2
Row 2, Col 1  | Row 2, Col 2

For complete details please see
the [documentation](https://python-markdown.github.io/extensions/tables/).

### Limitations of markdown

The simplicity of markdown is great but it comes with a cost: it is limited.
You can always try embedding HTML markup mixed in with markdown and hope that
it interacts as you want
(use the live preview server feature for quick feedback),
and this has costs degrading readability of the original.

Here is a list of known limitations we've run into[^*].
[^*]: Ideas for workarounds or other solutions are welcome.

* Code excerpt formatting (`code`) does not allow italics or other decorations.
* Centering text is unsupported.
* Underlining text is unsupported. There is quite a [lively 
debate](https://talk.commonmark.org/t/feature-request-underline-text/343/23)
about this.
* Coloring or shading or highlighting text is unsupported.
* --There should be an expression for long dash.--
* --Section header should have anchors provided automatically.--

## Metadata

At the head of a markdown file you can write lines of metadata.

    name: value

Attribute names are lowercase words followed by a colon,
and the value is the rest of the line after a space or spaces.

The most commonly used attributes are shown below by example:

    title: Title of the page
	date: 2023-04-30 21:22:23

It's good practice to specify a title or "(untitled)" will be used.
Dates are useful for ordering collections of pages, and if omitted
the file date is used.

Pages can be assigned dispositions for rendering into the public site as:

    draft: 1
	staged: 1

Draft pages are considered unfinished and are not rendered.
Staged pages are skipped in the public website, but are included in 
a second staged version that can be browsed with `/_STAGED_` prefix.
The intention is to add some content marked as staged and then preview
how it will look on the site at the special URL `/_STAGED_/index.html`
(or other URLs with the prefix); later remove the staged attributes to go live.

It makes no sense to use both draft & staged together, and if omitted
zero values are assumed and the page is rendered normally.

