## Kernel interface functions

The Kernel namespace implements functions to read RTOS information. Currently it implements one function to read the current RTOS kernel millisecond tick count.

### Kernel namespace reference

[![View code](https://www.mbed.com/embed/?type=library)](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespacertos_1_1_kernel.html)

### `get_ms_count()` example

Kernel implements one function named `get_ms_count()` to read the current RTOS kernel millisecond tick count. The below code snippet demonstrates use of the `get_ms_count()` function to calculate the elapsed time:

```
void send_data()
{
    // 64-bit time doesn't wrap for half a billion years, at least
    uint64_t now = Kernel::get_ms_count();
    //do some operations
    // ...

    uint64_t later = Kernel::get_ms_count();

    //calculate millisecs elapsed
    uint64_t elapsed_ms = later - now;
}
```
