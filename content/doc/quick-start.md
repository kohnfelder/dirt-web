title: dirt quick start

Installing *dirt* takes just a minute, and starting a new site another minute.
Of course you do have to create the content (words and images) for the site.

<table style="background-color: lightgray;"><tr><td>NOTE: 
Shell commands you type are preceded by '$' prompt; other lines are output.
</td></tr></table>

## Install dirt

*COMING SOON*

## Create a dirt directory

Start with a clean new directory to build your *dirt* website.

    $ mkdir ~/dirt-example
    $ cd ~/dirt-example

## Create starter template

Create a minimal set of files to get started (in the new directory).

    $ dirt start
    Welcome to the dirt SSG!
    Create your website by editing these simple starting files.
      Edit the homepage markdown prototype: ./content/index.md
      Customize the configuration file: ./content/_config.toml

Now you have a little homepage for your site and a site configuration file.
The content files that are the source of text and images
are in the `./content/` directory.
From these, *dirt* generates HTML files that present the content as authored
in the `./public/` directory (the name is standard for SSGs
to emphasize) that this stuff will be shown on the web.

      $ ls ./content/
      _config.toml  index.md

## Preview the website

You can see what your site looks like in the browser by using dirt as
a local webserver.

      $ ../dirt/dirt server
      Serving http://localhost:1313 ...

This command locks up the terminal while serving the *dirt*-generated
webpages for local preview, so just browse to `http://localhost:1313`
and you can see the site in its unfinished form. To get back to your
command line just interrupt with **control-C** which stops serving the
site locally.

## Start writing

To make your homepage your own, just edit the `./content/index.md` file.
There is a little filler text in there by way of example that you can
modify, or wipe it all and just start typing. Refer to other documentation
pages for details, or you can just try things and learn as you go.

## Live preview

Here's a neat trick (not original) to help make *dirt* sort of WYSIWYG.
Restart the `dirt server` (if you interrupted it previously) and browse
to the homepage. Make a few edits and save the file: *dirt* will see the
change, rebuild the site, and refresh the browser so you can immediately
see what the edited content looks like.

Keep working like this, saving to update the preview as often as you like.
You can also rebuild the site anytime with the `dirt make` command.

## Checking

The web has too make dead links because websites come and go,
but *dirt* can check that the links you put in your content work.
When you are have a good looking draft of the site, before going live
you can run the `dirt check` command to check for bad links.
This can take a few seconds for each link in your content because *dirt*
is going to try getting it and will give you an error message if it can't.
Fix any errors, check one more time, and you are good to go.

## Publishing to the web

*COMING SOON*

-----------------------

