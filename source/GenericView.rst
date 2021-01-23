Generic View
============

A view is a data structure which generally is used to access (i.e. read or write) raw memory in-place
i.e. without copying. This speeds up the program because it is no longer moving bytes from one place
to another for every small use. It is also used as a common interface to raw memory containing an
array of objects.

C++ STL Implementations
-----------------------

    From C++17 the STL provides ``std::string_view`` which works as a view of ``char`` s.

    From C++20 the STL provides ``std::span`` which works as a view for any type.

Since, there is no "generic" view for all types in C++ 17, I implemented one in this library.

Memory View
-----------

Memory view is basically ``GenericView<uint8_t>``. The only way it differs from generic view of
``uint8_t`` is that it is written to ``std::ostream`` s, which provides a better view of the memory
than the default generic view way which is made for objects.

Reference
---------

The API reference for generic view can be found `here <DataStructuresAPI.html#_CPPv4I0EN6Shroon9Structure11GenericViewE>`_. Memory view uses the same API.
