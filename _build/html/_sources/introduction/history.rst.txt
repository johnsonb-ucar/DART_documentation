Brief History
=============

This is a placeholder page. We're using it to demonstrate useful syntax provided by reStructuredText.

Examples of Useful Syntax provided by reStructuredText
------------------------------------------------------

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

Built-In Syntax for Notes and Warnings
--------------------------------------
We can intersperse the following note and caution boxes within the documentation to emphasize important points.

Notes can be used for friendly points of emphasis.

.. note:: It's important to test your setup by assimilating a single observation first.

Warnings can be used to illustrate requirements that must be followed by the user.

.. warning:: Your netCDF library must have been compiled with the same compiler (including version) that you will use to compile DART and also must include the F90 interfaces. In practice this means that even if you have a netCDF distribution on your system, you may need to recompile netCDF in a separate location to match the compiler you will use for DART.

Ability to Embed Videos
-----------------------
We can also embed videos to highlight specific points.

.. raw:: html

   <div style="text-align: center; margin-bottom: 2em;">
   <iframe width="100%" height="350" src="https://www.youtube.com/embed/GofCsx2apP4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
   </div>

.. [1] Lorenz, Edward N. (1963) “Deterministic Nonperiodic Flow.” *Journal of the Atmospheric Sciences* **20** (2): 130–141.
