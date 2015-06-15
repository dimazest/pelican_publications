A plugin for the Pelican_ static website generator that
embeds a BibTeX publication list in a page or article
using a ``publications`` restructured text directive.

Usage

* by passing a path to a ``.bib`` file::

    .. publications:: path/to/publications.bib
        :template: path/to/publications.html
        :sort: date

* by passing BibTeX entries directly::

    .. publications::

        @article{hill2014simlex,
          title={Simlex-999: Evaluating semantic models with (genuine) similarity estimation},
          author={Hill, Felix and Reichart, Roi and Korhonen, Anna},
          journal={arXiv preprint arXiv:1408.3456},
          year={2014},
          url={http://arxiv.org/pdf/1408.3456v1.pdf}
        }

By default pelican_publications uses a ``publications`` template
in the Pelican theme. This can be overridden by setting
the template option as a path to a Jinja2 template.
The template is passed one parameter, ``publications``, which is
a list of BibTeX entries; alternatively the BibTex entries are passed
as the directive content. These BibTeX entries are simple dictionaries
in the format used by the bibtexparser_ Python package, with a few
customisations such as converting page ranges to use an html en dash
and splitting the author field into a list of authors.

Possible sort options are:

date
    Sort by publication date (this is the default).

key
    Sort by BibTeX key.

name
    Sort by author names.

.. _Pelican: http://docs.getpelican.com
.. _bibtexparser: https://bibtexparser.readthedocs.org
