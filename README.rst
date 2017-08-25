==================================
Example Block Extension For Sphinx
==================================

This is a modified fork of Serge Domkowski's `examplecode extension <https://bitbucket.org/birkenfeld/sphinx-contrib/src/7f39b7f255e34bfe588f0065a5d9709a7d8e7614/examplecode/?at=default>`_ for Sphinx.

About
=====

This is a simple extension that, when rendered as HTML, will fold multiple
example blocks containing different examples into a single block
which can be toggled from one to another using buttons.

This extension adds the ``example-block`` directive which adds a class to
a container wrapping the code blocks that should be folded. The class allows
the included JavaScript and CSS to render the folded block and buttons.



Quick Example
-------------

Source would look something like this::

    .. example-block::
        .. code-block:: python

            import api

        .. code-block:: ruby

            require 'my-api'

*sphinxcontrib-exampleblock* makes use of pygments which are supported OOT with sphinx.

That means all languages and lexers which are working with sphinx are working with *sphinxcontrib-exampleblock*

If you want to use a example block which is not supported by that you can write you own lexer or use another one as *alias*.

Let's say we want to use Debian and Fedora package management examples. Both are not yet supported with pygments.

In your conf.py add the following code

.. code-block:: python

   from sphinx.highlighting import lexers
   from pygments.lexers import BashLexer
   lexers["debian", "dfn"] = BashLexer()


Here we are telling sphinx to use the lexer for ``bash`` as alias for Debian and Fedora.

The drawback is that you do not have color support for ``apt`` or ``dnf``.
On the other site sphinx will be able to build without errors.

Installation
------------

.. code-block:: console

    $ pip install sphinxcontrib-exampleblock


Enabling The eExtension In Sphinx
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Add sphinxcontrib.exampleblock to the list of extensions in the conf.py file. For example:

.. code-block:: console

    extensions = ['sphinxcontrib.example']


Contribute
----------

- `Issue Tracker <https://github.com/testthedocs/sphinxcontrib-exampleblock/issues>`_
- `Source Code <https://github.com/svx/sphinxcontrib-exampleblock>`_

Support
-------

If you are having issues, please let us know.


License
-------

The project is licensed under MIT.
