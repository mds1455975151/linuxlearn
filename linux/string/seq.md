> seq 命令用于产生从某个数到另外一个数之间的所有证书

语法
---
    seq [选项]... 尾数
    seq [选项]... 首数 尾数
    seq [选项]... 首数 增量 尾数
    
选项
---
    -f, --format=格式        使用printf 样式的浮点格式
    -s, --separator=字符串   使用指定字符串分隔数字（默认使用：\n）
    -w, --equal-width        在列前添加0 使得宽度相同
    实例

实例
--
    
-f 选项: 指定格式

    seq -f"%3g" 9 11

-s: 指定分隔符(默认是回车)
    
指定 `\n` 作为分隔符号:

    # seq -s "`echo -e "\n"`" 19 10 119
    192939495969798999109119
    

> awk '/start_pattern/, /end_pattern/' filename

    
    seq 100 | awk '/13/,/15/'
    cat /etc/passwd| awk '/mai.*mail/,/news.*news/'