> whereis: 命令用来定位指令的二进制程序、源代码文件和man手册页等相关文件的路径。

`whereis`命令只能用于程序名的搜索，而且`只搜索二进制文件（参数-b）、man说明文件（参数-m）和源代码文件（参数-s）`。如果省略参数，则返回所有信息。

和find相比，whereis查找的速度非常快，这是因为linux系统会将 系统内的所有文件都记录在一个数据库文件中，当使用whereis和下面即将介绍的locate时，会从数据库中查找数据，而不是像find命令那样，通 过遍历硬盘来查找，效率自然会很高。 但是该数据库文件并不是实时更新，**默认情况下时一星期更新一次，因此，我们在用whereis和locate 查找文件时，有时会找到已经被删除的数据，或者刚刚建立文件，却无法查找到，原因就是因为数据库文件没有被更新**。


语法
```
whereis(选项)(参数)
```
选项
```
-b：只查找二进制文件；
-B<目录>：只在设置的目录下查找二进制文件；
-f：不显示文件名前的路径名称；
-m：只查找说明文件；
-M<目录>：只在设置的目录下查找说明文件；
-s：只查找原始代码文件；
-S<目录>只在设置的目录下查找原始代码文件；
-u：查找不包含指定类型的文件。
```


> which命令用于查找并显示给定命令的绝对路径，环境变量PATH中保存了查找命令时需要遍历的目录。which指令会在环境变量$PATH设置的目录里查找符合条件的文件。也就是说，使用which命令，就可以看到某个系统命令是否存在，以及执行的到底是哪一个位置的命令。


语法
```
which(选项)(参数)
```
选项
```
-n<文件名长度>：制定文件名长度，指定的长度必须大于或等于所有文件中最长的文件名；
-p<文件名长度>：与-n参数相同，但此处的<文件名长度>包含了文件的路径；
-w：指定输出时栏位的宽度；
-V：显示版本信息。
```