一、【赋值操作】
===============================================================

所有的赋值操作可以在上位编辑状态下写入控件事件中，也可以串口传输过来(串口传输记得加三个0xff的结束符)


.. warning:: 所有的赋值操作都不支持多余空格，添加进任何空格，编译都会报错



.. code-block:: sh
   :caption: 字符串属性赋值
   :name: test1
   :emphasize-lines: 0
   :linenos:

   t0.txt="123"     给t0控件的txt属性赋值"123"
   t0.txt=t1.txt    把t1控件的txt属性赋值给t0控件的txt属性


.. tip:: t0控件的txt属性为字符串类型，字符串类型的属性赋值常量必须加双引号

.. code-block:: c#
   :caption: 字符串赋值写法
   :name: test2
   :emphasize-lines: 2
   :linenos:

   t0.txt=123  //错误
   t0.txt="123"  //正确

.. tip:: val和txt属性相互转换不能直接赋值，需要使用covx进行转换

.. code-block:: c#
   :caption: val和txt属性相互转换
   :name: test3
   :emphasize-lines: 2,4
   :linenos:

   t0.txt=h0.val     //错误      
   covx h0.val,t0.txt,0,0  //正确
   n0.val=t0.txt     //错误      
   covx t0.txt,n0.val,0,0  //正确

▶数值属性赋值

.. code-block:: sh
   :caption: val和txt属性相互转换
   :name: test4
   :emphasize-lines: 0
   :linenos:

   n0.val=123      给n0控件的val属性赋值123
   n0.val=h0.val   把h0控件的val属性赋值给n0控件的val属性
   dim=80          给系统变量dim赋值80（背光亮度立即变为80亮度）
   baud=115200     给系统变量baud赋值115200(屏幕波特率立即变为115200)
   n0.val=baud     把屏幕当前的波特率系统变量赋值给n0控件的val属性

以下为错误的赋值写法:

.. code-block:: sh
   :caption: val和txt属性相互转换
   :name: test5
   :emphasize-lines: 0
   :linenos:

   n0.val="123"         错误原因：n0控件的val属性为数值类型，数值类型的属性赋值常量不应该有双引号
   n0.val=t0.txt         错误原因：t0控件的txt属性是字符串类型，不能赋值给数值类型的属性


温馨提示:

1.txt、path、dir属性是字符串类型，其他属性一般都是数值类型。

2.字符串类型和数值类型可以通过covx指令来实现相互转换赋值，具体请参看基本指令集中的covx指令说明。