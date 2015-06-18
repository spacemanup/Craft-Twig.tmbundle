# Craft Twig

A Craft CMS influenced Twig bundle for Sublime Text and Textmate, customized to work with Craft CMS specific Twig extensions.

View [Craft-Twig Demo Video](https://vimeo.com/131062707)

## Features

Craft Twig provides syntax highlighting for Craft templates, several snippets available via tab trigger, a couple key bindings, and comment support.

### Twig Tags (via key bindings)

    ctrl+shift+[    {{  }}
    ctrl+shift+5    {%  %}
    command + /     {#  #}

### Twig Tags (via tab trigger)

    }}              {{  }}
    %%              {%  %}
    ##              {#  #}

    extends         {% extends 'template' %}
    inc             {% include 'template' with vars %}
    incp            {% include 'template' with {
                      key: 'value'
                    }} %}

    set, setb       {% set var = value %}
    block, blockb   {% block name %} ... {% endblock %}
    filter, filterb {% filter name %} ... {% endfilter %}

    if, ifb         {% if condition %} ... {% endif %}
    ife             {% if condition %} ... {% else %} ... {% endif %}
    for             {% for item in seq %} ... {% endfor %}
    fore            {% for item in seq %} ... {% else %} ... {% endfor %}
    else            {% else %}

    endif           {% endif %}
    endfor          {% endfor %}
    endset          {% endset %}
    endblock        {% endblock %}
    endfilter       {% endfilter %}

### Twig Tags, Customized for Craft (via tab trigger)

    The following tab triggers output a simple example of a loop in two different formats for their respective Craft tags. The first trigger, provides an example using chaining syntax (craft.entries.section('articles')). The second trigger with the same name ending with `p`, provides the same example using object syntax.

    assets, assetsp          craft.assets loop
    categories, categoriesp  craft.categories loop
    entries, entriesp        craft.entries loop
    feed                     craft.feeds.getFeedItems loop
    tags, tagsp              craft.tags loop
    users, usersp            craft.users loop

    ciel               ceil()
    csrf               {{ getCsrfInput() }}
    exit               {% exit 404 %}
    floor              floor()
    includecss         {% set myCss %} ... {% endset %} {% includeCss myCss %}
    includecss         {% includeCssFile "/resources/css/global.css" %}
    includecss         {% set myHiResCss %} ... {% endset %} {% includeCss myHiResCss %}
    includejs          {% set myJs %} ... {% endset %} {% includeJs myJs %}
    includejs          {% includeJsFile "/resources/css/global.css" %}
    matrix             Outputs a basic Matrix Field loop
    max                max()
    min                min()
    paginate           Simple:   Outputs an example of pagination with craft.entries
                       Advanced: Outputs an example of pagination with craft.entries
    redirect           {% redirect 'login' %}
    request            craft.request.getParam()
    request            craft.request.getPost()
    request            craft.request.getQuery()
    request            craft.request.getSegment()
    requirelogin       {% requireLogin %}
    requirepermission  {% requirePermission "spendTheNight" %}
    round              round()
    shuffle            shuffle()
    switch             {% switch variable %}{% endswitch %}
    url, urla          url('path'), url('path', params, 'http', false)

### Craft Quick Reference

    info            All craft.assets properties and template tags
    info            All craft.crategories properties and template tags
    info            All craft.config properties and template tags
    info            All craft.entries properties and template tags
    info            All craft.feeds properties and template tags
    info            All craft.fields properties and template tags
    info            All craft.globals properties and template tags
    info            All craft.request properties and template tags
    info            All craft.sections properties and template tags
    info            All craft.session properties and template tags
    info            All craft.tags properties and template tags
    info            All craft.users properties and template tags
    info            All craft globals (site info, date, users, template tags)

### Debugging

    dump            <pre>{{ dump() }}</pre>

### PHP

    dd              Craft::dd();

----

## Installation

TextMate, and most editors that support TextMate bundles, allow the installation of bundles simply by extracting an archive or cloning the repository into the application's bundle directory. This bundle is no different. Below is a list of common bundle directories.

#### Sublime Text

To install this bundle in Sublime Text, download the bundle via Package Control or, if you wish to install the theme manually, a few extra steps are required:

1. Open Sublime Text and in the Preferences menu click `Browse Packages`.
2. Copy `Craft-Twig.tmbundle` into the Packages folder
3. Restart Sublime Text.

**A note on upgrading**

