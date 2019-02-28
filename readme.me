# Seminar questions

### Threads, synchronisation and deadlock

#### Threads


**1. How do threads differ from processes?**

Threads share memory, processes do not share memory. In other words, threads run in a shared memory space, while processes run in separate memory spaces.

**2. Why is it more “expensive” to create a new process compared to creating a new thread?**

We must allocate new memory space and copy data for every new process. Threads only need its own stack and CPU contexts.

**3. In short, explain the many-to-one user level thread model. Also explain what happens if one of the threads makes a blocking system call in the many-to-one user level thread model.**

In the many to one user level thread model, there is only one kernel thread, but mapped to it can be several user level threads. But, having only one kernel thread means that if one of the user level treads make a system call, it will block all other threads!

#### Need for synchronization
**4. What is meant by an atomic operation? Give examples of non-atomic operations.**

An atomic operation is an operation that appears to the rest of the system to occur at once. There will be no interruption in the middle of it. It will run from start to finish like it was just one instruction. An example of a non-atomic operation is decrementing / incrementing a variable.

**5. Define the following terms: Race condition, Data race, Critical section and Mutual exclusion.**

* **Race Condition:** A race condition exists when some outcome depends on the timing or sequence of events. A race condition exists when two or more threads would access a shared resources in such a way that would cause unexpected results.

* **Data Race:** A data race occurs when two instructions from different threads access some shared resource and at least one of these is a write, and there is no synchronization.

* **Critical section:** Critical section is a part of a program that should not be executed by more than one thread at a time.

* **Mutual exclusion:** Only one task is allowed to be in its critical section at a time.

#### Properties of lock operations
**6. What is meant by a spin lock? What is meant by busy waiting?**

A spin lock is just a while loop, continuously checking some condition to see if the lock is open.

Busy waiting is when a process is wasting cpu cycles while waiting, by continuously looping and doing nothing.

**7. In the context of mutual exclusion, what is meant by starvation?**

If a process never gets to run in its critical section.

#### Software based synchronization

**8. What are the limitations of Petersson’s solution to the mutual exclusion problem?**

In Petersson's solution when a process wants to enter its critical section, it must raise a flag, and then set the turn to the other task. When that task is done, it will lower its flag and allow the first ask to enter.

```c
flag[0] = true; // Shared
turn = 1;       // Shared
while (flag[1] && turn == 1) { /* Busy waiting */ }
// Critical section
flag[0] = false;
```

The limitations are that it is not guaranteed to work on modern architectures, and it works only for two concurrent tasks (but can be generalized).

### Hardware support for synchronization
**9. Name two atomic CPU instructions that can be used to implement synchronization locks.**

* **Swap:** The swap-instruction swaps the values of two memory slots.
* **TAS:** The TAS-instruction (TestAndSet) will set and test the value of a memory slot.

**10. How can spin locks be constructed using the two atomic instructions from above?**

##### Swap

Before entering the critical section, we will swap the values of the lock and a variable ``key``, until ``key`` (the value of lock, now set to true) is false.

```c
do {
  bool key = true;
  while (key == true) {
    swap(&lock, &key);
  }
  // Critical section
  lock = false;
  // Remainder section
} while (true);
```

##### **TestAndSet (TAS)**

We will always call the TAS in a while loop, until the lock is false.

```c
do {
  while (TestAndSet(&lock)) { /* Busy wait */ }
  // Critical section
  lock = false;
  // Remainder section
} while (true);

```

#### Abstractions for synchronization
**11. What operations can be performed on a semaphore and how do these operations work?**

Semaphores have 4 operations:

##### init()

Initializes the semaphore.

```c
sem_t *init(int n) {
  sem_t *S = malloc(sizeof(*int));
  *S = n;
  return S;
}
```

##### destroy()

Deinitialize the semaphore.

```c
void destroy(sem_t *S) {
  free(S);
}
```

##### wait()

Decrements the semaphore if the counter is above zero, otherwise wait until it is.

```c
  void wait(sem_t *S) {
    while (*S <= 0);
    (*S)--;
  }
```

##### signal()

Increment the semaphore.
```c
  void signal(sem_t *S) {
    (*S)++
  }
```

**12. What operations can be performed on a mutex lock and how do these operations work?**

A mutex lock is similar to a binary semaphore. It should have some sort of retain and release operations.

**13. What is the difference between a mutex lock and a semaphore?**

A mutex lock is like a binary semaphore, meaning only one task at a time can be the owner. With counting semaphores there can be several threads in the critical section.

**14. When implementing semaphores and mutex locks, how can busy waiting be avoided?**

