###############################################
DMTN-019 Dipoles in difference imaging from DCR
###############################################

I use the StarFast simulator to generate many simulated observations of a field at a range of airmasses from 1.0 to 2.0, and at several LSST bands. After differencing each image from the observation in each band closest to zenith, I generate a metric to characterize the number and size of dipoles in the residual.

View this technote at http://dmtn-019.lsst.io or see a preview of the
current version in `this repo`_

.. _this repo: ./index.rst



..
  Uncomment this section and modify the DOI strings to include a Zenodo DOI badge in the README
  .. image:: https://zenodo.org/badge/doi/10.5281/zenodo.#####.svg
     :target: http://dx.doi.org/10.5281/zenodo.#####

Build this technical note
=========================

You can clone this repository and build the technote locally with `Sphinx`_

.. code-block:: bash

   git clone https://github.com/lsst-dm/dmtn-019
   cd dmtn-019
   pip install -r requirements.txt
   make html

The built technote is located at ``_build/html/index.html``.

Editing this technical note
===========================

You can edit the ``index.rst`` file, which is a reStructuredText document.
A good primer on reStructuredText is available at http://docs.lsst.codes/en/latest/development/docs/rst_styleguide.html

Remember that images and other types of assets should be stored in the ``_static/`` directory of this repository.
See ``_static/README.rst`` for more information.

The published technote at http://dmtn-019.lsst.io will be automatically rebuilt whenever you push your changes to the ``master`` branch on `GitHub <https://github.com/lsst-dm/dmtn-019>`_.

Updating metadata
=================

This technote's metadata is maintained in ``metadata.yaml``.
In this metadata you can edit the technote's title, authors, publication date, etc..
``metadata.yaml`` is self-documenting with inline comments.

****

Copyright 2016 AURA/LSST

This work is licensed under the Creative Commons Attribution 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by/4.0/.

.. _Sphinx: http://sphinx-doc.org
