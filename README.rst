OVERVIEW
========

This is the script I use to setup my development environment using CMake and the 3
compilers I most often test with: GCC, Clang, and unfortunately--because of the need to
write software that works on Windows--some setup for cross-compiling using the mingw64
suite in Linux. You should find it useful in your own adventures with writing wholesome,
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

  acm_dir
    The path to a directory containing an amccmake.conf file.
    This script will generate multiple unique directories for your
    CMake-based project, one for each compiler/build combination. Currently,
    six different directories are created, all inside a directory specified
    in the configuration file (BUILD_PATH).

