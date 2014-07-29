
.. _prepare:

:c:type:`uv_prepare_t` --- Prepare handle
=========================================

TODO


Data types
----------

.. c:type:: uv_prepare_t

    Prepare data type.

.. c:type:: void (*uv_prepare_cb)(uv_prepare_t* handle)

    Type definition for callback passed to :c:func:`uv_prepare_start`.


Public members
^^^^^^^^^^^^^^

N/A

.. note:: The :c:type:`uv_handle_t` members also apply.


API
---

.. c:function:: int uv_prepare_init(uv_loop_t*, uv_prepare_t* prepare)

    TODO

.. c:function:: int uv_prepare_start(uv_prepare_t* prepare, uv_prepare_cb cb)

    TODO

.. c:function:: int uv_prepare_stop(uv_prepare_t* prepare)

    TODO

.. note:: The :c:type:`uv_handle_t` API functions also apply.


