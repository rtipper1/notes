Scheduling processes within an operating system is a massive problem when designing an OS. There are two main types of scheduling being non-preemptive (sequential) and concurrent scheduling

___
## Non-Preemptive Scheduling
Processes execute sequentially, there is not concurrency inside the process and we must assume that the program ins single-threaded.

The main disadvantage of non-preemptive scheduling is that it could get stuck at an infinite loop.

___
## Concurrent Processes
Processes in a system can execute concurrently

This is ideal for ...
* Physical resource sharing (system utilization)
* Computational speed (multi core)
* Modularity
* Convenience (chrome, google drive, clock))

Before moving process to running OS sets a timer, if process yields/blocks, clear timer and go to scheduler, if the timer expires go to scheduler.