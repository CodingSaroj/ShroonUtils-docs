GettingStarted
==============

This library requires C++17 or above.

**Note**: `CMake 3.14+ <https://cmake.org>`_ is required for operations that require CMake.

CMake-based projects
-------------------------

To use this library, add the following to your CMakeLists.txt:

.. code:: cmake

    set(ShroonStructure_DIR "<path to the root of library>/cmake/")
    find_package(ShroonStructure 0.1 REQUIRED)

    # ...

    # Adding the include directories
    target_include_directories(YourTarget [PUBLIC|PRIVATE|INTERFACE] SHRN_STRUCTURE_INCLUDE_DIRS)

Non-CMake projects
-----------------------

Since this is a header only library, just add ``include/`` in the project root to your compiler
include directories.

Including the library
---------------------

If you are not defining your own error reporter function then you need to add the following lines
before including the library:

.. code:: c++

    #define SHRN_STRUCTURE_DEFAULT_ERROR_REPORTER 1

See `Error Reporter <ErrorReporter.html>`_ for more info on what this does.

There are two ways to include the library:

1. Include required data structures individually.
2. Include ``Shroon/Structure/Structures.hpp`` which includes all the data structures in the library.

Building the examples
---------------------

Configuration
-------------

Use the following commands in command prompt or terminal in the project root to configure the examples:

.. code::

    mkdir build && cd build
    cmake .. -G "<Name of generator>" -DSHRN_STRUCTURE_BUILD_EXAMPLES=ON

Building
--------

Build the example using the files for your chosen `CMake Generator <https://cmake.org/>`_.

Running
-------

The examples are stored in ``build/bin/example/`` from project root.
