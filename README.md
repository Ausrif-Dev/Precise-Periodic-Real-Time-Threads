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

![alt text](https://github.com/Ausrif-Dev/Precise-Periodic-Real-Time-Threads/blob/35696883a56c144f2d47ecaa6e13cf1fddbb06ba/pthreadsudoRes.PNG?raw=true)

The temperature, pressure and display were displayed with 5 second interval subsequently as
stated using the “mytimer.tv_sec = seconds;” and “mytimer.tv_nsec = nanoseconds;” that gets
the value from a function call “timer_handler(TP_SEC, TP_NSEC);”.

The priority set for these threads are temperature>pressure>display. Therefore, the temperature and
pressure were able to be updated to new values before it is displayed. The PID for temperature,
pressure and display are as follows:

![alt text](https://github.com/Ausrif-Dev/Precise-Periodic-Real-Time-Threads/blob/35696883a56c144f2d47ecaa6e13cf1fddbb06ba/pthreadsudoRes2.PNG?raw=true)
![alt text](https://github.com/Ausrif-Dev/Precise-Periodic-Real-Time-Threads/blob/35696883a56c144f2d47ecaa6e13cf1fddbb06ba/pthreadsudoRes3.PNG?raw=true)
