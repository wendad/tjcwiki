addr-设备地址
===============================================================



字符串写法:addr=256

HEX写法:addr=0x0100

以上两条写法是同一个意思，配置的是同一个地址，配置之后有断电保存功能。

.. attention:: 
   1.有效地址范围为256-2815

   (即0x0100-0x0aff),0为无地址,65535为广播地址，广播地址只能用于广播数据，不能配置某个设备为广播地址，出厂默认地址为0,即没有地址。

   2.向一个有地址的设备发送指令时，需要在指令前加上2字节的地址数据，以hex方式发送,2字节小端模式,比如设备配置的地址为addr=256,那么发送给他指令时需要在指令前面增加两个字节:0x00 0x01(注意，配置的时候是0x0100,发送指令的时候是低位在前，所以是0x00 0x01跟配置的写法是相反的)。

   3.该配置只能在实物上有效，模拟器是无法测试的。
