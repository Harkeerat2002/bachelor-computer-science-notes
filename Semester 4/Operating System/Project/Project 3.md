# Task
## 2.2.3 Priority Scheduling
### First Task:
Implement priority scheduling in Pintos. When a thread is added to the ready list that has a higher priority than the currently running thread, the current thread should immediately yield the processor to the new thread. Similarly, when threads are waiting for a lock, semaphore, or condition variable, the highest priority waiting thread should be awakened first. A thread may raise or lower its own priority at any time, but lowering its priority such that it no longer has the highest priority must cause it to immediately yield the CPU.
#### priority scheduling:
Thread priorities range from `PRI_MIN (0)` to `PRI_MAX (63)`. Lower numbers correspond to lower priorities, so that priority 0 is the lowest priority and priority 63 is the highest. The initial thread priority is passed as an argument to thread_create(). If there’s no reason to choose another priority, use `PRI_DEFAULT (31)`. The PRI_ macros are defined in ‘threads/thread.h’, and you should not change their values.
# Methods Implemented
## `thread.c`
- `under_priortize(struct list_elem *a, struct list_elem *b, void *aux)`
	This is looks at **a** and **b** and compares them to compares their priority. It sees if a has a less priority than b, and if it does then it returns true, otherwise it would return false.
- `latest_cpu()`
	Uses the FP Real to find to get the latest CPU, which can be influenced by the niceness and changes that.
- `update_priority()`
	It updates the priority with the help of FPR and uses the formula to calculate the priority for it.
- Edited `thread_tick()`
	Every time it ticks it would check to see if the thread_mlfqs is enabled by the OS. If it is enabled then it would increase the recent_cpu, and then would get the numbers of thread ready to run, calculate the average_load and then for each thread it would get the latest_cpu.Afterwards,s for each 4 ticks it would also update the priority for each thread. 
- Edited `thread_create()`
	Every time a thread is created it would also add the following variables to it:
	-> sleep_for
	-> nice
	-> recent_cpu
	Then it would check if thread_mlfqs is enabled. If it is enabled,d then would call the yielding function
- `yielding()`
	Gets the current thread priority and the thread with the highest priority in the ready list. It would then see, then see that if the current thread priority is less than the one in the list. If it iis,then it would be yielded, otherwise it would continue. 
- Edited `thread_set_priority()`
- `thread_set_nice()`
- `thread_get_nice()`
- `thread_get_recent_cpu()`
- Edited `next_thread_to_run()`
- `thread_block_until()`
- `thread_wake_up()`
# Code Description
