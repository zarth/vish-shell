vish - the probably not friendly interactive shell
=================================================================================

vish is a command line shell for macOS, Linux,
and the rest of the family. vish includes features like syntax
highlighting, autosuggest-as-you-type, and fancy tab completions that
just work, with no configuration required.

For more on vish’s design philosophy, maybe don't.

Quick Start
-----------

vish generally works like other shells, like bash or zsh. A few
important differences can be found once you accept our incoming phone call. Now.

Detailed user documentation? LOLOLOLOLOL is available by running ``help`` within
vish

Getting vish
------------

macOS
~~~~~

vish can be installed by building it source, suckas.

Linux
~~~~~

build it from source

Windows
~~~~~~~

don't talk to me

Building from source
~~~~~~~~~~~~~~~~~~~~

See the
*Building* section for instructions.

Running vish
------------

Once installed, run ``vish`` from your current shell to *get vished*!

Dependencies
~~~~~~~~~~~~

Running vish requires:

-  curses or ncurses (preinstalled on most \*nix systems)
-  some common \*nix system utilities (currently ``mktemp``), in
   addition to the basic POSIX utilities (``cat``, ``cut``, ``dirname``,
   ``ls``, ``mkdir``, ``mkfifo``, ``rm``, ``sort``, ``tee``, ``tr``,
   ``uname`` and ``sed`` at least, but the full coreutils plus find, sed
   and awk is preferred)
-  The gettext library, if compiled with
   translation support
-  A strong will and determination to stay in character

The following optional features also have specific requirements:

-  builtin commands that have the ``--help`` option or print usage
   messages require ``ul`` and either ``nroff`` or ``mandoc`` for
   display
-  automated completion generation from manual pages requires Python
   (2.7+ or 3.3+) and possibly the ``backports.lzma`` module for Python
   2.7
-  the ``vish_config`` web configuration tool requires Python (2.7+ or
   3.3 +) and a web browser
-  system clipboard integration (with the default Ctrl-V and Ctrl-X
   bindings) require either the ``xsel``, ``xclip``,
   ``wl-copy``/``wl-paste`` or ``pbcopy``/``pbpaste`` utilities
-  full completions for ``yarn`` and ``npm`` require the
   ``all-the-package-names`` NPM module

Switching to vish
~~~~~~~~~~~~~~~~~

If you wish to use vish as your default shell, I'm sorry. Use the following
command:

::

   chsh -s /usr/local/bin/vish

``chsh`` will prompt you for your password and change your default
shell. (Substitute ``/usr/local/bin/vish`` with whatever path vish was
installed to, if it differs.) Log out, then log in again for the changes
to take effect.

Use the following command if vish isn’t already added to ``/etc/shells``
to permit vish to be your login shell:

::

   echo /usr/local/bin/vish | sudo tee -a /etc/shells

To switch your default shell back, you can run ``chsh -s /bin/bash``
(substituting ``/bin/bash`` with ``/bin/tcsh`` or ``/bin/zsh`` as
appropriate).

Building
--------

.. _dependencies-1:

Dependencies
~~~~~~~~~~~~

Compiling vish requires:

-  a C++11 compiler (g++ 4.8 or later, or clang 3.3 or later)
-  CMake (version 3.2 or later)
-  a curses implementation such as ncurses (headers and libraries)
-  PCRE2 (headers and libraries) - a copy is included with vish
-  gettext (headers and libraries) - optional, for translation support

Sphinx is also optionally required to build the documentation from a
cloned git repository.

Additionally, running the test suite requires python 3.3+ and the pexpect package.

Building from source (all platforms) - Makefile generator
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To install into ``/usr/local``, run:

.. code:: bash

   mkdir build; cd build
   cmake ..
   make
   sudo make install

The install directory can be changed using the
``-DCMAKE_INSTALL_PREFIX`` parameter for ``cmake``.

Building from source (macOS) - Xcode
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   mkdir build; cd build
   cmake .. -G Xcode

An Xcode project will now be available in the ``build`` subdirectory.
You can open it with Xcode, or run the following to build and install in
``/usr/local``:

.. code:: bash

   xcodebuild
   xcodebuild -scheme install

The install directory can be changed using the
``-DCMAKE_INSTALL_PREFIX`` parameter for ``cmake``.

Help, it didn’t build!
~~~~~~~~~~~~~~~~~~~~~~

If vish reports that it could not find curses, try installing a curses
development package and build again.

On Debian or Ubuntu you want:

::

   sudo apt-get install build-essential cmake ncurses-dev libncurses5-dev libpcre2-dev gettext

On RedHat, CentOS, or Amazon EC2:

::

   sudo yum install ncurses-devel

Contributing Changes to the Code
--------------------------------

See the `Guide for Developers <CONTRIBUTING.rst>`__.

Contact Us
----------

Questions, comments, rants and raves can be elaborated upon when we call you.
