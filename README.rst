DART Documentation
==================

This repository contains a draft of DART documentation created using reStructuredText and Sphinx.

Installing Sphinx
-----------------

There are many ways to install Sphinx. The easiest way is to use pip:

.. parsed-literal::
   $ pip install -U Sphinx

If you prefer to use a package manager such as anaconda, install it following these instructions:

https://docs.conda.io/en/latest/miniconda.html

and then create an environment:

.. parsed-literal::
   $ create -n sphinx_env python docutils sphinx
   $ source activate sphinx_env

Rebuilding Documentation
------------------------

To rebuild the documentation, cd to the respository root and

.. parsed-literal::
   $ make clean ; make html

The rebuilt documentation will be accessible via:

.. parsed-literal::
   $ open _build/html/index.html
