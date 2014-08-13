
.. _threading:

Threading and synchronization utilities
=======================================

TODO


Data types
----------

TODO


Public members
^^^^^^^^^^^^^^

TODO


API
---

.. c:function:: int uv_mutex_init(uv_mutex_t* handle)
.. c:function:: void uv_mutex_destroy(uv_mutex_t* handle)
.. c:function:: void uv_mutex_lock(uv_mutex_t* handle)
.. c:function:: int uv_mutex_trylock(uv_mutex_t* handle)
.. c:function:: void uv_mutex_unlock(uv_mutex_t* handle)

.. c:function:: int uv_rwlock_init(uv_rwlock_t* rwlock)
.. c:function:: void uv_rwlock_destroy(uv_rwlock_t* rwlock)
.. c:function:: void uv_rwlock_rdlock(uv_rwlock_t* rwlock)
.. c:function:: int uv_rwlock_tryrdlock(uv_rwlock_t* rwlock)
.. c:function:: void uv_rwlock_rdunlock(uv_rwlock_t* rwlock)
.. c:function:: void uv_rwlock_wrlock(uv_rwlock_t* rwlock)
.. c:function:: int uv_rwlock_trywrlock(uv_rwlock_t* rwlock)
.. c:function:: void uv_rwlock_wrunlock(uv_rwlock_t* rwlock)

.. c:function:: int uv_sem_init(uv_sem_t* sem, unsigned int value)
.. c:function:: void uv_sem_destroy(uv_sem_t* sem)
.. c:function:: void uv_sem_post(uv_sem_t* sem)
.. c:function:: void uv_sem_wait(uv_sem_t* sem)
.. c:function:: int uv_sem_trywait(uv_sem_t* sem)

.. c:function:: int uv_cond_init(uv_cond_t* cond)
.. c:function:: void uv_cond_destroy(uv_cond_t* cond)
.. c:function:: void uv_cond_signal(uv_cond_t* cond)
.. c:function:: void uv_cond_broadcast(uv_cond_t* cond)
.. c:function:: void uv_cond_wait(uv_cond_t* cond, uv_mutex_t* mutex)
.. c:function:: int uv_cond_timedwait(uv_cond_t* cond, uv_mutex_t* mutex, uint64_t timeout)

.. c:function:: int uv_barrier_init(uv_barrier_t* barrier, unsigned int count)
.. c:function:: void uv_barrier_destroy(uv_barrier_t* barrier)
.. c:function:: int uv_barrier_wait(uv_barrier_t* barrier)

.. c:function:: void uv_once(uv_once_t* guard, void (*callback)(void))

.. c:function:: int uv_key_create(uv_key_t* key)
.. c:function:: void uv_key_delete(uv_key_t* key)
.. c:function:: void* uv_key_get(uv_key_t* key)
.. c:function:: void uv_key_set(uv_key_t* key, void* value)

.. c:function:: int uv_thread_create(uv_thread_t* tid, uv_thread_cb entry, void* arg)
.. c:function:: unsigned long uv_thread_self(void)
.. c:function:: int uv_thread_join(uv_thread_t *tid)

TODO
