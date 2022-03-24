四.程序中使用CRC校验数据
===============================================================

(1.60.1及其以上上位机版本支持)

1.以下代码将实现屏幕给外部设备发送2组常量数据，并在结尾带上Modbus的CRC16校验结果：

.. code-block:: c
   :emphasize-lines: 0
   :linenos:

   crcrest 1,0xffff              复位CRC
   crcputs "hex date is:",0      CRC校验字符串:hex date is:
   crcputh 03 25                 CRC校验hex:0x03,0x25
   prints "hex date is:",0       串口发送字符串:hex date is:
   printh 03 25                  串口发送hex:0x03,0x25
   prints crcval,2               串口发送校验结果


2.以下代码将实现屏幕给外部设备发送2组变量数据，并在结尾带上Modbus的CRC16校验结果：

.. code-block:: c
   :emphasize-lines: 0
   :linenos:

   crcrest 1,0xffff              复位CRC
   crcputs t0.txt,0              CRC校验字符串变量t0.txt
   crcputs n0.val,0              CRC校验数值变量n0.val
   prints t0.txt,0               串口发送字符串变量t0.txt
   prints n0.val,4               串口发送数值变量n0.val
   prints crcval,2               串口发送校验结果


3.以下代码将实现在主动解析模式下对串口缓冲区的数据进行CRC校验,并将成功与否的结果显示到t0.txt

.. code-block:: sh
   :emphasize-lines: 0
   :linenos:

   if(usize>=24)
   {
      crcrest 1,0xffff         复位CRC
      crcputu 0,22             校验串口缓冲区的前面22个字节
      sys0=0                   sys0是4字节的整形数据,CRC结果只有2字节，所以先给多余字节数据清零
      ucopy sys0,22,2,0        将接收缓冲区中接收到的CRC结果赋值给sys0
   if(sys0==crcval)校验通过
   {
      t0.txt="校验通过"
   }else
   {
      t0.txt="校验不通过"
   }
      udelete 24               删除已经处理的24字节
   }

