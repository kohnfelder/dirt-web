title: dirt documentation

This is the documentation for the *dirt* simple static site generator (SSG).
Use *dirt* to create a simple website from one or more content pages authored
in *markdown* format (plaintext files augmented by mark-up formatting).

<table style="background-color: lightgray;"><tr><td>
WORK IN PROGRESS: (April 2023) We are building *dirt* and expanding the
documentation as features are added, but the idea is to keep it simple.
</td></tr></table>

## Introduction

If you want to present some text on the web as a site, *dirt* can do that.
Write in markdwon format (details follow) in one or more files and run
*dirt* to convery that to a nice looking collection of web pages.
You can include some image files, link between pages, and things like that.
Static sites are limited to presenting webpages, so no forms fancy web app
features are available -- a static site is like a pamphlet.

*Who's it for?* Linux users who can put together a collection of
content files, then (with layers of insulating interfaces and error
checking) for anybody.

*What's it for?* Putting content on the web as simply as possible.

To each their own: if this sounds right for you, please try it out.

Documentation is organized as follows:

* [Quick start](./quick-start.html)
* [Content authoring guide](./authoring.html)
* [Site configuration guide](./configuration.html)
* [Live preview guide](./server.html)
* Custom layouts and styles (future feature)
* [Markdown syntax](https://daringfireball.net/projects/markdown/syntax)
(n.b. [minor differences](./authoring.html#markd-diffe))
* [Vision](./vision.html)
* [Technical documentation](./technical.html)

## Conceptual

It may be useful to consider that a website conceptually consists of 
{structure, content, navigation} and a SSG simply morphs one representation 
of these into another (i.e. the kind that web browsers handle). 
At core I think we want to define a simple "source representation" 
(directories of markdown and other content) that corresponds to 
our mental conception, and a library that does the transformation. 
The SSG uses tools: config parameters, content format conversion, 
recombination of parts (building webpages and RSS feeds), etc.

## Features

* webpages are written in markdown with optional metadata at the top
* pages in a directory can be ordered and linked in sequence
* subscriptions via automatically generated RSS feeds

