xstr-写字指令
===============================================================

xstr x,y,w,h,fontid,pointcolor,backcolor,xcenter,ycenter,sta,string

x:起始点坐标x；

y:起始点坐标y；

w:区域宽度；

h:区域高度；

fontid:字库ID；

pointcolor:字体颜色；

backcolor:背景色(sta设置为切图或图片时，backcolor表示图片ID);

xcenter:水平对齐方式(0为左对齐，1为居中，2为右对齐)；

ycenter: 垂直对齐方式(0为上对齐，1为居中，2为下对齐)；

sta:背景填充方式(0为切图，1为单色，2为图片，3为无背景,sta设置为切图或图片时，backcolor表示图片ID)

string:字符内容；

实例1:xstr 0,0,100,30,1,RED,BLACK,1,1,1,”中国”  

实例解释：使用字库1在起始坐标(0,0)，宽度100,高度30这个区域写出”中国”，字体色为RED，背景色为BLACK(如果不想写背景色(即无背景)可以设置sta参数为3),水平对齐方式为居中，垂直对齐方式也为居中。

备注：

1.字符写到超过设定的w以后将自动换行，如果换行到h之后还有剩下的字符没写完，将会被忽略。

2.关于颜色值的说明请参看cls指令的备注。