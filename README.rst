sphinx fontawesome
##################

It is a extension for sphinx.

Add directive for use fontawesome 

Installation
------------

::

    pip install sphinx_fontawesome


Or

::

    git clone https://github.com/fraoustin/sphinx_fontawesome.git
    cd sphinx_fontawesome
    python setup.py install

Use
---

In your conf.py

::

    import sphinx_fontawesome
    extensions = ['sphinx_fontawesome']

In your rst file, you can use

* directive

::

   .. fa:: check

* role

::

   :fa:`check`
   :fa:`check lg`
   :fa:`square-o`

* substitution

::

    |check|
    |square-o|

If you change in your conf.py a value of prolog_rst, and you use subsitution you
can add in prolog_rst sphinx_fontawesome.prolog

::

    prolog_rst = sphinx_fontawesome.prolog + "my prolog"

For add css fontawesome, you can cssfiles option of your theme

::

    html_theme_options = {
        'cssfiles': ["http://netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.min.css"]
    }

or create _templates/layout.html

::

    {%- extends "yourtheme/layout.html" %}
    {%- block extrahead %}
    {{ super() }}
    <link href="http://netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.min.css" rel="stylesheet">
    {% endblock %}

You can generate todo list if you add in css (as font-awesome css)

::
    table.field-list th.field-name {
        color: white;
    }

    table.field-list th.field-name .fa {
        color: black;
    }

and write todo list

::

    :|o|: task 1
    :|x|: task 2
    :|x|: task 3
