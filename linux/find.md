> find : 搜索命令 



命令参数:

    pathname: find命令所查找的目录路径。例如用.来表示当前目录，用/来表示系统根目录。 

    -print： find命令将匹配的文件输出到标准输出。 

    ..


    命令选项:

    -name 按照文件名查询文件
    -perm 按照文件权限来查找文件
    -uer 按照文件属主来查询文件
    -group 按照文件所属的组来查找文件
    -mtime -n +n  按照文件的更改时间来查找文件， - n表示文件更改时间距现在n天以内，+ n表示文件更改时间距现在n天以前。find命令还有-atime和-ctime 选项，但它们都和-m time选项。

    atime : 访问时间(access time)
    mtime : 修改时间(modify time)
    ctime: 状态修改时间(change time)

    -type  查找某一类型的文件，诸如：

    b - 块设备文件。

    d - 目录。

    c - 字符设备文件。

    p - 管道文件。

    l - 符号链接文件。

    f - 普通文件。

    ## 查看文件属性
    stat filename 

    ## 命令参数：

    -a 列出打开文件存在的进程

    -c<进程名> 列出指定进程所打开的文件

    -g  列出GID号进程详情

    -d<文件号> 列出占用该文件号的进程

    +d<目录>  列出目录下被打开的文件

    +D<目录>  递归列出目录下被打开的文件

    -n<目录>  列出使用NFS的文件

    -i<条件>  列出符合条件的进程。（4、6、协议、:端口、 @ip ）

    -p<进程号> 列出指定进程号所打开的文件

    -u  列出UID号进程详情

    -h 显示帮助信息

    -v 显示版本信息



### 例子


    atime n  查找系统中最后N分钟访问的文件
    amin n  查找系统中最后n*24小时访问的文件

    # 查找今天的(24小时内)

    find . -atime -1

    # 查找今天之前的(24小时内)

    find . -atime +1

    # 搜索当前目录的以 .log 结尾,一天内,权限问 600 ,大小大于 1 b 的普通文件,并且按照普通方式输出
    find . -type f -name '*.log' -atime -1 -perm 600 -size +1c -print