We can introduce some sort of wait queue. When a thread is waiting to enter the critical section, it will be put to sleep, and awaken when it's the thread's turn.

### Deadlock
**15. Name and explain the for necessary conditions for deadlock?**

There are 4 conditions for deadlock:

* **Mutual exclusion:** Only one task at a time can use a resource instance.
* **Hold and wait:** A task holding at least one resource is waiting to acquire additional resources held by other tasks.
* **No preemption:** A resource can be released only voluntarily by the task holding it.
* **Circular wait:** Task 1 is waiting for task 2, who is waiting for task 3 und so weiter.

**16. Explain the differences between deadlock prevention and deadlock avoidance.**

* **Deadlock avoidance** is when deadlocks cannot occur at all (because a task will not acquire some shared resource unless the system deems it safe).
* **Deadlock prevention** is when the system prevents a deadlock. The system makes sure that at least one of the four conditions doesn't hold.

**17. Explain how deadlock prevention can be used to prevent circular wait.**

By imposing total ordering.

**18. What conclusions regarding deadlock can be made using a resource allocation graph (RAG)?**

If there are deadlocks, or possibilities of a deadlock.

#### Dining philosophers
**19. Explain the Dining philosophers problem.**

The dining philosophers problem is a way to visualize deadlocks. There are five philosophers around a table, with 1 chopstick between each philosopher, totalling in 5 chopsticks. To eat, a philosopher needs 2 chopsticks. And a chopstick can only be held by one philosopher at a time. They will first pick up the left one, then the right one. This will cause a deadlock.

#### Rendezvous
**20. Two threads A and B both executes a loop. Explain how two semaphores can be used to enforce the two threads to have a rendezvous after each iteration, i.e., the threads should perform the iterations in lockstep. Lockstep means that the threads first perform iteration 0, then iteration 1, then iteration 2, etc. For each iteration the order between the threads should not be restricted. The following is an example of a valid trace of execution: A0, B0, B1, A1, B2 A2. The following are examples of invalid traces of execution: A0, A1, B0, B1 and A0, B0, B1, B2.**

We need two semaphores, A and B initialized to 1 and 0, respectively. When thread A is executing, it should first wait for semaphore A, then run it's code. Afterwards it should signal B. Vice versa for thread B.

**21. Could mutex locks be used instead of semaphores when solving the rendezvous problem above? Justify your answer.**

No, we have no guarantee that thread B will execute after thread A has relinquished the mutex lock.

#### Bounded buffer
**22. Explain how semaphores can be used to synchronize access to a bounded buffer.**

It is similar to question 20. You have two sempahores, one called ``empty``, which represents how many empty slots there are in the buffer, and the other one called ``data`` which represents how any slots have data in it. ``empty`` should be initialized to the buffer size, and ``data`` to 0.

Before a producer inserts an item, it should wait for ``empty``, to make sure it is above 0. When it has inserted an item, it should signal ``data``, to make sure the consumer knows it can read.

Before a consumer removes an item, it should wait for ``data``, to make sure it is above 0. When it has removed an item, it should signal ``empty``, to make sure the producer knows there are at least one spot in the buffer.

Also, a mutex lock should be used before insert/removing an item.

#### Banker’s algorithm
**23. Is Banker’s algorithm an example of deadlock prevention or deadlock avoidance? Justify your answer.**

Banker's algorithm is an example of deadlock avoidance, as it makes sure a deadlock never can happen.

**24. Consider a system with four tasks T0, T1, T2, T3 and four resources A, B, C, D. The initial state S0 for Banker’s algorithm is defined by:**

```java
     Allocation            Max
     ┌ 1 2 0 2 ┐       ┌ 2 2 2 4 ┐        Available
     | 0 1 1 1 |       | 2 2 4 3 |       [ 2 1 3 1 ]
     | 1 0 0 1 |       | 2 1 2 1 |
     └ 2 0 1 0 ┘       └ 3 3 4 5 ┘
```

**Calculate the ``Allocation`` and ``Need`` matrices and the ``Available`` vector for the new state S1 after T1 makes a request for one more instance of the resource C and one more instance of resource D. Determine if S1 is safe by running the safety algorithm step by step, show your calculations in the below table.**

