4.与arduino mega联调
================================================================

arduino代码如下

.. code-block:: c++
   :emphasize-lines: 0
   :linenos:

    //arduino的GND接串口工具的GND,共地
    //arduino的TX3接串口工具的RX
    //arduino的RX3接串口工具的TX
    //根据自己的实际改为对应的串口,我这里接的是TX3和RX3
    #define TJC Serial3

    int a;
    unsigned long nowtime;
    void setup() {
        // put your setup code here, to run once:
        //初始化串口
        TJC.begin(115200);

        //因为串口屏开机会发送88 ff ff ff,所以要清空串口缓冲区
        while (TJC.read() >= 0); //清空串口缓冲区
        TJC.print("page main\xff\xff\xff"); //发送命令让屏幕跳转到main页面
        nowtime = millis(); //获取当前已经运行的时间
    }

    void loop() {
        // put your main code here, to run repeatedly:
        char str[100];
        if (millis() >= nowtime + 1000) {
            nowtime = millis(); //获取当前已经运行的时间

            //用sprintf来格式化字符串，给n0的val属性赋值
            sprintf(str, "n0.val=%d\xff\xff\xff", a);
            //把字符串发送出去
            TJC.print(str);

            //用sprintf来格式化字符串，给t0的txt属性赋值
            sprintf(str, "t0.txt=\"现在是%d\"\xff\xff\xff", a);
            //把字符串发送出去
            TJC.print(str);


            //用sprintf来格式化字符串，触发b0的按下事件,直接把结束符整合在字符串中
            sprintf(str, "click b0,1\xff\xff\xff");
            //把字符串发送出去
            TJC.print(str);

            delay(50);  //延时50ms,才能看清楚点击效果

            //用sprintf来格式化字符串，触发b0的弹起事件,直接把结束符整合在字符串中
            sprintf(str, "click b0,0\xff\xff\xff");
            //把字符串发送出去
            TJC.print(str);

            a++;
        }

    }
