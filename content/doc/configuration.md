title: dirt configuration guide

## Site configuration

Use the `_config.toml` file in the site content root directory to
configure parameters for the site. Settings not listed in this configuration
will be determined by the root configuration file dirt provides
(meta/dirt.toml), which in turn on the command line you can substitute
another file. If you use your own root configuration file it must define
all the defaults declared in dirt.toml so things will break. (This flexibility
was designed to allow a number of sites to be configured uniformly,
but it may not be that useful and the option best removed.)

The site is configured with a `_config.toml` file in the content
directory. The first line specifies pages have the string suffix added
to their titles. The next two lines specify ordering by date (per
markdown metadata) in descending order. The following lines beginning
`[menu]` define a simple menu of links that can be included in markdown
as {\$menu}.

    host_url = "https://www.example.com"
    framework = "pico"
    title_suffix = " --- dirt"
    
    [menu]
        home = "/"
        log = "/sub/log.html"
        doc = "/sub/doc.html"
    
    [feed]
        [blog]
            channel = "blog"
			description = "Describe the RSS channel"
			url = "/blog"

This configuration specifies a menu consisting of three items: "home",
"log", and "doc", with the respective links associated.

The blog feed will be generated at `/blog.xml`

## Collections

Content files in a directory can be treated as collections for
structure, such as for blog posts. Note that index files are never
included in the collection for any directory.

Use the `_collection.toml` file in the content directory to configure
parameters for the collection.

    navigation = "none"
    orderby = "date"
    ordering = "descending"

Navigation buttons (links to previous and next page in the collection)
can be optionally configured at the "top" or "bottom" position of
the page (before or after the content). Collection pages are sorted into
order according to `orderby` (date or filename) and `ordering`
(ascending or descending).

## Embed variables

Collections of pages can reference variables that describe the page within
the whole collection. In markdown, write `{$    }`,
filling in the blank with a variable name as shows below.

* **_seq**: Sequence number within the collection (1 is first, etc.)
* **_count**: Count of pages in the collection
* **_next**: Link button to the next page in the collection
* **_prev**: Link button to the previous page in the collection

(The previous/next embeds are empty in the context of the first/last page
of a collection.)
