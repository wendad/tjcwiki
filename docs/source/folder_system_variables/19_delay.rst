delay-延时
===============================================================



delay=10   (让设备停顿10ms)

低于50ms时可以使用delay，超过50ms时建议用定时器来延时

.. attention:: 执行延时指令后，设备CPU不会执行任何指令，但是会继续接受串口指令保存到串口指令缓存区。

