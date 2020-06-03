.. Data Assimilation Research Testbed documentation master file, created by
   sphinx-quickstart on Mon Jun  1 21:17:49 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to the Data Assimilation Research Testbed
=================================================
The following are examples of useful features that are built into reStructuredText. All of the examples below are entered as plain text in the repository and are rendered here as html using a syntax parser.

The table of contents to the left are also entered as plain text and the parser organizes them into an ordered hierarchy with collapsable submenus and "Previous" and "Next" links between each page. Click on :doc:`/the_elements_of_dart/observations` for an example.

Full Citations in Footnotes & Mathematical Symbols
--------------------------------------------------
The Lorenz (1963) [1]_ model is specified by a set of three ordinary differential equations:

.. math::

   \frac{dx}{dt} = \sigma(y-x)

   \frac{dy}{dt} = x(\rho-z)-y

   \frac{dz}{dt} = xy-\beta z

where the coefficients are given default values in DART: :math:`\rho=28`, :math:`\sigma=10` and :math:`\beta=8/3`.

Syntax Highlighting in Code Snippets and Namelists
--------------------------------------------------
Fortran syntax can be highlighted both in namelists:

.. code-block:: fortran

   &perfect_model_obs_nml
      single_file_out            = .true.
      output_state_files         = "perfect_output.nc"
      output_interval            = 1,
   /

and in code snippets:

.. code-block:: fortran

   module model_mod

      use        types_mod,      only : r8, i8, i4

      real(r8) ::  sigma = 10.0_r8
      real(r8) ::      r = 28.0_r8
      real(r8) ::      b = 8.0_r8 / 3.0_r8
      real(r8) :: deltat = 0.01_r8
      integer  :: time_step_days = 0
      integer  :: time_step_seconds = 3600

      ! compute the lorenz model dt from standard equations

      dt(1) = sigma * (x(2) - x(1))
      dt(2) = -1.0_r8*x(1)*x(3) + r*x(1) - x(2)
      dt(3) = x(1)*x(2) - b*x(3)

    end module model_mod

Syntax highlighting also works in other languages such as bash:

.. code-block:: bash

   # /glade/u/home/johnsonb/.bashrc
   module load ncview
   module load diffuse

Introduction
------------

A brief introduction to data assimilation and DART's design philosopy.

* :doc:`/introduction/history`
* :doc:`/introduction/philosophy`

.. toctree::
 :maxdepth: 2
 :hidden:
 :caption: Introduction

 /introduction/history
 /introduction/philosophy

The Elements of DART
--------------------

These describe the necessary elements of an assimilation system.

* :doc:`/the_elements_of_dart/model-state`
* :doc:`/the_elements_of_dart/observations`
* :doc:`/the_elements_of_dart/forward-operators`
* :doc:`/the_elements_of_dart/filters`
* :doc:`/the_elements_of_dart/localization`
* :doc:`/the_elements_of_dart/inflation`

.. toctree::
 :maxdepth: 3
 :hidden:
 :caption: The Elements of DART

 /the_elements_of_dart/model-state
 /the_elements_of_dart/observations
 /the_elements_of_dart/forward-operators
 /the_elements_of_dart/filters
 /the_elements_of_dart/localization
 /the_elements_of_dart/inflation

Running DART
------------

Instructions for downloading and building DART.

* :doc:`/running_dart/quick-start`
* :doc:`/running_dart/system-requirements`
* :doc:`/running_dart/downloading`
* :doc:`/running_dart/building`
* :doc:`/running_dart/running`
* :doc:`/running_dart/assimilation-cycle`

.. toctree::
 :maxdepth: 2
 :hidden:
 :caption: Running DART

 /running_dart/quick-start
 /running_dart/system-requirements
 /running_dart/downloading
 /running_dart/building
 /running_dart/running
 /running_dart/assimilation-cycle

Supported Models
----------------

A description of the models supported by DART.

* :doc:`/supported_models/simple-models`
* :doc:`/supported_models/large-geophysical-models`
* :doc:`/supported_models/previously-supported-models`
* :doc:`/supported_models/add-your-model`


.. toctree::
 :maxdepth: 2
 :hidden:
 :caption: Supported Models

 /supported_models/simple-models
 /supported_models/large-geophysical-models
 /supported_models/previously-supported-models
 /supported_models/add-your-model

Diagnostics
-----------

Available diagnostics to apply to your assimilation.

* :doc:`/diagnostics/dart-qc-codes`
* :doc:`/diagnostics/assimilation-effective`
* :doc:`/diagnostics/observation-space-diagnostics`
* :doc:`/diagnostics/state-space-diagnostics`
* :doc:`/diagnostics/matlab-diagnostic-scripts`

.. toctree::
 :maxdepth: 2
 :hidden:
 :caption: Diagnostics

 /diagnostics/dart-qc-codes
 /diagnostics/assimilation-effective
 /diagnostics/observation-space-diagnostics
 /diagnostics/state-space-diagnostics
 /diagnostics/matlab-diagnostic-scripts

Further Aspects of DA
---------------------

Guidance for additional aspects of Data Assimilation.

* :doc:`/further_aspects_of_da/perfect-model-experiment`
* :doc:`/further_aspects_of_da/initial-ensemble-construction`
* :doc:`/further_aspects_of_da/localization-tuning`
* :doc:`/further_aspects_of_da/inflation-tuning`

.. toctree::
 :maxdepth: 2
 :hidden:
 :caption: Further Aspects of DA

 /further_aspects_of_da/perfect-model-experiment
 /further_aspects_of_da/initial-ensemble-construction
 /further_aspects_of_da/localization-tuning
 /further_aspects_of_da/inflation-tuning

FORD API
--------

Example link to external resource.

* `Example External Link <https://github.com/Fortran-FOSS-Programmers/ford>`_

.. toctree::
 :maxdepth: 2
 :hidden:
 :caption: API

 Example External Link <https://github.com/Fortran-FOSS-Programmers/ford>


Contributors' Guide
-------------------

A guide for adding your code to DART.

* :doc:`/contributors_guide/pull-requests`
* :doc:`/contributors_guide/style-guide`

.. toctree::
 :maxdepth: 2
 :hidden:
 :caption: Contributors' Guide

 /contributors_guide/pull-requests
 /contributors_guide/style-guide

.. [1] Lorenz, Edward N. (1963) “Deterministic Nonperiodic Flow.” *Journal of the Atmospheric Sciences* **20** (2): 130–141.
