get-带格式获取变量值/常量值
===============================================================

get att

att:变量名称

实例1:get t0.txt (返回控件t0的txt属性值)   实例2:get j0.val(返回控件j0的val属性值)

实例3:get “123”(返回常量字符串”123”)     实例4:get 123(返回常量数值：”123”)

备注：

1.使用get指令获取的变量为字符串类型时，返回的数据为0X70+字符串内码+结束符，如果是数值类型(如进度条的val属性)设备返回0X71+变量的4字节十六进制数据(int类型)+结束符。数值的存放模式为小端模式（即低位在前，高位在后）。

2.get指令可以由串口发送，也可以在上位软件编辑界写进用户代码中实现屏幕主动发送变量(主动发送的时候可以配合printh指令在前面加一段自定义标示来告诉单片机此变量是属于哪个控件的)。

3.get指令和print指令很类似,唯一的区别是get返回的数据带了起始标示符（0x70或0x71）和结束符(0xff 0xff 0xff)，而print没有。

4..数据具体返回格式请查看本表格后面的”串口HMI设备返回数据格式"。
