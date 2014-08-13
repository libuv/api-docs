
.. _dll:

Shared library handling
=======================

TODO

Data types
----------

.. c:type:: uv_lib_t

    Shared library data type.


Public members
^^^^^^^^^^^^^^

N/A


API
---

.. c:function:: int uv_dlopen(const char* filename, uv_lib_t* lib)

    TODO

.. c:function:: void uv_dlclose(uv_lib_t* lib)

    TODO

.. c:function:: uv_dlsym(uv_lib_t* lib, const char* name, void** ptr)

    TODO

.. c:function:: const char* uv_dlerror(const uv_lib_t* lib)

    TODO

