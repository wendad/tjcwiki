9.编译报错：XXX初始值无效
============================================================

1.字库ID无效错误
------------------------------------

出现这类错误是因为：控件使用了字库。但是字库资源中不存在这个字库。解决办法是添加一个字库文件到字库资源中，并修改控件的字库属性对应到指定的字库ID。

如何制作字库和添加字库，请参阅文档：开发环境详解->字库



2.图片ID无效错误
------------------------------------

出现这类错误是因为：选择了页面/控件背景为图片，但是图片资源中又不存在这个ID的图片。解决办法是添加对应的图片文件到图片资源中，并修改控件的图片属性对应到指定的图片ID。
