# storikaze-docview
Storikaze Documentation Viewing Program


## Basic Game Plan

Storikaze is adopting, for the sake of expediency, a PHP-based format for documentation. All pages in a documentation project will be indexed in JSON, but the pages themselves will be written in PHP. However, they will not be in standalone PHP, in that the pages themselves will not be the entry-point files on which PHP is directly invoked (and if possible, shouldn't even be placed in a server-visible directory) but will be instead invoked through the rendering engine itself.


## Significant PHP Global Variables:

__$docmain__: *[string]* The main JSON file of the documentation manifest tree

__$themdir__: *[string]* The root directory of the theme

__$drcn\___*xx*: *[string]* Instructional information that may or may-not be specific to a specific mode script of the documentation rendering engine. Currently, by the way, the only two modes being planned are one for live-rendering through Apache and another for generating a static HTML edition.

__$cdus__: *[stdClass object]* Set up by the mode script (and/or it's mode-specific subsidiaries) containing information that possibly be needed by either the rendering engine or the pages themselves. The aforementioned strings, by the way, contain information that is *provided* to the mode-script. This object, however (and all contained therein) is set up *by* the mode-script.

__$cdus->cpg__: *[string]* The current page's file location on the server

__$cdus->ptitl__: *[string]* The current page's title