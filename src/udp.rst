
.. _udp:

:c:type:`uv_udp_t` --- UDP handle
=================================

UDP handles encapsulate UDP communication for both clients and servers.


Data types
----------

.. c:type:: uv_udp_t

    UDP handle type.

.. c:type:: uv_udp_send_t

    UDP send request type.

.. c:type:: uv_udp_flags

    Flags used in :c:func:`uv_udp_bind` and :c:type:`uv_udp_recv_cb`..

    ::

        enum uv_udp_flags {
            /* Disables dual stack mode. */
            UV_UDP_IPV6ONLY = 1,
            /*
            * Indicates message was truncated because read buffer was too small. The
            * remainder was discarded by the OS. Used in uv_udp_recv_cb.
            */
            UV_UDP_PARTIAL = 2,
            /*
            * Indicates if SO_REUSEADDR will be set when binding the handle in
            * uv_udp_bind.
            * This sets the SO_REUSEPORT socket flag on the BSDs and OS X. On other
            * Unix platforms, it sets the SO_REUSEADDR flag. What that means is that
            * multiple threads or processes can bind to the same address without error
            * (provided they all set the flag) but only the last one to bind will receive
            * any traffic, in effect "stealing" the port from the previous listener.
            */
            UV_UDP_REUSEADDR = 4
        };

.. c:type:: void (*uv_udp_send_cb)(uv_udp_send_t* req, int status)

    Type definition for callback passed to :c:func:`uv_udp_send`, which is
    called after the data was sent.

.. c:type:: void (*uv_udp_recv_cb)(uv_udp_t* handle, ssize_t nread, const uv_buf_t* buf, const struct sockaddr* addr, unsigned flags)

    Type definition for callback passed to :c:func:`uv_udp_recv_start`, which
    is called when the endpoint receives data.

    * `handle`: UDP handle
    * `nread`:  Number of bytes that have been received.
      0 if there is no more data to read. You may discard or repurpose
      the read buffer. Note that 0 may also mean that an empty datagram
      was received (in this case `addr` is not NULL). < 0 if a transmission
      error was detected.
    * `buf`: :c:type:`uv_buf_t` with the received data.
    * `addr`: ``struct sockaddr*`` containing the address of the sender.
      Can be NULL. Valid for the duration of the callback only.
    * `flags`: One or more or'ed UV_UDP_* constants. Right now only
      ``UV_UDP_PARTIAL`` is used.

    .. note:: The receive callback will be called with `nread` == 0 and
              `addr` == NULL when there is nothing to read, and with
              `nread` == 0 and `addr` != NULL when an empty UDP packet is
              received.


Public members
^^^^^^^^^^^^^^

.. c:member:: size_t uv_udp_t.send_queue_size

    Number of bytes queued for sending. This field strictly shows how much
    information is currently queued.

.. c:member:: size_t uv_udp_t.send_queue_count

    Number of send requests currently in the queue awaiting to be processed.

.. c:member:: uv_udp_t* uv_udp_send_t.handle

    UDP handle where this send request is taking place.

.. note:: The :c:type:`uv_handle_t` members also apply.


API
---

.. c:function:: int uv_udp_init(uv_loop_t*, uv_udp_t* handle)

    Initialize a new UDP handle. The actual socket is created lazily.
    Returns 0 on success.

.. c:function:: int uv_udp_open(uv_udp_t* handle, uv_os_sock_t sock)

    Opens an existing file descriptor or Windows SOCKET as a UDP handle.

    Unix only:
    The only requirement of the `sock` argument is that it follows the datagram
    contract (works in unconnected mode, supports sendmsg()/recvmsg(), etc).
    In other words, other datagram-type sockets like raw sockets or netlink
    sockets can also be passed to this function.

.. c:function:: int uv_udp_bind(uv_udp_t* handle, const struct sockaddr* addr, unsigned int flags)

    Bind the UDP handle to an IP address and port.

    :param handle: UDP handle. Should have been initialized with
        :c:func:`uv_udp_init`.

    :param addr: `struct sockaddr_in` or `struct sockaddr_in6`
        with the address and port to bind to.

    :param flags: Indicate how the socket will be bound,
        ``UV_UDP_IPV6ONLY`` and ``UV_UDP_REUSEADDR`` are supported.

    :returns: 0 on success, or an error code < 0 on failure.

.. c:function:: int uv_udp_getsockname(const uv_udp_t* handle, struct sockaddr* name, int* namelen)

    Get the local IP and port of the UDP handle.

    :param handle: UDP handle. Should have been initialized with
        :c:func:`uv_udp_init` and bound.

    :param name: Pointer to the structure to be filled with the address data.
        In order to support IPv4 and IPv6 `struct sockaddr_storage` should be
        used.

    :param namelen: On input it indicates the data of the `name` field. On
        output it indicates how much of it was filled.

    :returns: 0 on success, or an error code < 0 on failure.

.. c:function:: int uv_udp_set_membership(uv_udp_t* handle, const char* multicast_addr, const char* interface_addr, uv_membership membership)

    TODO

.. c:function:: int uv_udp_set_multicast_loop(uv_udp_t* handle, int on)

    TODO

.. c:function:: int uv_udp_set_multicast_ttl(uv_udp_t* handle, int ttl)

    TODO

.. c:function:: int uv_udp_set_multicast_interface(uv_udp_t* handle, const char* interface_addr)

    TODO

.. c:function:: int uv_udp_set_broadcast(uv_udp_t* handle, int on)

    TODO

.. c:function:: int uv_udp_set_ttl(uv_udp_t* handle, int ttl)

    TODO

.. c:function:: int uv_udp_send(uv_udp_send_t* req, uv_udp_t* handle, const uv_buf_t bufs[], unsigned int nbufs, const struct sockaddr* addr, uv_udp_send_cb send_cb)

    TODO

.. c:function:: int uv_udp_try_send(uv_udp_t* handle, const uv_buf_t bufs[], unsigned int nbufs, const struct sockaddr* addr)

    TODO

.. c:function:: int uv_udp_recv_start(uv_udp_t* handle, uv_alloc_cb alloc_cb, uv_udp_recv_cb recv_cb)

    TODO

.. c:function:: int uv_udp_recv_stop(uv_udp_t* handle)

    TODO

.. note:: The :c:type:`uv_handle_t` API functions also apply.


