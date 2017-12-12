# linuxStudy
学习Linux命令

## ln命令
创建文件链接，分为创建硬链接和符号链接（软链接），有很多配置选项


### 1.创建文件软连接
文件位置：*linuxStudy/ln*
#### 通俗的说就是我要谁就把谁拉进来

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

## 设置文件权限
参考文档： http://blog.csdn.net/dijkstar/article/details/50645139

#### Linux 系统中采用三位十进制数表示权限，如0755， 0644.
### 对应位置
#### ABCD
#### A- 0， 表示十进制
#### B－用户
#### C－组用户
#### D－其他用户

### 数字代表含义
#### ---  -> 0   (no excute , no write ,no read)
#### --x  -> 1   excute, (no write, no read)
#### -w-  -> 2   write 
#### -wx  -> 3   write, excute
#### r--  -> 4   read
#### r-x  -> 5   read, excute
#### rw-  -> 6   read, write , 
#### rwx  -> 7   read, write , excute
####  
 0755->即用户具有读/写/执行权限，组用户和其它用户具有读写权限；
 
 0644->即用户具有读写权限，组用户和其它用户具有只读权限；
