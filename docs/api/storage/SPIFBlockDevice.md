## SPI Flash block device

<span class="images">![](https://os.mbed.com/docs/development/mbed-os-api-doxy/class_s_p_i_f_block_device.png)<span>SPIFBlockDevice class hierarchy</span></span>

This API is a block device for NOR-based SPI flash devices that support SFDP.

NOR-based SPI flash supports byte-sized read and writes, with an erase size of around 4 kbytes. An erase sets a block to all 1s, with successive writes clearing set bits.

To configure this class, please see our [BlockDevice configuration documentation](../reference/configuration-storage.html#blockdevice-default-configuration).

### SPIFBlockDevice class reference

[![View code](https://www.mbed.com/embed/?type=library)](https://os.mbed.com/docs/development/mbed-os-api-doxy/class_s_p_i_f_block_device.html)

### SPIFBlockDevice example

``` cpp TODO
// Here's an example using the MX25R SPI flash device on the K82F
#include "mbed.h"
#include "SPIFBlockDevice.h"

// Create flash device on SPI bus with PTE5 as chip select
SPIFBlockDevice spif(PTE2, PTE4, PTE1, PTE5);

int main() {
    printf("spif test\n");

    // Initialize the SPI flash device and print the memory layout
    spif.init();
    printf("spif size: %llu\n",         spif.size());
    printf("spif read size: %llu\n",    spif.get_read_size());
    printf("spif program size: %llu\n", spif.get_program_size());
    printf("spif erase size: %llu\n",   spif.get_erase_size());

    // Write "Hello World!" to the first block
    char *buffer = (char*)malloc(spif.get_erase_size());
    sprintf(buffer, "Hello World!\n");
    spif.erase(0, spif.get_erase_size());
    spif.program(buffer, 0, spif.get_erase_size());

    // Read back what was stored
    spif.read(buffer, 0, spif.get_erase_size());
    printf("%s", buffer);

    // Deinitialize the device
    spif.deinit();
}
```

### Related content

- [BlockDevice configuration documentation](../reference/configuration-storage.html#blockdevice-default-configuration).
