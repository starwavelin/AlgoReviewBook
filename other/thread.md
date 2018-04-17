# Process, Threads, Single Thread

The overhead (代价) for thread is context switch, the overhead for process is Lock.  

One-thread, event loop, non-blocking IO can be used in Web Server, but this mode cannot be used for client-side web browsers, or Operating Systems.  

This is because, for OS, it must be multi-threaded cuz Users want to do different things at the same time. 分时  