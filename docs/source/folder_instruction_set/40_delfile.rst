delfile-删除文件
===============================================================

仅X3,X5系列支持

delfile filepath

filepath:文件路径(例:"ram/0.jpg"或"sd0/1.jpg")

实例:delfile "ram/0.jpg"  (删除内存文件系统中的"0.jpg"文件)

实例:delfile "sd0/a.jpg"  (删除SD卡根目录中的"a.jpg"文件)

备注：

要使用内存文件系统必须先在工程配置选项中配置内存文件系统的大小，新建工程默认内存文件系统大小为0，即不可能使用。