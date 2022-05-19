Matplotlib Sphinx Theme
=======================

This is the official Sphinx theme for Matplotlib documentation.  It extends the
``pydata-sphinx-theme`` project, but adds custom styling and a navigation bar.

When creating a Matplotlib subproject you can include this theme by changing this
line in your ``conf.py`` file

.. code-block:: python

   html_theme = 'mpl_sphinx_theme'

And by including ``mpl_sphinx_theme`` as a requirement in your documentation
installation.

See the ``docs/conf.py`` file for other settings.

There are three main templates that replace the defaults in ``pydata-sphinx-theme``:

.. code-block::

   navbar_start = mpl_navbar_logo.html
   navbar_center = mpl_nav_bar.html
   navbar_end = mpl_icon_links.html   

Note that the option ``html_logo`` need not be specified as it is included 
in ``mpl_sphinx_theme/mpl_navbar_logo.html``.  The logo is stored at 
``mpl_sphinx_theme/static/images/logo2.svg``.  

To change the top navbar, edit ``mpl_sphinx_theme/mpl_nav_bar.html``

To change the social icons, edit ``mpl_sphinx_theme/mpl_icon_links.html``

To change the style, edit ``mpl_sphinx_theme/static/css/style.css``

Releasing
---------

Manually for now... see the todo below for how we hope to eventually do it 
automagically.

.. code-block::

   $ git checkout <commit-hash>
   $ git tag -a x.y.z -m 'Version x.y.z'
   $ git push upstream main --tags
   $ python -m build -s -w
   $ twine upload dist/mpl_sphinx_theme-x.y.z*

TODO: This project `uses GitHub Actions <https://github.com/matplotlib/mpl-sphinx-theme/blob/main/.github/workflows/publish-pypi.yml>`_
to automatically push a new release to PyPI whenever
a git tag is pushed. For example, to release a new ``x.y.z`` version of
``mpl-sphinx-theme``, checkout the commit you would like to release,
add a git tag, and push the tag to the ``main`` branch of the
``matplotlib/mpl-sphinx-theme`` repository:

TODO: After a new release is published on PyPI, a pull request to the ``mpl-sphinx-theme``
`conda-forge feedstock <https://github.com/conda-forge/mpl-sphinx-theme-feedstock>`_
for the new ``x.y.z`` release will automatically be opened by conda-forge bots.
