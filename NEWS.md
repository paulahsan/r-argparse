argparse 2.0.1
==============
* Improved passing of arguments to Python from R.
  In particular should fix bug in using ``add_help`` argument in ``ArgumentParser``.
  Thanks George Chlipala for bug report.
* Removes ``getopt`` as a dependency.

argparse 2.0.0
==============
* Now uses ``R6`` classes instead of ``proto`` classes (#25).  
  The typical user shouldn't need to change any ``argparse`` code 
  but I did make private the previously public ``python_code``
  element of the object returned by ``ArgumentParser()``.
* Parsers now support ``add_subparsers`` (#14).
  Suggestion of Zebulun Arendsee.
* Parsers now support ``add_argument_group`` (#26).  
  Suggestion of Dario Beraldi. 
* Parsers now support ``add_mutually_exclusive_group`` (#23).  
  Suggestion of Vince Reuter.

argparse 1.1.1
==============
* Better support for machines only running Python 2.7.  
* DESCRIPTION makes explicit that it requires version 1.0.0 of ``proto`` dependency.  
  Thanks Christophe Poulet for bug report.

argparse 1.1.0
==============
* Better support for Unicode arguments/options.
  Thanks Erick Rocha Fonseca for bug report.
* Fix bug when setting ``type='integer'`` in ``add_argument``.
  Thanks Dominik Mueller for bug report and suggested solution.
* The package ``proto`` has been moved from ``Depends`` to ``Imports`` in ``DESCRIPTION``.
  We now use ``jsonlite`` package instead of ``rjson`` to parse ``JSON``.
* Better error message when accidentally trying to define a positional argument in ``ArgumentParser()``
  Suggestion of Alex Reinhart.
* Other error message output when an parsing error is detected have been tweaked slightly.

argparse 1.0.7
==============
* Now supports showing program's version with ``action='version'``.
  Suggestion of Dario Beraldi.

argparse 1.0.6
==============
* Fix bug when setting ``required=FALSE`` in ``add_argument``.
  Thanks Claire D. McWhite for bug report.

argparse 1.0.4
==============
* You can now pass in a character vector to the ``metavar`` argument of ``add_argument``.
  Thanks Paul Newell for bug report and a patch.

argparse 1.0.3
==============
* `add_argument` now throws a warning recommending using action "store_true" or "store_false" 
  if type set to "logical" and action set to "store".  Suggestion of Martí Duran Ferrer
* You can now explicitly set a `NULL` default in `add_argument`.  
  Previously one could only implicitly set a `NULL` default by not setting any default at all.
  Suggestion of Hyunsoo Kim.

argparse 1.0.2
==============
* Fixes parsing bug when using a very large argument list.  Thanks Taylor Pospisil for bug report.
* Parse error usage message now prints to standard error.  User requested help message quit status is now zero.  
  Thanks to PlasmaBinturong for report/request.
* If Python script fails with error pass on error message to user.
  Thanks to Martí Duran Ferrer for report/request.

argparse 1.0.1
==============
* Fix minor bug when running package tests on machines with both old and new versions of Python.  Thanks Prof. Brian Ripley for bug report.

argparse 1.0.0
==============
* Some support for ``choices`` argument in ``parser$add_argument``.  Thanks Christopher Small for report/request.

* Some support for ``formatter_class`` argument in ``ArgumentParser``.  Thanks Costas Bouyioukos for report/request.

* Package now looks for Python binaries with ``findpython::find_python_cmd``
  which is a little bit more robust than the previous ``argparse::find_python_cmd``.

* If ``interactive() == TRUE`` then ``parse_args`` will no longer ``quit(status=1)`` after printing a help message
  but will instead throw an error.  ``argparse`` will continue to ``quit(status=1)`` after printing a help message
  for non-interactive Rscripts.


argparse 0.5.3
==============

* Fix bug in parser$add_argument for case when we specify a default vector
  instead of scalar.  Thanks Martin Diehl for bug report.

* ``find_python_cmd`` will now also look for a ``python2.7`` binary.

* Website moved to https://github.com/trevorld/argparse
