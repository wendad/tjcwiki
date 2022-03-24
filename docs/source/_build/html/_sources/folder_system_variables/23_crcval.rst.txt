crcval-crc校验结果
===============================================================

(只可获取不可设置,使用前请先用crcrest指令复位初始值）

n0.val=crcval    (当前CRC校验结果赋值给n0.val)

prints crcval,2  (当前CRC校验结果的低2位打印到串口)

.. attention:: 
   1.先使用crcrest复位CRC值，复位之后，可使用crcputs或crcputh或crcputu校验指定数据,检验完毕读取系统变量crcval获得校验结果)

   2.完整的CRC校验实例代码请参考:程序中使用CRC校验数据

