
Welcome to the libuv API documentation
======================================

Overview
--------

libuv is a multi-platform support library with a focus on asynchronous I/O. It
was primarily developed for use by Node.js, but it's also used by Mozilla's
Rust language, Luvit, Julia, pyuv, and others.

.. warning::

    This documentation is not yet complete. You can help by sending
    `pull requests <https://github.com/libuv/api-docs>`_!


Features
--------

* Full-featured event loop backed by epoll, kqueue, IOCP, event ports.
* Asynchronous TCP and UDP sockets
* Asynchronous DNS resolution
* Asynchronous file and file system operations
* File system events
* ANSI escape code controlled TTY
* IPC with socket sharing, using Unix domain sockets or named pipes (Windows)
* Child processes
* Thread pool
* Signal handling
* High resolution clock
* Threading and synchronization primitives


Downloads
---------

libuv can be downloaded from `here <http://dist.libuv.org/dist/>`_.


Documentation
-------------

.. toctree::
   :maxdepth: 1

   design
   loop
   handle
   timer
   prepare
   check
   idle
   async

