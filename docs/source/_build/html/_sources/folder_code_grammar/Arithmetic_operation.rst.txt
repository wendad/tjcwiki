二、【运算操作】
===============================================================

.. attention:: 所有运算不支持乘除法优先，也不支持括号优先级，统一从左到右的顺序，请特别注意。

   所有的运算操作可以在上位编辑状态下写入控件事件中，也可以串口传输过来(串口传输记得加三个0xff的结束符)

   所有的运算操作都不支持多余空格，添加进任何空格，编译都会报错

▶数值类型变量运算操作

支持的运算符：+  -  *  /  %   &  |  ^  <<  >>

.. code-block:: c#
   :caption: 正确的运算操作
   :name: test6
   :emphasize-lines: 0
   :linenos:

   n0.val=n0.val+n1.val+2
   n0.val++
   n0.val+=2
   n0.val=n1.val%3
   n0.val=h0.val*10
   n0.val*=10
   n0.val=n1.val&3
   n0.val=n1.val^5



.. code-block:: sh
   :caption: 以下为错误的运算写法
   :name: test7
   :emphasize-lines: 0
   :linenos:

   n0.val=t0.txt+1          错误原因：数值类型的变量必须跟数值类型的变量做运算，并赋值给数值类型的变量
   n0.val=1+"2"             错误原因：数值类型的变量必须跟数值类型的变量做运算，并赋值给数值类型的变量

注意:当数字控件的最高位为1时(即负数),进行右移操作时,最高位将补1,例如0x80000000>>31后变为0xFFFFFFFF而不是0x01





字符串类型变量运算操作

运算符 "+"

.. code-block:: c#
   :caption: 字符串拼接
   :name: test8
   :emphasize-lines: 0
   :linenos:

   t0.txt="1"+"2"
   t0.txt=t0.txt+t1.txt
   t0.txt+="abc"+"xy"


.. code-block:: sh
   :caption: 以下为错误的运算写法
   :name: test9
   :emphasize-lines: 0
   :linenos:

   t0.txt=1+2                 错误原因：1和2都是数值常量 字符串类型的变量只能跟字符串常量/变量相加，不能跟一个数值常量/变量相加
   t0.txt=t0.txt+h0.val    错误原因：h0.val是数值变量,不能跟字符串变量相加



运算符 "-"

.. code-block:: sh
   :caption: 字符串删除
   :name: test10
   :emphasize-lines: 0
   :linenos:

   t0.txt=t0.txt-1    删除t0.txt最后1个字符
   t0.txt=t0.txt-3    删除t0.txt最后3个字符
   t0.txt-=n0.val     删除t0.txt最后n0.val个字符

在字符串变量运算中，"-"代表删除的意思,所以用"-"的时候，字符串变量必须"-"一个数值常量/变量来表示删除多少个字符，这里跟用"+"是不一样的。用"+"的时候必须是字符串+字符串；用"-"的时候必须是字符串-数值。
