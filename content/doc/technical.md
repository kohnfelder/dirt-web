title: dirt technical documentation

This is additional documentation for dirt developers.

## SSG Config

The root configuration file is `meta/dirt.toml` (inside dirt's own directory),
or this can be specified with a custom file on the command line 
(`-c` or `--config`). This file contains:

    [dirs]
    	content = "content"
    	public = "public"
    
    [defaults]
    	title = "(untitled)"
    
    [filetypes]
    	static_types = ["img", "png", "css"]
    	page_types = ["md"]


## Context

The dirt SSG uses a context dictionary to hold various command line
arguments and configuration state. This collection of data is stored
in a types.SimpleNamespace object with attributes as follows:

* `content_path` = the pathname of the content directory defining the site
* `public_path` = the pathname of the target directory for the generated site
* `pages` = generated site pages (TODO)
* `defaults` = `[defaults]` section of the dirt config file
    * site_title = title for the site if not specified in its config
* `static_types` = list from the `[filetypes]` section of the dirt config file
* `page_types` = list from the `[filetypes]` section of the dirt config file
* `config`=None, 
* `site` = site configuration parameters from its _config.toml file
* `timestamp` = timestamp of the current generated static site files
* `snippets` = HTML fragments preloaded for use by the frameworks
* `build_time` = timestamp denoting when the current file set is generated


## Trust model

A SSG has a very simple trust model -- only fully trusted users 
have access to the inputs (content and config files) so security 
is not a big concern. However I can imagine (working hard) there 
is an exposure where a naive user is told "type XXXXX into the ZZZZ file" 
and it introduces bad stuff. Of course, markdown contains script 
and malicious script can be inserted into the webpages; and it 
could link to a bad website (not very preventable) I think the 
code is secure: HTML text gets duly escaped and such. 

One problem that I don't know how to fix is you could configure 
the target public/ directory to be anything and 
perhaps with admin access one could induce dirt to write or delete files 
in bad places.

CI script is a potential concern, but automation should run these in 
a virtual machine or container that limits access as an effective sandbox.
