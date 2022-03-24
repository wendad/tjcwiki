.. toctree::
   :maxdepth: 1

************************************
名称组使用说明
************************************


大多数情况下，我们操作控件属性是这样的(这也是我们推荐的控件操作方式)：

.. code-block:: sh
   :emphasize-lines: 0
   :linenos:

   t0.txt="123"     给t0控件的txt属性赋值"123"
   n0.val=15        给n0控件的val属性赋值15
   z0.val=185       给z0控件的val属性赋值185

假如我们不知道控件名字，只知道控件ID怎么操作呢？这就需要名称组来实现

控件名称组格式:  b[控件ID].属性

.. code-block:: sh
   :emphasize-lines: 0
   :linenos:

      b[5].txt="123"        当前页面ID为5的控件的txt属性赋值为"123"
      b[n0.val].txt="123"   当前页面ID为n0.val的控件的txt属性赋值为"123"

.. attention:: 必须确保当前页面的此控件具有txt属性,否则赋值会失败



页面名称组格式:p[页面DP号].b[控件ID号].属性


.. code-block:: sh
   :emphasize-lines: 0
   :linenos:

      p[2].b[4].txt="456"             ID为2的页面中，ID为4的控件的txt属性赋值为"456"
      p[n0.val].b[n1.val].txt="456"   ID为n0.val的页面中，ID为n1.val的控件的txt属性赋值为"456"

.. attention:: 必须确保此页面中的此控件具有txt属性,否则赋值会失败



配合for语句批量改变控件属性(将eeprom地址100开始连续的值加载到数值控件n0～n9(ID:5~14)):


.. code-block:: sh
   :emphasize-lines: 0
   :linenos:

      sys1=100                        设置eeprom读取位置
      for(sys0=n0.id;sys0<=n9.id;sys0++)     for循环读取eeprom并赋值给数值控件
      {
         repo b[sys0].val,sys1         读取指定位置的eeprom数据
         sys1+=4                       eeprom读取地址加4，因为一个数值类型占用4byte空间。
      }

.. attention:: 必须确保ID从5-14的控件都具有val属性,否则赋值会失败


配合for语句批量隐藏控件n0～n9(ID:5~14):


.. code-block:: sh
   :emphasize-lines: 0
   :linenos:

      
      for(sys0=n0.id;sys0<=n9.id;sys0++)     for循环读取eeprom并赋值给数值控件
      {
         vis b[sys0],0
      }





所有控件的ID号软件自动分配，不可手动设置，用户在编辑UI界面时，按顺序依次放置的控件，软件将连续分配ID。

使用快捷栏的“置顶”、“置底”功能会使控件ID发生变化，因为图层的前后关系是跟控件ID关联的，ID最小的在最底层(所以页面ID是0),ID最大的在最上层，每个控件都有自己的图层，全部是通过ID来区别前后关系的。







































































































































