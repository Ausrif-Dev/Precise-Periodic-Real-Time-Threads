# Precise Periodic Real Time Threads
Simulate a system where temperature and pressure are continuously monitored and periodically displayed. 
Each aspect of the system runs in its own thread, with controlled access to shared resources using mutexes to ensure thread safety. 
This code also assigns priorities to the threads to manage their execution order and responsiveness.

![alt text](https://github.com/Ausrif-Dev/Precise-Periodic-Real-Time-Threads/blob/5c69b7843f960221132e972f871f01380cd4eac4/pthreadsudo1.PNG?raw=true)

The system was design to have only one core of CPU to make sure all
the threads can be run using a single processing core. Therefore, the threads won’t be separated
to multicore processes. The output on the left shows the PID on the “sudo ./pthread” which is
the running process. The output also prints the thread ID for the temperature, pressure, and
display.
