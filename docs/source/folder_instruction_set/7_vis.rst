vis-隐藏/显示控件
===============================================================


vis obj,state

obj:控件名称或控件ID

state:状态(0或1)

实例1:vis b0,0 (隐藏b0控件) 实例2:vis b0,1 (显示b0控件)

实例3: vis 1,0 (隐藏ID为1的控件) 实例4: vis 1,1 (显示ID为1的控件)

备注：

第一个参数 为255表示 当前页面所有控件，例:vis 255,0(隐藏当前页面所有控件) vis 255,1(显示当前页面所有控件)。