##### Fuffes uträkning:
```
  Allocation            Need
     ┌ 1 2 0 2 ┐       ┌ 1 0 2 2 ┐        Available
     | 0 1 2 2 |       | 2 1 2 1 |       [ 2 1 2 0 ]
     | 1 0 0 1 |       | 1 1 2 0 |
     └ 2 0 1 0 ┘       └ 1 3 3 5 ┘

     1. Work = [2 1 2 0] Finish = [F F F F]
     2. Need_T2 = [1 1 2 0] < [2 1 2 0]
     3. Work = [1 0 0 1] + [2 1 2 0] = [3 1 2 1] Finish = [F F T F]
     2. Need_T1 = [2 1 2 1] < [3 1 2 1]
     3. Work = [0 1 2 2] + [3 1 2 1] = [3 2 4 3] Finish = [F T T F]
     2. Need_T0 = [1 0 2 2] < [3 2 4 3]
     3. Work = [1 2 0 2] + [3 2 4 3] = [4 4 4 5] Finish = [T T T F]
     2. Need_T3 = [1 3 3 5] < [4 4 4 5]
     3. Work = [2 0 1 0] + [4 4 4 5] ? [6 4 5 5] Finish = [T T T T]
     2. GOTO 4
     4. Finish = [T T T T] => Safe state
```

##### Farres räkneskapsberäkningskalkyler:

```java
LEGEND:
Sx = State X
Tx = Task X

Before Request(T1): // State 0

   Allocation            Max              Need
T0 ┌ 1 2 0 2 ┐       ┌ 2 2 2 4 ┐       ┌ 1 0 2 2 ┐       Available
T1 | 0 1 1 1 |       | 2 2 4 3 |       | 2 1 3 2 |      [ 2 1 3 1 ]
T2 | 1 0 0 1 |       | 2 1 2 1 |       | 1 1 2 0 |
T3 └ 2 0 1 0 ┘       └ 3 3 4 5 ┘       └ 1 3 3 5 ┘

Request(T1) = (0, 0, 1, 1)

1. Request(T1) <= Need(T1, S0)?
  (0, 0, 1, 1) <= (2, 1, 3, 2)   OK!

2. Request(T1) <= Available(S0)?
  (0, 0, 1, 1) <= (2, 1, 3 ,1)   OK!

3. Calculate shit, son

i)   Need(T1, S1)       = Need(T1, S0) - Request(T1)
                        = (2, 1, 3, 2) - (0, 0, 1, 1)
                        = (2, 1, 2, 1)

ii)  Allocation(T1, S1) = Allocation(T1, S0) + Request(T1)
                        = (0, 1, 1, 1) + (0, 0, 1, 1)
                        = (0, 1, 2, 2)

iii) Available(S1)      = Available(S0) - Request(T1)
                        = (2, 1, 3, 1) - (0, 0, 1, 1)
                        = (2, 1, 2, 0)

After Request(T1): // State 1

    Allocation            Max              Need
T0 ┌ 1 2 0 2 ┐       ┌ 2 2 2 4 ┐       ┌ 1 0 2 2 ┐       Available
T1 | 0 1 2 2 |       | 2 2 4 3 |       | 2 1 2 1 |      [ 2 1 2 0 ]
T2 | 1 0 0 1 |       | 2 1 2 1 |       | 1 1 2 0 |
T3 └ 2 0 1 0 ┘       └ 3 3 4 5 ┘       └ 1 3 3 5 ┘


Now, let us do the Safety Dance™!

|      |   Available   |        |
| Step | A | B | C | D | Choice |
| ---- | --|---|---|---|--------|
| 1    | 2 | 1 | 2 | 0 |   T1   | Available(1) = Available(S0) - Request(T1)
| 2    | 2 | 2 | 4 | 2 |   T2   | Available(2) = Available(1) + Allocation(T1, S1)
| 3    | 3 | 2 | 4 | 3 |   T0   | Available(3) = Available(2) + Allocation(T2, S1)
| 4    | 4 | 4 | 4 | 5 |   T3   | Available(4) = Available(3) + Allocation(T0, S1)
| 5    | 6 | 4 | 5 | 5 |   --   | Available(5) = Available(4) + Allocation(T3, S1)

Available(step) = Available(step) + Allocation(task, state)

```

| Step | A | B | C | D | Choice |
| ---- | --|---|---|---|--------|
| 1    | 2 | 1 | 2 | 0 |   T1   |
| 2    | 2 | 2 | 4 | 2 |   T2   |
| 3    | 3 | 2 | 4 | 3 |   T0   |
| 4    | 4 | 4 | 4 | 5 |   T3   |
| 5    | 6 | 4 | 5 | 5 |   --   |

#### Priority inversion
**25. Use a figure to explain what is meant by priority inversion.**

**26. Explain how priority inheritance solves the problem with priority inversion.**

When a task blocks a high priority task it inherites the priority of the task it blocks, thus it cannot be preempted by a task of lower priority than the task it blocks.
