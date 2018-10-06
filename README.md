# Thread-Local-Storage
Implement local storage for threads leveraging the pthread library

# Goal
Develop local storage for threads by leveraging the pthread library in C. The following are functions to be applied in the thread local storage library:
* Create thread local storage
* Read and write to tls
* Delete the LSA
* Clone the local storage area

# Notes

* Utilize Semaphores to solve critical section problems and to achieve process synchronization while multi-threading
* Page fault handeling - if a thread trys to access LSA of another thread then that thread will terminate o/w the SIGSEGV signal will be reraised
* Copy on Write - this is methodology used for cloning. If LSA is cloned then the clone will point to the same pages as original unless a write occurs then those pages are copied
* Allocation of memory using mman library
* mman lib used to disable reading and writing via mprotect function
