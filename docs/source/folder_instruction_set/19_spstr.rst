spstr-字符串分割
===============================================================

spstr src,dec,key,index

src:源变量(必须是字符串变量)

dec:目标变量(必须是字符串变量)

key:分隔符字符串(必须是字符串变量)

index:取第几份(在src字符串中用key字符串做分割后，取第index份字符内容赋值给dec变量)

实例：data0.txt的d字符内容为:aaaa^bbbb^cccc^dddd

执行命令：spstr data0.txt,t0.txt,"^",2

运行结果：t0.txt内容为：cccc