If you are upgrading from Craft-Twig v1 to Craft-Twig v2, you may run into a few errors having to do with cache or sessions. If you run into errors, try the following (this example use paths for OSX and Sublime Text 3):

1. Uninstall your previous version of Craft-Twig
2. Delete any cached version of Craft-Twig in<br>`~/Library/Application Support/Sublime Text 3/Cache/`
3. Delete the Sublime session in<br>`~/Library/Application Support/Sublime Text 3/Local/Session.sublime_session`
4. Delete the Package Control cache in<br>`~/Library/Application Support/Sublime Text 3/Packages/User/Package Control.cache`
5. Reinstall the Craft-Twig package

#### TextMate

- `/Library/Application Support/TextMate/Bundles`

#### Textmate 2

You can install this bundle in TextMate 2 by opening the preferences and going to the bundles tab. After installation it will be automatically updated for you.

----

## Themes

This bundle comes with two themes,

- Artisan Light
- Artisan Dark

These Themes are designed for use with the Craft-Twig bundle, but also fit general use. Feel free to use them as a base theme for constructing your own custom theme as well.

### Scopes

To aid customizing your own theme, here's a list of what each Twig element is scoped to:

    Tags:
        {{ }}:
            Tag:       punctuation.definition.tag.output.twig
            Scope:     meta.tag.output.twig
        {% %}:
            Tag:       punctuation.definition.tag.expression.twig
            Scope:     meta.tag.expression.twig
        {# #}:
            Tag:       punctuation.definition.tag.comment.twig
            Scope:     comment.block.twig

    Embedded:
        {% set css %}: source.css.embedded.twig
        {% set js %}:  source.js.embedded.twig

    Constants:
        Language:      constant.language.twig
        Numeric:       constant.numeric.twig
        Entities:      constant.character.entity.html

    Operators:
        Arithmetic:    keyword.operator.arithmetic.twig
        Assignment:    keyword.operator.assignment.twig
        Bitwise:       keyword.operator.bitwise.twig
        Comparison:    keyword.operator.comparison.twig
        Logical:       keyword.operator.logical.twig

    Strings:
        Single:        string.quoted.single.twig
        Double:        string.quoted.double.twig

    Arrays:            punctuation.section.twig
        Accessor:
            Begin:     punctuation.section.twig
            End:       punctuation.section.twig
        Separator:     punctuation.separator.twig
            Keys:      support.type.argument.twig
    Hashes:            punctuation.section.twig
        Accessor:
            Begin:     punctuation.section.twig
            End:       punctuation.section.twig
        Separator:     punctuation.separator.twig
            Keys:      support.type.argument.twig

    Tags:              entity.name.tag.twig
    Macros:            entity.name.function.twig

    Functions:         entity.name.function.twig
        Parens:
            Begin:     punctuation.section.twig
            End:       punctuation.section.twig
        Arguments:     support.other.variable

    Filters:           support.function.filters.twig
        Parens:
            Begin:     punctuation.section.twig
            End:       punctuation.section.twig
        Arguments:     support.other.variable

    Tests:             support.function.tests.twig

## Extras

There are a few additional things in `/Extras` folder

- A `Craft-Twig Unit Test.twig` file for testing the Grammar and Themes
- Sublime Text Keymaps

## References

- [Craft](http://buildwithcraft.com/)
- [Twig](http://www.twig-project.org/)
- [Sublime Text](http://www.sublimetext.com/)
- [Textmate](http://macromates.com/)
- [Straight Up Craft](http://straightupcraft.com/)

----

## Notes & Thanks

This repo has been forked from the popular [PHP-Twig](https://github.com/Anomareh/PHP-Twig.tmbundle) Textmate bundle. A lot of updates have been made, a lot of comments have been added, and parts of the bundle have been re-written from scratch (there is really no other way to make sense of maintaining a Language Grammar)!

The Craft Twig fork:

- Adds heavy commenting and new structure to the `Craft-Twig.tmLanguage` file
- Adds auto-pair key bindings for Twig action tags `{% %}`, output tags `{{ }}`
- Adds support to use the comment shortcut `command + /`
- Adds several snippets for use with Craft
- Adds quick documentation snippets for referencing Craft template tags and syntax
- Adds two Themes: Artisan Light and Artisan Dark
- Updates various scopes in the Language Grammar in attempt to accommodate more Themes
- Updates the README to document the existing features and new snippets
- Updates the README so the language refers to this fork
- Has not been tested on Windows or Linux

Happy tabbing.
