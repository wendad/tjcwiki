rept-从用户存储区读取数据并透传发送到串口
===============================================================

(仅k0 x系列支持)

rept add,lenth

add: 用户存储区位置(从0开始)

lenth:读取并透传发送的长度

实例:rept 10,30  (从用户存储区的10位置读取30个字节并透传发送到串口)

备注：

不管存储区中的数据是字符串还是数值，设备都按16进制来读取和发送指定的字节数量到串口，并且不会发结束符。

用户存储区位置为0-1023。