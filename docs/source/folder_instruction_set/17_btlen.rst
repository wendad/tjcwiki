btlen-字符串变量字节长度测试
===============================================================

btlen att0,att1

att0:需要测试的字符串变量

att1:把测试结果赋值给此变量

实例:btlen t0.txt,n0.val (把字符串变量t0.txt的实际字节长度赋值给n0.val)

备注:

1.btlen测试的是以字节为单位的长度，而strlen测试的是以字符为单位的长度，比如一个汉字用btlen测试出来的长度是2字节,用strlen测试出来的长度是1字符。

2.被测试的变量必须是字符串类型，写入的变量必须是数值类型，否则会报错。