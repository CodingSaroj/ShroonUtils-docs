Error Reporter
==============

The data structures in this library use a callback to report errors. This way if you are using a logger
then you can define this callback to output to that instead of the default ``std::cerr``.

The callback is an ``std::function<void(std::string, bool)>`` defined inside the namespace
``Shroon::Structure``. A possible definition could look like:

.. code:: c++

    std::function<void(std::string, bool)> Shroon::Structure::ErrorReporter = [](std::string log, bool fatal)
    {
        std::cerr<<"Shroon::Structure::"<<(fatal ? "FatalError: " : "Error: ")<<log<<"\n";

        if (fatal)
        {
            exit(1);
        }
    };

In fact, the definition above is the default one, so, if you just want the errors to be written to
``std::cerr`` like the format above then you should add the following lines before including the
library to define the error reporter **only once in only one cpp file in your project**:

.. code:: c++

    #define SHRN_STRUCTURE_DEFAULT_ERROR_REPORTER 1
