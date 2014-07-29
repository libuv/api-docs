
.. _check:

:c:type:`uv_check_t` --- Check handle
=====================================

TODO


Data types
----------

.. c:type:: uv_check_t

    check data type.

.. c:type:: void (*uv_check_cb)(uv_check_t* handle)

    Type definition for callback passed to :c:func:`uv_check_start`.


Public members
^^^^^^^^^^^^^^

N/A

.. note:: The :c:type:`uv_handle_t` members also apply.


API
---

.. c:function:: int uv_check_init(uv_loop_t*, uv_check_t* check)

    TODO

.. c:function:: int uv_check_start(uv_check_t* check, uv_check_cb cb)

    TODO

.. c:function:: int uv_check_stop(uv_check_t* check)

    TODO

.. note:: The :c:type:`uv_handle_t` API functions also apply.


