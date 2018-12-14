## SlicingBlockDevice

<span class="images">![](https://os.mbed.com/docs/development/mbed-os-api-doxy/class_slicing_block_device.png)<span>SlicingBlockDevice class hierarchy</span></span>

The SlicingBlockDevice class provides a way to break up a block device into subunits without the need to manually track offsets. The SlicingBlockDevice acts as an opposite of the [ChainingBlockDevice](chainingblockdevice.html) class.

The constructor takes in the master block device pointer and the start and end addresses of where you would like to partition the sub-block. By not specifying the end address, you create a block device that spans from the provided start address to the end of the underlying block device.

  - _bd_ -  Block device to back the SlicingBlockDevice.
  - _start_ - Start block address to map to block 0. Negative addresses are calculated from the end of the underlying block device.
  - _end_ - End block address to mark the end of the block device. This block is not mapped; negative addresses are calculated from the end of the underlying block device.

To configure this class, please see our [BlockDevice configuration documentation](../reference/configuration-storage.html#blockdevice-default-configuration).

### SlicingBlockDevice class reference

[![View code](https://www.mbed.com/embed/?type=library)](https://os.mbed.com/docs/development/mbed-os-api-doxy/_slicing_block_device_8h_source.html)

### SlicingBlockDevice example

This SlicingBlockDevice example partitions a [HeapBlockDevice](heapblockdevice.html) into three subunits and showcases programming and reading back data segments through both the underlying master block device and the sliced subunits.

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/SlicingBlockDevice_ex_1/)](https://os.mbed.com/teams/mbed_example/code/SlicingBlockDevice_ex_1/file/62c01cd06ff7/main.cpp)

### Related content

- [ChainingBlockDevice](chainingblockdevice.html) API reference.
- [HeapBlockDevice](heapblockdevice.html) API reference.
- [BlockDevice configuration documentation](../reference/configuration-storage.html#blockdevice-default-configuration).
