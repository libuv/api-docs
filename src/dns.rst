
.. _dns:

DNS utility functions
=====================

TODO

Data types
----------

.. c:type:: uv_getaddrinfo_t

    `getaddrinfo` request data type.

.. c:type:: uv_nameinfo_t

    `getnameinfo` request data type.


Public members
^^^^^^^^^^^^^^

TODO


API
---

.. c:function:: int uv_getaddrinfo(uv_loop_t* loop, uv_getaddrinfo_t* req, uv_getaddrinfo_cb getaddrinfo_cb, const char* node, const char* service, const struct addrinfo* hints)

    TODO

.. c:function:: void uv_freeaddrinfo(struct addrinfo* ai)

    TODO

.. c:function:: int uv_getnameinfo(uv_loop_t* loop, uv_getnameinfo_t* req, uv_getnameinfo_cb getnameinfo_cb, const struct sockaddr* addr, int flags)

    TODO

