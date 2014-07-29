
.. _loop:

:c:type:`uv_loop_t` --- Event loop
==================================

TODO


Data types
----------

.. c:type:: uv_loop_t

    Loop data type.


Public members
^^^^^^^^^^^^^^

.. c:member:: void* uv_loop_t.data

    Space for user-defined arbitrary data. libuv does not use this field.


API
---

.. c:function:: int uv_loop_init(uv_loop_t* loop)

    TODO

.. c:function:: int uv_loop_close(uv_loop_t* loop)

    TODO

.. c:function:: uv_loop_t* uv_default_loop(void)

    TODO

.. c:function:: int uv_run(uv_loop_t* loop, uv_run_mode mode)

    TODO

.. c:function:: int uv_loop_alive(const uv_loop_t* loop)

    TODO

.. c:function:: void uv_stop(uv_loop_t* loop)

    TODO

.. c:function:: size_t uv_loop_size(void)

    TODO

.. c:function:: int uv_backend_fd(const uv_loop_t* loop)

    TODO

.. c:function:: int uv_backend_timeout(const uv_loop_t* loop)

    TODO

.. c:function:: uint64_t uv_now(const uv_loop_t* loop)

    TODO

.. c:function:: void uv_update_time(uv_loop_t* loop)

    TODO

