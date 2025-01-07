.. image:: https://img.shields.io/badge/dmtn--306-lsst.io-brightgreen.svg
   :target: https://dmtn-306.lsst.io
.. image:: https://github.com/lsst-dm/dmtn-306/workflows/CI/badge.svg
   :target: https://github.com/lsst-dm/dmtn-306/actions/

#####################################################
Data Movement Model for the Vera C. Rubin Observatory
#####################################################

DMTN-306
========

The set of sky images recorded nightly by the camera mounted on the telescope of the Vera C. Rubin Observatory will be processed in facilities located on three continents. Data acquisition will take place at Cerro Pachón in the Andes mountains in Chile, where the observatory is located. A first copy of the raw image data set is stored at the summit site of the observatory and immediately transferred through dedicated network links to the archive site and the US Data Facility hosted at SLAC National Laboratory in California, USA.
After an embargo period of a few days, the full image set is copied to the UK and French Data Facilities, where a third copy is located. During its 10 years in operation starting late 2025, annual processing campaigns across all images taken to date will be jointly performed by the three facilities, involving sophisticated algorithms to extract the physical properties of the celestial objects and producing science-ready images and catalogs. Data products 24 resulting from the processing campaigns at each facility will be sent to SLAC and combined to create a consistent Data Release, which is served to the scientific community for its science studies via Data Access Centers in the US and 27 Chile and Independent Data Access Centers elsewhere.
In this contribution we present an overall view of how we leverage the tools selected for managing the movement of data among the Rubin processing and serving facilities, including Rucio and FTS3. We will also present the tools we developed to integrate Rucio’s data model and Rubin’s Data Butler, the software abstraction layer that mediates all access to storage by pipeline tasks that implement science algorithms.

Links
=====

- Live drafts: https://dmtn-306.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-306

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-306

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the ``acronyms.tex`` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
