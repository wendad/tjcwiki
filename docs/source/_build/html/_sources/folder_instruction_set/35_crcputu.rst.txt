crcputu-crc校验一段串口缓冲区数据(recmod=1时有效)
===============================================================

crcputu star,length

star:串口缓冲区数据起始位

length:需要校验的数据长度

实例1:crcputu 0,22           (校验串口缓冲区的前面22个字节，recmod=1时有效) 

备注：

1.使用crcputs或crcputh或crcputu校验指定数据,检验完毕读取系统变量crcval获得校验结果。

2.完整的CRC校验实例代码请参考:程序中使用CRC校验数据