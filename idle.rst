
.. _idle:

:c:type:`uv_idle_t` --- Idle handle
===================================

TODO


Data types
----------

.. c:type:: uv_idle_t

    idle data type.

.. c:type:: void (*uv_idle_cb)(uv_idle_t* handle)

    Type definition for callback passed to :c:func:`uv_idle_start`.


Public members
^^^^^^^^^^^^^^

N/A

.. note:: The :c:type:`uv_handle_t` members also apply.


API
---

.. c:function:: int uv_idle_init(uv_loop_t*, uv_idle_t* idle)

    TODO

.. c:function:: int uv_idle_start(uv_idle_t* idle, uv_idle_cb cb)

    TODO

.. c:function:: int uv_idle_stop(uv_idle_t* idle)

    TODO

.. note:: The :c:type:`uv_handle_t` API functions also apply.


