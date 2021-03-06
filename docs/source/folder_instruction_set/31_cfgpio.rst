cfgpio-扩展IO模式配置
===============================================================

(仅k0 x5系列支持)

cfgpio id,state,obj

id:扩展IO的序号

state:配置模式(0-上拉输入模式,1-控件事件邦定输入模式,2-推挽输出模式,3-PWM输出模式,4-开漏模式)

obj:绑定控件名称或ID(此参数仅在配置为控件事件邦定输入模式下有效，其他模式下无效)

实例1:cfgpio 0,0,0  (将io0配置为上拉输入，配置为此模式后，任意时刻可以使用系统变量pio0读取当前输入电平,如:n0.val=pio0)

实例2:cfgpio 1,2,0  (将io1配置为推挽输出,配置为此模式后，任意时刻可以使用系统变量pio1控制当前输出电平，如:pio1=1)

实例3:cfgpio 2,1,b0 (将io2配置为控件事件邦定输入，邦定控件为b0,配置为此模式后，io2产生下降沿的时候将触发b0控件的按下事件，产生上升沿的时候将触发b0控件的弹起事件)

实例4:cfgpio 4,3,0 (将io4配置为PWM输出模式，配置之前需要先设置占空比，即系统变量变量中的pwm4)

备注：

1.K0系列只有io4-io7才支持PWM输出，X5系列只有io7才支持PWM输出 其他IO不支持。配置其他IO为PWM模式会报错。

2.使用控件事件邦定输入模式时，必须是在当前配置时刻的当前页面的控件才能邦定，不可以邦定其他页面的控件（即使是全局内存占用的控件也不可以），邦定当前页面控件以后，当重新刷新页面或者切换到别的页面后，邦定事件将不会继续触发，因此每次刷新页面需要重新邦定，建议将邦定代码写在页面的前初始化事件中最为合适。

3.每个需要用到外部IO的页面，都必须在前初始化事件中重新配置一次需要用到的相关IO口