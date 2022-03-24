crcrest-复位crc初始值
===============================================================

crcrest crctype,initval

crctype:crc校验类型(必须为1,Modbus crc16校验方式)

initval:初始值(一般为0xffff)

实例1:crcrest 1,0xffff  (复位CRC初始值为0xffff，以便后续检验数据)

备注：

1.复位之后，可使用crcputs或crcputh或crcputu校验指定数据,检验完毕读取系统变量crcval获得校验结果。

2.完整的CRC校验实例代码请参考:程序中使用CRC校验数据