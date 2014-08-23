
.. _misc:

Miscelaneous utilities
======================

TODO

Data types
----------

.. c:type:: uv_buf_t

    Buffer data type.


Public members
^^^^^^^^^^^^^^

TODO


API
---

.. c:function:: unsigned int uv_version(void)

    TODO

.. c:function:: const char* uv_version_string(void)

    TODO

.. c:function:: uv_buf_t uv_buf_init(char* base, unsigned int len)

    TODO

.. c:function:: char** uv_setup_args(int argc, char** argv)

    TODO

.. c:function:: int uv_get_process_title(char* buffer, size_t size)

    TODO

.. c:function:: int uv_set_process_title(const char* title)

    TODO

.. c:function:: int uv_resident_set_memory(size_t* rss)

    TODO

.. c:function:: int uv_uptime(double* uptime)

    TODO


.. c:function:: char** uv_setup_args(int argc, char** argv)

    TODO

.. c:function:: int uv_get_process_title(char* buffer, size_t size)

    TODO

.. c:function:: int uv_set_process_title(const char* title)

    TODO

.. c:function:: int uv_resident_set_memory(size_t* rss)

    TODO

.. c:function:: int uv_uptime(double* uptime)

    TODO


.. c:function:: char** uv_setup_args(int argc, char** argv)

    TODO

.. c:function:: int uv_get_process_title(char* buffer, size_t size)

    TODO

.. c:function:: int uv_set_process_title(const char* title)

    TODO

.. c:function:: int uv_resident_set_memory(size_t* rss)

    TODO

.. c:function:: int uv_uptime(double* uptime)

    TODO

.. c:function:: int uv_getrusage(uv_rusage_t* rusage)

    TODO

.. c:function:: int uv_cpu_info(uv_cpu_info_t** cpu_infos, int* count)

    TODO

.. c:function:: void uv_free_cpu_info(uv_cpu_info_t* cpu_infos, int count)

    TODO

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


