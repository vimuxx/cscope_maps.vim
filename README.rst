Installation
============

Make the ``cs`` script available in your system's PATH. You can either download it directly or link it from this repository if you have it cloned.

Method 1: Direct Download
-------------------------

.. code-block:: bash

   curl https://raw.githubusercontent.com/vimuxx/cscope_maps.vim/master/cs -o /usr/local/bin/cs
   chmod +x /usr/local/bin/cs

Method 2: Symbolic Link
-----------------------

If you have this repository cloned (e.g., as part of a vim configuration like `.vim <https://github.com/vimuxx/.vim>`_), you can link the script:

.. code-block:: bash

   ln -s /path/to/cscope_maps.vim/cs /usr/local/bin/cs

Important Prerequisites
=======================

For all subcommands except ``find``, you **must** compile your target project before running the ``cs`` script.

It functions by analyzing build artifacts (e.g., ``.d``, ``.cmd`` files) generated during compilation. An uncompiled project will cause script failure or yield empty results. The ``find`` subcommand is the only exception, as it operates on source files directly.

Usage
=====

To see the full list of commands and project types supported:

.. code-block:: bash

   cs help

For certain projects like the Linux Kernel, the ``cs`` command must be run from the directory where the ``.config`` file is located.
