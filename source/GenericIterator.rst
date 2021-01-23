Generic Iterator
================

Iterator is a very common object used for iterating the elements of different data structures with
the same API. These are most commonly used with ``for`` loops. C++ style foreach loops use iterators
as well.

About this implementation
-------------------------

The iterator implemented in this library is a generic iterator, meaning it can be used by any data
structure as long as the data structure match the criteria for data structures that can be iterated
by this iterator.

Criteria for ability to support data structure
----------------------------------------------

A data structure which needs to be iterated by this iterator needs to follow the following criteria:

1. The structure should have a way to access all the elements using unique continuous unsigned indices.
2. Implement ``bool IsIndexValid(size_t index) const`` function which returns if the given index is valid.
3. Implement ``ValueType & Get(size_t index)`` which returns the element which belongs to the given
   index. ``ValueType`` must be the type which is passed as first template parameter to
   ``GenericIterator``. A const version of this function i.e. ``const ValueType & Get(size_t index) const``
   is also required.

The iterator declares the ``StructureType`` as a friend class so, the data structure can access private
members of the iterator.

Unless the required functions are part of the API for the structure, it is recommended to implement
these functions as private members and add ``GenericIterator`` as a friend class.
