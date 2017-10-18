# linuxStudy
学习Linux命令

## ln命令
创建文件链接，分为创建硬链接和符号链接（软链接），有很多配置选项


### 1.创建文件软连接
文件位置：*linuxStudy/ln*

这里是举一个软链接的🌰，用到的参数是-s，-f
> -s : 创建符号链接

> -f : 强行建立文件或目录的连接，不论文件或目录是否存在
       
我觉得吧，就是有点像快捷方式

##### *ln*文件夹里有*origin*和*dest*两个文件夹，*origin*文件夹里有*dir1*文件夹，现在要做的就是将*dir1*连接到*dest*文件夹里：
1.进入*origin*文件夹，进行以下操作:
 检查文件（可省略该步骤）

```angular2html
ls -la
```
输出了：// drwxr-xr-x  2 mq  staff   68 Oct 18 16:24 dir1

2.进入*dest*文件夹，进行以下操作:

链接文件
```angular2html
ln -sf ../origin/dir1
```
这句话的意思就是在目前的文件夹下创建一个和*origin*下*dir1*一样的文件夹，并将创建好的这个*dir1*链接到*origin/dir1*
这时可以看到dest文件夹下已经生成了一个dir1文件夹，连接成功！

