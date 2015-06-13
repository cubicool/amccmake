OVERVIEW
========

This is the Bash script I use to setup my development environment on Linux
using CMake and the 3 compilers I most often test with: GCC, Clang, and
unfortunately--because of the need to write software that works on
Windows--support for cross-compiling using the mingw64 suite. You
should find it useful in your own adventures while writing wholesome,
warning-free cross-platform code. :)

USAGE
=====

amccmake <config | help | amc_dir...>

Options
-------

  config
    Creates a standard amccmake.conf file in the local directory;
    generally the first step in using amccmake.

  help
    Print this help message.

  amc_dir
    The path to a directory containing an amccmake.conf file.
    This script will generate multiple unique directories for your
    CMake-based project, one for each compiler/build combination. Currently,
    six different directories are created, all inside a directory specified
    in the configuration file (BUILD_PATH).

Example
-------

An example might look like::

  # amccmake config
  # vim amccmake.conf
  # ...edit...
  # amccmake .
  # cd build
  # less -S error.txt
  # cd gcc-debug
  # make

REQUIREMENTS
============

Any psuedo-recent version of CMake will probably be okay. You will also need to install
gcc and g++, clang and clang++, and the mingw64-g++ packages on whatever distro you
develop on (in Fedora, this package is simply called mingw64-gcc, etc.)

TODO/BUGS
=========

- There is an issue (that I have trouble reproducing consistently) whereby the compiler will
  get set to something totally wonky; it tends to happen, I think, after running amccmake
  twice, where the first attempt failed and the second does not.

