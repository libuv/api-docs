
.. _handle:

:c:type:`uv_handle_t` --- Base handle
=====================================

`uv_handle_t` is the base type for other libuv handle types. Strcutures are
aligned so that any libuv handle can be cast to `uv_handle_t`. All API
functions defined here work with any handle type.


Data types
----------

.. c:type:: uv_handle_t

    The base libuv handle structure.

.. c:type:: uv_any_handle

    Union of all handle types.

.. c:type:: void (*uv_close_cb)(uv_handle_t* handle)

    Tpe definition for callback passed to :c:func:`uv_close`.


Public members
^^^^^^^^^^^^^^

.. c:member:: uv_loop_t* uv_handle_t.loop

    Pointer to the :c:type:`uv_loop_t` where the handle is running on. Readonly.

.. c:member:: void* uv_handle_t.data

    Space for user-defined arbitrary data. libuv does not use this field.


API
---

.. c:function:: int uv_is_active(const uv_handle_t* handle)

    TODO

.. c:function:: int uv_is_closing(const uv_handle_t* handle)

    TODO

.. c:function:: void uv_close(uv_handle_t* handle, uv_close_cb close_cb)

    TODO

.. c:function:: void uv_ref(uv_handle_t* handle)

    TODO

.. c:function:: void uv_unref(uv_handle_t* handle)

    TODO

.. c:function:: int uv_has_ref(const uv_handle_t* handle)

    TODO

.. c:function:: size_t uv_handle_size(uv_handle_type type)

    TODO


Refcounting
-----------

TODO

