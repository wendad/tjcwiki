sleep-睡眠
===============================================================

sleep=0   (退出睡眠)

sleep=1   (进入睡眠)

.. attention:: 睡眠状态下可以执行如下指令：get,print, printh。 也可以 执行 sleep=1，wup=X 的赋值语句，并且支持上位软件联机，其他指令不会执行。如果是带扩展IO的硬件,IO配置为绑定控件事件时，睡眠模式下也不会产生中断事件。
