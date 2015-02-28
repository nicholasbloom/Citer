# Citations from bibtex for Sublime Text

This Sublime Text 3 plugin provides citation search and Tab-completion for citations stored in a bibtex file. Configure the file path and you are good to go!

The default set up is optimized to work with AcademicMarkdown.

Uses the [bibtexparser](https://github.com/sciunto/python-bibtexparser) library from sciunto.

# Configuration

You must specify the location of your bibtex file in preferences. You can use a list of paths, and Citer will read all of the files into one database for reference.

Optionally you can define the bibtex fields to search in when using Citer: Search, the default citation format, and the list of scopes to limit the operation of the plugin (by default, Citer will only suggest citations within plain text scopes and is disabled in source code).

You can also configure the appearance of entries in the QuickView panel, by editing the "quickview_format" setting.

See below for example configuration


```js
{
    //REQUIRED - as of 2/23 this can be a list of quoted file strings or a single string

    "bibtex_file_path": "example/path/to/file.bib",

    //OPTIONAL:

    //By default Citer Search looks for your keyword in the 
    //author, title, year, and Citekey (id) feilds
    "search_fields": ["author", "title", "year", "id"] ,
    // Can be any combination of {author}, {title} and {citekey}
    "quickview_format": "{author} - {title} - {citekey}",
    // Can be any combination of {author}, {title} and {citekey}
    "pandoc_cite_fix": true
    //Default format is @Citekey
    "citation_format": "@%s",
    //list of scopes. Could be top level "text" or "source", or limit to
    // e.g "text.html.markdown"
    "completions_scopes": ["text"],
    "enable_completions": True
}
```


# Commands

**Citer: Search** - enter a search term. All results where the term is found in the author, title, citekey, or year fields will be shown (the searched fields are configurable)

**Citer: Show All** - show all the entries in your bibtex in a quick view (you can then search in the title)

# Completions

Citer provides autocompletions for your citekeys, these are enabled by default and can be disabled in the config.

# Compatibility

Citer has (to date) only been tested with bibtex generated by Mendeley. It should work with any well-formed bibtex file.

# Pandoc Fix

Cleans up Pandoc cites after multiple entries: [See Here](http://gfycat.com/TenseTameCopperbutterfly)

# Licence
LGPLv3. See COPYING for details.