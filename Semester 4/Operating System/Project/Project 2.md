# Task
Reimplement `timer_sleep()`, defined in ‘devices/timer.c’. Although a working implementation is provided, it “busy waits,” that is, it spins in a loop checking the current time
and calling `thread_yield()` until enough time has gone by. Reimplement it to avoid busy waiting.
# Pintos Documentation Notes
## 2.1 Background
### 2.1.1 Understanding Threads
- When a thread is created, you are creating a new context to be scheduled. 
- You provide a function to be run in this context as an argument to `thread_create()`. 
- The first time the thread is scheduled and runs, it starts from the beginning of that function and executes in that context. 
- When the function returns, the thread terminates.
- Each thread, therefore, acts like a mini-program running inside Pintos, with the function passed to `thread-create()` acting like `main()`.

### 2.1.2 Source Files
`thread.c` and `thread.h` :
	Basic thread support. Much of your work will take place in these files.
	‘thread.h’ defines struct thread, which you are likely to modify in all four
	projects.
`timer.c` and `timer.h` :
	System timer that ticks, by default, 100 times per second. You will modify this
	code in this project.

## A.2 Threads
`enum thread_status status`
The thread's state, one of the following:
**THREAD_RUNNING**
	The thread is running. Exactly one thread is running at a given time. `thread_current()` returns the running thread.
**THREAD_READY**
	The thread is ready to run, but it’s not running right now. The thread could be selected to run the next time the scheduler is invoked. Ready threads are kept in a doubly linked list called ready_list.
**THREAD_BLOCKED**
	The thread is waiting for something, e.g. a lock to become available, an interrupt to be invoked. The thread won’t be scheduled again until it transitions to	the THREAD_READY state with a call to `thread_unblock()`. This is most conveniently done indirectly, using one of the Pintos synchronization primitives that block and unblock threads automatically
**THREAD_DYING**
	The thread will be destroyed by the scheduler after switching to the next thread.

# Code Description
## Methods Implemented:
### `thread.c`:
```c++
/*
* Blocks a thred and sets the wakeUpTick of the current thread to the pased in * * * parameter
*/
void
our_tsleep
(int64_t wakinguptick) {
	// Interupt
	enum intr_level prev = intr_disable();
	struct thread * curr = thread_current();
	curr->wakeUpTick = wakinguptick;
	list_push_back(&tlist, &curr->elem);
	thread_block();
	intr_set_level(prev);
}

/*
* Scans the sleeping list, and checks if the timer has expired or not. If it has * * then it unblocks it and removes it from the list
*/
void
scan_tsleep() {
	enum intr_level prev = intr_disable();
	struct list_elem *begin = list_begin(&tlist);
	int64_t current = timer_ticks();  
	
	while (begin != list_end(&tlist)) {
		struct thread *t = list_entry(begin,struct thread, elem);
		struct list_elem * next = list_next (begin);
		if (current >= t->wakeUpTick) {
			list_remove(begin);
			thread_unblock(t);
		}
		begin = next;
	} 
	
	intr_set_level(prev);
}
```
#### Each line Explanation
`our_tsleep()`
```c++
// It turns the interrupts off, and equates prev to the previouse interrupt state.
enum intr_level prev = intr_disable();

// Equates curr to the current thread.
struct thread * curr = thread_current();

// Equates current threads wakeUpTick to the wake up tick from the parameter, which // came from timer_sleep()
curr->wakeUpTick = wakinguptick;

// Adds the current threads element to the list and pushes it back there.
list_push_back(&tlist, &curr->elem);

// Takes the current thread and puts it to sleep.
thread_block();

// Turns the interupt on for the prevuouse interrupt state.
intr_set_level(prev);
```

`scan_tsleep()`
```cpp
// It turns the interrupts off, and equates prev to the previouse interrupt state.
enum intr_level prev = intr_disable();

// Gets the first thread from the list_elem
struct list_elem *begin = list_begin(&tlist);

// Gets the current number of ticks since OS started
int64_t current = timer_ticks();  

// Checks to see if the begin doesnt equal to the list_end... 
while (begin != list_end(&tlist)) {
	//
	struct thread *t = list_entry(begin,struct thread, elem);
	struct list_elem * next = list_next (begin);

	// Checks to see if the wakeUptick which is the ticks it was supposed to sleep for is less that the current ticks
	if (current >= t->wakeUpTick) {
		// If it is then it would remove the first element of the list.
		list_remove(begin);
		// It would also unblock the thread which was sleeping.
		thread_unblock(t);
	}
	// Begin wuld then equal to the next.
	begin = next;
} 

// Turns the interupt on for the prevuouse interrupt state.
intr_set_level(prev);
```
### `timer.c`:
```cpp
/* Sleeps for approximately TICKS timer ticks. Interrupts must be turned on. */
void
timer_sleep (int64_t ticks)
{
	int64_t start = timer_ticks(); 
	ASSERT (intr_get_level () == INTR_ON);
	our_tsleep(ticks + start);
}
```
#### Each line Explanation
`timer_sleep()`
```c++
// Equates start with the number time ticks since OS booted
int64_t start = timer_ticks(); 

// Compares the intr_get_level() with INTR_ON, was already there. 
ASSERT (intr_get_level () == INTR_ON);

// Line changed to our own implementation, calls a method from thread.c which takes 
// int64_t as to at what time the thread should come back from sleep
our_tsleep(ticks + start);
```

### Other Methods Used in this project
**`intr_disable()`:**
	Turns interrupts off, returns the previous interrupt state.
**`intr_set_level(prev)`**
	Turn interrupts on or off according to level. Returns the previous interrupt state.

**`list_push_back():`**
	Insert ELEM at the end of the list, so that it becomes the back in the LIST.
**`list_begin():`**
	Returns the beginning of LIST
**`list_end():`**
	Returns the end of LIST

**`timer_ticks():`**
	Returns the number of timer ticks since the OS booted

**`thread_tick():`**
	Called by the timer interrupt at each timer tick. It keeps track of thread statistics
	and triggers the scheduler when a time slice expires. Also called `scan_tsleep()` every time as well whenever the tick is increased to check if the timer has expired or not.

# Doubts in Project 2
1. What is `tlist`?