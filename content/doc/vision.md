title: dirt vision


## Philosophy

Simplicity is the core design paradigm that aligns with many good things:
easy to learn and easy to use; fast and lightweight; and (in time) reliable.
The author loved the SSG concept, but they all have so many bells and whistles
that in practical it was needlessly awkward to use and confusing understanding
what the SSG did and what the theme or layout or template did.

With *dirt*, every effort is made to keep things as simple as possible.
Pages are written in markdown so you can organize text with headings,
use italics or bold, numbered lists, links, embed images, and so forth.
You can choose a framework for the site that is designed to handle details of
layout, fonts, and other aspects of presentation.
Beyond choosing a framework, you don't get to fiddle with minutia such as
widths of margins, but the framework should do things in a reasonable way.

This limited design is intended for people who are mostly concerned about
the content (words and images), and less about precisely how it's presented
in the web browser. The idea is to select frameworks that do a nice job
in a general way rather than fiddle with things to customize the appearance.
This not only keeps things simple, but it avoids pitfalls (that CSS is
notorious for) where you try to tweak something a little and the whole page
is suddenly messed up.

For dirt, the overriding philosophy is to keep it simple rather than
powerful, providing basic features but not "the kitchen sink". It
should be easy to build simple websites and they "just work". Small
changes, especially editing or adding new content, should be easy and
reliable.

## Alternatives

While it feels selfish, I believe there is an integrity in design that
is only achieved by following one person's vision. There must be many thousands
of web-based website building tools, yet having helped non-technically inclined
people make websites I know they are not so easy to use as they appear.
Major website building apps have many features as well as a vast library of
extensions and plug-ins that a first-time user is overwhelmed by a steep
learning curve, and for third party add-ons there is also the question of
knowing which are trustworthy and well built. Using these tools once every
few months, even if I recall what I need to do, simply navigating through all
the menus to find the screen in mind can be challenging.

The concept of WYSIWYG doesn't quite work in the modern web because page
presentation on a small mobile screen will often be *very* different from
a large screen
-- so there is no final form as when laying out for the printed page.
In my view, this argues for a strict separation of content and form,
and trusting a rendering process to handle the intricacies of HTML/CSS.
Even though I understand the web conceptually I don't have the encyclopedic
knowledge of the many complicated specs (not to mention browser compat).
Compiling code written in a high level language into machine code is a
powerful way to program for the same reasons.

SSGs provide a clean content and form separation, compiling files into
websites. I built a modest website with one of the most popular SSGs and
overall it was a great experience.
Very quickly I had a basic website up and running, but when I tried to
fine tune things it became difficult. The documentation went on and one
with so many parameters and options, and multiple ways of doing things.

So I thought this is a great idea, but it should be simpler. I was personally
glad to give up fine-tuning the presentation, I just wanted to write and
put that content out on the web in a usable form. Since I wanted to brush up
my python coding, so I wrote my own minimalist SSG in about 2000 lines of code.

## Future vision

Writing in April 2023, *dirt* has a ways to go but I think the bare bones
are there and its simplicity is promising. It will need refinement to be
ready for wider use, but it builds static websites (and it's very fast).
It does take some technical skill (I cloned a git repository and so on) to
use an SSG, but I don't think that it has to.

I think non-technically inclined people would like to use an SSG -- in a way,
the early blogging platforms were tools for building a certain kind of static
website. Everyone has been using email and editing documents long enough that
authoring a file of text is a straightforward task many can do reliably.
Along with the simplicity there is a certain robustness: you can't mess up
a text file too much, but if you do it isn't hard to see the mistake.
(About the worst is to break markdown syntax which usually means either the
intended formatting doesn't appear, or a mark up character appears as text.)

Once *dirt* is usable as a simple garden variety SSG, I'd like to explore
adding web-based file editing to the server. This would allow modifications
with just a web browser -- and you can awkwardly do this in github/gitlab
today. Since the live preview can work over the internet (not just localhost)
this should put simple website authoring within reach of anyone. And since
all the website building platform have import functions, it will always be
easy to jump to a feature-rich professional level at any time.

For all these reasons, simplicity is a core value: hence the name *dirt*.

* Content is what counts, leave the presentation to a framework
* Edit file collections to edit the website
* Mistakes don't hurt much (mess up markdown and it looks wrong locally)
* Keep everything simple
