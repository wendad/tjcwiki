pio0~pio7-扩展IO端口
===============================================================


(仅x5 k0系列才支持)

pio4=1        (IO4置为1)

n0.val=pio2 (io2的电平状态赋值给n0.val)

covx pio3,t0.txt,0,0 (io3的电平状态转换给t0.txt)

.. attention:: 
   1.使用pio端口之前一定要先使用cfgpio指令配置好IO模式。

   2.上电默认所有扩展IO模式为上拉输入（内部上拉电阻为50K）。
