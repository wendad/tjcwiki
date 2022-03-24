refile-重命名文件3
===============================================================

仅X3,X5系列支持

refile srcfilepath,decfilepath

srcfilepath:源文件路径

decfilepath:目标文件路径

实例:refile "ram/0.jpg","ram/1.jpg"  (将内存文件系统中的0.jpg更名为1.jpg)

实例:refile "sd0/a.jpg","sd0/b.jpg"  (将SD卡根目录中的a.jpg更名为b.jpg)

备注：

要使用内存文件系统必须先在工程配置选项中配置内存文件系统的大小，新建工程默认内存文件系统大小为0，即不可能使用。