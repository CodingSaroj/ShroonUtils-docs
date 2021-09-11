GettingStarted
==============

This is a header-only library, so no building is required.

Although, you do need to add the following code before including the library headers in **one** of
your source files:

.. code:: c

    #define SUTL_IMPLEMENTATION

Error Handler
-------------

By default, all the errors are written to ``stderr``.

But if you want to use a custom handler then add the following code before including the library
headers in the same source file where ``SUTL_IMPLEMENTATION`` is defined:

.. code:: c

    #define SUTL_ERROR_HANDLER_CUSTOM 1

Then you need to add the following code to initialize the error handler:

.. code:: c

    void ( * SUTLErrorHandler)(const char *) = MyErrorHandlerFn;

Replace ``MyErrorHandlerFn`` with your custom error handler function.

An example of an error handler function is (this is also the default implementation):

.. code:: c
    
    void MyErrorHandlerFn(const char * msg)
    {
        fprintf(stderr, "%s\n", msg);
    }
