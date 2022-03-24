crcputs-crc校验一个变量/常量
===============================================================

crcputs att,length

att:变量名称

length:需要校验的数据长度(0为自动长度)

实例1:crcputs t0.txt,0   (CRC校验字符串变量t0.txt)

实例2:crcputs "abc",0    (CRC校验字符串常量"abc")

备注：

1.使用crcputs或crcputh或crcputu校验指定数据,检验完毕读取系统变量crcval获得校验结果。

2.完整的CRC校验实例代码请参考:程序中使用CRC校验数据