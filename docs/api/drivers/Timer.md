## Timer

<span class="images">![](https://os.mbed.com/docs/v5.10/mbed-os-api-doxy/classmbed_1_1_timer.png)<span>Timer class hierarchy</span></span>

Use the Timer interface to create, start, stop and read a timer for measuring small times (between microseconds and seconds).

You can independently create, start and stop any number of Timer objects.

<span class="notes">**Note:** Timers are based on 32-bit int microsecond counters, so they can only time up to a maximum of 2^31-1 microseconds (30 minutes). They are designed for times between microseconds and seconds. For longer times, use the `time()` real time clock. </span>

### Timer class reference

[![View code](https://www.mbed.com/embed/?type=library)](https://os.mbed.com/docs/v5.10/mbed-os-api-doxy/classmbed_1_1_timer.html)

### Timer hello, world

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/Timer_HelloWorld/)](https://os.mbed.com/teams/mbed_example/code/Timer_HelloWorld/file/0d21eea06da7/main.cpp)

### Related content

- [Office Hours video about low power, tickless and sleep](https://youtu.be/OFfOlBaegdg?t=669).
