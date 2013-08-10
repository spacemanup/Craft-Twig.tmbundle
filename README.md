# Craft Twig

A Craft CMS influenced Twig bundle for Sublime Text, customized to work with Craft CMS specific Twig extensions. 

### Notes & Thanks

This repo has been forked from the popular [PHP-Twig](https://github.com/Anomareh/PHP-Twig.tmbundle) Textmate bundle.  For props and credits and the README file at the time this was forked, please see the [original README file](Extras/README-Original.md).

The Craft Twig fork:
- Adds auto-pair key bindings for Twig action tags `{% %}`, output tags `{{ }}`
- Adds support to use the comment shortcut `command + /`
- Adds several snippets for use with Craft
- Adds quick documentation snippets for referencing Craft template tags and syntax
- Updates the README to document the existing features and new snippets 
- Updates the README so the language refers to this fork (and links to the previous README).
- Drops support for Textmate (I'm happy to add it back if someone wants to help integrate it)
- Has not been tested on Windows or Linux

Please report any bugs and share any recommendations that could improve usability.


## Features

### Twig Tags

    ctrl+shift+[    {{  }}
    ctrl+shift+5    {%  %}
    command + /     {#  #}

    }}              {{  }}
    %%              {%  %}
    ##              {#  #}

    extends         {% extends 'template' %}
    inc             {% include 'template' with vars only %}

    set, setb       {% set var = value %}
    block, blockb   {% block name %} ... {% endblock %}
    filter, filterb {% filter name %} ... {% endfilter %}   

    if, ifb         {% if condition %} ... {% endif %}
    ife             {% if condition %} ... {% else %} ... {% endif %}
    for             {% for item in seq %} ... {% endfor %}
    fore            {% for item in seq %} ... {% else %} ... {% endfor %}
    else            {% else %}

### Twig Tags (Customized for Craft)

    assets          Outputs a simple craft.assets query and loop
    entries         Outputs a simple craft.entries query and loop
    feeds           Outputs a simple craft.feeds query and loop
    tags            Outputs a simple craft.tags query and loop
    users           Outputs a simple craft.users query and loop
    paginate        Simple:   Outputs an example of pagination with craft.entries
                    Advanced: Outputs an example of pagination with craft.entries

    exit            {% exit 404 %}
    includecss      {% set myCss %} ... {% endset %} {% includeCss myCss %}
    includecss      {% includeCssFile "/resources/css/global.css" %}
    includecss      {% set myHiResCss %} ... {% endset %} {% includeCss myHiResCss %}
    includejs       {% set myJs %} ... {% endset %} {% includeJs myJs %}
    includejs       {% includeJsFile "/resources/css/global.css" %}
    redirect        {% redirect 'login' %}
    requirelogin    {% requireLogin %}
    requirepermission  {% requirePermission "spendTheNight" %}

### Craft Quick Reference

    info            All craft.assets properties and template tags
    info            All craft.entries properties and template tags
    info            All craft.feeds properties and template tags
    info            All craft.request properties and template tags
    info            All craft.tags properties and template tags
    info            All craft.users properties and template tags
    info            All craft globals (site info, date, users, template tags)

### Debugging
    
    dump            <pre>{{ dump() }}</pre>



## Installation

TextMate, and most editors that support TextMate bundles, allow the installation of bundles simply by extracting an archive or cloning the repository into the application's bundle directory. This bundle is no different. Below is a list of common bundle directories.


#### Sublime Text 2

Linux

    $XDG_CONFIG_HOME/sublime-text-2/Packages` or `~/.Sublime Text 2/Packages

OS X

    ~/Library/Application Support/Sublime Text 2/Packages

Windows

    %APPDATA%/Sublime Text 2/Packages/

#### TextMate

    /Library/Application Support/TextMate/Bundles


## Scopes

To aid theming, here's a list of what each Twig element is scoped to.

    Tags:
        {{ }}:
            Tag:       punctuation.section.tag.twig
            Scope:     meta.tag.template.value.twig
        {% %}:
            Tag:       punctuation.section.tag.twig
            Scope:     meta.tag.template.block.twig
        {# #}:         comment.block.twig
        Embedded:
            {{ }}:     meta.tag.inline.any.html meta.tag.template.value.twig
            {% %}:     meta.tag.inline.any.html meta.tag.template.block.twig
            
    Constants:
        Language:      constant.language.twig
        Numeric:       constant.numeric.twig
        
    Operators:
        Arithmetic:    keyword.operator.arithmetic.twig
        Assignment:    keyword.operator.assignment.twig
        Bitwise:       keyword.operator.bitwise.twig
        Comparison:    keyword.operator.comparison.twig
        Logical:       keyword.operator.logical.twig
        Other:         keyword.operator.other.twig
        
    Objects:           variable.other.twig
    Properties:        variable.other.property.twig
        Accessors:
            Dot:       punctuation.separator.property.twig
            Array:
                Begin: punctuation.section.array.begin.twig
                End:   punctuation.section.array.end.twig
                
    Strings:
        Single:        string.quoted.single.twig
        Double:        string.quoted.double.twig
    Arrays:            meta.array.twig
        Accessor:
            Begin:     punctuation.section.array.begin.twig
            End:       punctuation.section.array.end.twig
        Separator:     punctuation.separator.object.twig
    Hashes:            meta.hash.twig
        Accessor:
            Begin:     punctuation.section.hash.begin.twig
            End:       punctuation.section.hash.end.twig
        Separator:     punctuation.separator.object.twig
            Keys:      punctuation.separator.key-value.twig
            
    Keywords:          keyword.control.twig
    
    Functions:         support.function.twig
        Parens:
            Begin:     punctuation.definition.parameters.begin.twig
            End:       punctuation.definition.parameters.end.twig
        Arguments:     meta.function.arguments.twig
    Filters:           support.function.twig
        Parens:
            Begin:     punctuation.definition.parameters.begin.twig
            End:       punctuation.definition.parameters.end.twig
        Arguments:     meta.function.arguments.twig
        User-Defined:  meta.function-call.other.twig
    Macros:            meta.function-call.twig


## Extras

There are a few additional things in `/Extras`.


## References

[Craft](http://buildwithcraft.com/)
[Twig](http://www.twig-project.org/)
[Sublime Text](http://www.sublimetext.com/)
[Straight Up Craft](http://straightupcraft.com/)

