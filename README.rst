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

Usage with AI (Model Context Protocol)
======================================

Including ``cs-manifest.json`` allows AI agents that support the Model Context Protocol (MCP) to use the ``cs`` command securely and effectively.

Key features of this integration:

*   **Local Execution**: The manifest explicitly states that the ``cs`` command must be run on the user's local machine, ensuring that your source code is never uploaded to a remote server.
*   **Structured Usage**: The AI can understand all the subcommands (like ``uboot``, ``llvm``, etc.), parameters, and expected outputs, reducing errors.

Example
-------

Instruct a compatible AI agent by providing a task and the manifest's path. The agent will then parse the manifest and execute the command locally with the correct parameters.

.. code-block:: text

   generate cscope and clangd database for my compiled linux kernel here,
   please use the code indexer tool whose manifest is available at
   https://raw.githubusercontent.com/vimuxx/cscope_maps.vim/master/cs-manifest.json
