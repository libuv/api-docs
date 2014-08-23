
.. _misc:

Miscelaneous utilities
======================

This section contains miscelaneous functions that don't really belong in any
other section.


Data types
----------

.. c:type:: uv_buf_t

    Buffer data type.

.. c:type:: uv_rusage_t

    Data type for resource usage results.

    ::

        typedef struct {
            uv_timeval_t ru_utime; /* user CPU time used */
            uv_timeval_t ru_stime; /* system CPU time used */
            uint64_t ru_maxrss; /* maximum resident set size */
            uint64_t ru_ixrss; /* integral shared memory size */
            uint64_t ru_idrss; /* integral unshared data size */
            uint64_t ru_isrss; /* integral unshared stack size */
            uint64_t ru_minflt; /* page reclaims (soft page faults) */
            uint64_t ru_majflt; /* page faults (hard page faults) */
            uint64_t ru_nswap; /* swaps */
            uint64_t ru_inblock; /* block input operations */
            uint64_t ru_oublock; /* block output operations */
            uint64_t ru_msgsnd; /* IPC messages sent */
            uint64_t ru_msgrcv; /* IPC messages received */
            uint64_t ru_nsignals; /* signals received */
            uint64_t ru_nvcsw; /* voluntary context switches */
            uint64_t ru_nivcsw; /* involuntary context switches */
        } uv_rusage_t;

.. c:type:: uv_cpu_info_t

    Data type for CPU information.

    ::

        typedef struct uv_cpu_info_s {
            char* model;
            int speed;
            struct uv_cpu_times_s {
                uint64_t user;
                uint64_t nice;
                uint64_t sys;
                uint64_t idle;
                uint64_t irq;
            } cpu_times;
        } uv_cpu_info_t;


API
---

.. c:function:: unsigned int uv_version(void)

    Returns the libuv version packed into a single integer. 8 bits are used for
    each component, with the patch number stored in the 8 least significant
    bits. E.g. for libuv 1.2.3 this would return 0x010203.

.. c:function:: const char* uv_version_string(void)

    Returns the libuv version number as a string. For non-release versions
    "-pre" is appended, so the version number could be "1.2.3-pre".

.. c:function:: uv_buf_t uv_buf_init(char* base, unsigned int len)

    Constructor for :c:type:`uv_buf_t`.

    Due to platform differences the user cannot rely on the ordering of the
    `base` and `len` members of the uv_buf_t struct. The user is responsible for
    freeing `base` after the uv_buf_t is done. Return struct passed by value.

.. c:function:: int uv_get_process_title(char* buffer, size_t size)

    Gets the title of the current process.

.. c:function:: int uv_set_process_title(const char* title)

    Sets the current process title.

.. c:function:: int uv_resident_set_memory(size_t* rss)

    Gets the resident set size (RSS) for the current process.

.. c:function:: int uv_uptime(double* uptime)

    Gets the current system uptime.

.. c:function:: int uv_getrusage(uv_rusage_t* rusage)

    Gets the resource usage measures for the current process.

    .. note:: On Windows not all fields are set, the unsupported fields are
              filled with zeroes.

.. c:function:: int uv_cpu_info(uv_cpu_info_t** cpu_infos, int* count)

    Gets information about the CPUs on the system. The `cpu_infos` array will
    have `count` elements and needs to be freed with :c:func:`uv_free_cpu_info`.

.. c:function:: void uv_free_cpu_info(uv_cpu_info_t* cpu_infos, int count)

    Frees the `cpu_infos` array previously allocated with :c:func:`uv_cpu_info`.

.. c:function:: int uv_interface_addresses(uv_interface_address_t** addresses, int* count)

    TODO

.. c:function:: void uv_free_interface_addresses(uv_interface_address_t* addresses, int count)

    TODO

.. c:function:: void uv_loadavg(double avg[3])

    TODO

.. c:function:: int uv_ip4_addr(const char* ip, int port, struct sockaddr_in* addr)

    TODO

.. c:function:: int uv_ip6_addr(const char* ip, int port, struct sockaddr_in6* addr)

    TODO

.. c:function:: int uv_ip4_name(const struct sockaddr_in* src, char* dst, size_t size)

    TODO

.. c:function:: int uv_ip6_name(const struct sockaddr_in6* src, char* dst, size_t size)

    TODO

.. c:function:: int uv_inet_ntop(int af, const void* src, char* dst, size_t size)

    TODO

.. c:function:: int uv_inet_pton(int af, const char* src, void* dst)

    TODO

.. c:function:: int uv_exepath(char* buffer, size_t* size)

    TODO

.. c:function:: int uv_cwd(char* buffer, size_t* size)

    TODO

.. c:function:: int uv_chdir(const char* dir)

    TODO

.. uint64_t uv_get_free_memory(void)

    TODO

.. c:function:: uint64_t uv_get_total_memory(void)

    TODO

.. c:function:: uint64_t uv_hrtime(void)

    TODO


