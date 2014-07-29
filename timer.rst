
.. _timer:

:c:type:`uv_timer_t` --- Timer handle
=====================================

TODO


Data types
----------

.. c:type:: uv_timer_t

    Timer data type.

.. c:type:: void (*uv_timer_cb)(uv_timer_t* handle)

    Type definition for callback passed to :c:func:`uv_timer_start`.


Public members
^^^^^^^^^^^^^^

N/A

.. note:: The :c:type:`uv_handle_t` members also apply.


API
---

.. c:function:: int uv_timer_init(uv_loop_t* loop, uv_timer_t* handle)

    TODO

.. c:function:: int uv_timer_start(uv_timer_t* handle, uv_timer_cb cb, uint64_t timeout, uint64_t repeat)

    TODO

.. c:function:: int uv_timer_stop(uv_timer_t* handle)

    TODO

.. c:function:: int uv_timer_again(uv_timer_t* handle)

    TODO

.. c:function:: void uv_timer_set_repeat(uv_timer_t* handle, uint64_t repeat)

    TODO

.. c:function:: uint64_t uv_timer_get_repeat(const uv_timer_t* handle)

    TODO

.. note:: The :c:type:`uv_handle_t` API functions also apply.


