Mutex (Mutual Exclusion):

1. Purpose: Primarily used to protect shared resources from concurrent access.
2. Ownership: A mutex is owned by the task that locks it.
3. Release: Only the task that acquired the mutex should release it.
4. Use case: Ideal for protecting critical sections of code.

Semaphore:

1. Purpose: Used for signaling between tasks and controlling access to a finite number of resources.
2. Types: Binary semaphores (0 or 1) and counting semaphores (0 to n).
3. Ownership: Semaphores don't have a concept of ownership.
4. Release: Any task can release a semaphore.
5. Use cases: Signaling events, managing resource pools, implementing producer-consumer patterns.

When to use each:

Use a Mutex when:

1. You need to protect a shared resource from concurrent access.
2. You want to ensure that only the task that acquired the lock can release it.
3. You're implementing a critical section that should be accessed by only one task at a time.

Use a Semaphore when:

1. You need to signal between tasks (binary semaphore as a signal).
2. You're managing a finite pool of resources (counting semaphore).
3. You're implementing a producer-consumer pattern.
4. You need to synchronize multiple tasks with a shared event.