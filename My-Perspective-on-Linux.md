# My Perspective on Linux

## 基本命令

```shell
$ date # 查看当前时间
Mon Apr  8 11:21:24 DST 2019
$ cal # 查看日历
     April 2019
Su Mo Tu We Th Fr Sa
    1  2  3  4  5  6
 7  8  9 10 11 12 13
14 15 16 17 18 19 20
21 22 23 24 25 26 27
28 29 30

$ cal 2019 # 查看2019年日历
                            2019
      January               February               March
Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa
       1  2  3  4  5                  1  2                  1  2
 6  7  8  9 10 11 12   3  4  5  6  7  8  9   3  4  5  6  7  8  9
13 14 15 16 17 18 19  10 11 12 13 14 15 16  10 11 12 13 14 15 16
20 21 22 23 24 25 26  17 18 19 20 21 22 23  17 18 19 20 21 22 23
27 28 29 30 31        24 25 26 27 28        24 25 26 27 28 29 30
                                            31

       April                  May                   June
Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa
    1  2  3  4  5  6            1  2  3  4                     1
 7  8  9 10 11 12 13   5  6  7  8  9 10 11   2  3  4  5  6  7  8
14 15 16 17 18 19 20  12 13 14 15 16 17 18   9 10 11 12 13 14 15
21 22 23 24 25 26 27  19 20 21 22 23 24 25  16 17 18 19 20 21 22
28 29 30              26 27 28 29 30 31     23 24 25 26 27 28 29
                                            30

        July                 August              September
Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa
    1  2  3  4  5  6               1  2  3   1  2  3  4  5  6  7
 7  8  9 10 11 12 13   4  5  6  7  8  9 10   8  9 10 11 12 13 14
14 15 16 17 18 19 20  11 12 13 14 15 16 17  15 16 17 18 19 20 21
21 22 23 24 25 26 27  18 19 20 21 22 23 24  22 23 24 25 26 27 28
28 29 30 31           25 26 27 28 29 30 31  29 30


      October               November              December
Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa
       1  2  3  4  5                  1  2   1  2  3  4  5  6  7
 6  7  8  9 10 11 12   3  4  5  6  7  8  9   8  9 10 11 12 13 14
13 14 15 16 17 18 19  10 11 12 13 14 15 16  15 16 17 18 19 20 21
20 21 22 23 24 25 26  17 18 19 20 21 22 23  22 23 24 25 26 27 28
27 28 29 30 31        24 25 26 27 28 29 30  29 30 31

$ cal 1 2019 # 查看2019年1月日历
    January 2019
Su Mo Tu We Th Fr Sa
       1  2  3  4  5
 6  7  8  9 10 11 12
13 14 15 16 17 18 19
20 21 22 23 24 25 26
27 28 29 30 31

$ which git # 查看某个命令的路径
/usr/bin/git


$ cd ~ # 切换到家目录
$ mkdir tutorial # 创建目录
$ ls # 查看当前目录信息
tutorial
$ cd tutorial/ # 切换到tutorial目录
$ ls # 没有输出，则目录为空
$ touch file1.txt # 创建文件
$ touch file2.txt # 创建文件
$ ls
file1.txt  file2.txt # 创建的文件
$ vim file1.txt
$ vim file2.txt
$ cat file1.txt # 输出文件内容
hello1
$ cat file2.txt # 输出文件内容
hello2
$ cp file1.txt file3.txt # 复制文件
$ ls
file1.txt  file2.txt  file3.txt
$ cat file1.txt
hello1
$ cat file3.txt
hello1
$ diff file1.txt file3.txt # 列出连个文件的不同之处，没有输出说明完全相同
$ diff file1.txt file2.txt
1c1
< hello1
---
> hello2
$ mv file1.txt helloworld.txt # 对文件重命名
$ ls
file2.txt file3.txt helloworld.txt
$ mv helloworld.txt ../ # 移动文件到指定目录
$ rm file2.txt # 删除文件
$ rm file3.txt
$ rmdir tutorial/ # 删除目录，不能删除非空目录


$ cat invictus
Out of the night that covers me,

Black as the pit from pole to pole,
I thank whatever gods may be,
For my unconquerable soul,
In the fell clutch of circumstance,
I have not winced nor cried aloud,
Under the bludgeoning of chance,
My head if bloody, but unbowed,

Beyond this place of wrath and tear,

Looms but the Horror of the shade,
And yet the menace of the years,
Finds, and shall find, me unafraid,
It matters not how strait the gate,
How charged with punishments the scroll,
I am the master of my fate,
I am the captain of my soul.
$ head invictus -n 5 # 只显示文件前5行
Out of the night that covers me,

Black as the pit from pole to pole,
I thank whatever gods may be,
For my unconquerable soul,
$ tail invictus -n 5 #只显示文件后5行
Finds, and shall find, me unafraid,
It matters not how strait the gate,
How charged with punishments the scroll,
I am the master of my fate,
I am the captain of my soul.
$ wc invictus # 查看文件行数与单词数以及大小
 19 103 559 invictus # 19行 103个单词 559个字节 文件名称
```



---



## 文件结构与权限

Linux文件属性

1. 用户身份
   1. 拥有者(user)
   2. 用户组(group)
   3. 其他人(others)
2. 权限
   1. 可读(r)
      1. 对于文件：可以使用类似cat命令查看
      2. 对于目录：可以使用类似ls命令查看
   2. 可写(w)
      1. 对于文件：可以使用类似vim命令进行更改
      2. 对于目录：可以使用类似touch命令在目录中创建新文件
   3. 可执行(x)
      1. 对于文件：可以运行
      2. 对于目录：可以使用类似cd命令进入
3. 类型
   1. 目录(d)
   2. 文件(-)
   3. 链接(l)

```shell
$ pwd # 查看当前路径
/home/wangyuxiang0829
$ cd / # 切换到根目录
$ ls # 查看当前目录信息
bin   dev  home  lib    lib64   media  opt   root  sbin  sys  usr
boot  etc  init  lib32  libx32  mnt    proc  run   srv   tmp  var
$ ls -l # 查看当前目录详细信息
total 88
lrwxrwxrwx  1 root root     7 Feb 20 00:30 bin -> usr/bin
drwxr-xr-x  1 root root   512 Nov 29 21:49 boot
drwxr-xr-x  1 root root   512 Apr  8 11:21 dev
drwxr-xr-x  1 root root   512 Apr  6 22:18 etc
drwxr-xr-x  1 root root   512 Apr  6 22:18 home
-rwxr-xr-x  1 root root 87944 Jan  1  1970 init
lrwxrwxrwx  1 root root     7 Feb 20 00:30 lib -> usr/lib
lrwxrwxrwx  1 root root     9 Feb 20 00:30 lib32 -> usr/lib32
lrwxrwxrwx  1 root root     9 Feb 20 00:30 lib64 -> usr/lib64
lrwxrwxrwx  1 root root    10 Feb 20 00:30 libx32 -> usr/libx32
drwxr-xr-x  1 root root   512 Feb 20 00:30 media
drwxr-xr-x  1 root root   512 Apr  6 22:17 mnt
drwxr-xr-x  1 root root   512 Feb 20 00:30 opt
dr-xr-xr-x  9 root root     0 Apr  8 11:21 proc
drwx------  1 root root   512 Feb 20 00:30 root
drwxr-xr-x  1 root root   512 Apr  8 11:21 run
lrwxrwxrwx  1 root root     8 Feb 20 00:30 sbin -> usr/sbin
drwxr-xr-x  1 root root   512 Feb 20 00:30 srv
dr-xr-xr-x 12 root root     0 Apr  8 11:21 sys
drwxrwxrwt  1 root root   512 Feb 20 00:34 tmp
drwxr-xr-x  1 root root   512 Feb 20 00:30 usr
drwxr-xr-x  1 root root   512 Feb 20 00:30 var
```



---



## 变量

### 普通变量

```shell
$ a=10
$ echo $a
10
```

### 全局变量

```shell
$ echo $USER ##当前登陆系统的用户的用户名
wangyuxiang0829
$ echo $HOME ##当前用户的主目录
/home/wangyuxiang0829
$ cd $HOME ##切换到用户主目录
$ cd ~ ##另一种方式切换到用户主目录
$ echo ~ ##等价于$HOME
/home/wangyuxiang0829
```

```shell
$ echo $PATH ##等价于windows中环境变量->系统变量->Path
...
$ PATH=$PATH:/home/wangyuxiang0829/workspace ##添加某个路径进环境变量
$ echo $SHELL ##当前用户的默认shell
/bin/bash
```



---



## 打包与解包

### zip与unzip



### tar

```shell
$ tar --help
Usage: tar [OPTION...] [FILE]...
GNU 'tar' saves many files together into a single tape or disk archive, and can restore individual files from the archive.
# -c 压缩(compress)
# -x 提取(extract)
# -v 显示详细过程(verbose)
# -t 仅显示一个归档文件中的所有文件(list)
# -f 指定文件名称(需要是最后一个参数)(file)
##Examples:
  tar -cf archive.tar foo bar  # Create archive.tar from files foo and bar.
  tar -tvf archive.tar         # List all files in archive.tar verbosely.
  tar -xf archive.tar          # Extract all files from archive.tar.
```



---



## 压缩与提取

### .xz

```shell
$ xz --help
Usage: xz [OPTION]... [FILE]...
Compress or decompress FILEs in the .xz format.
# -z 压缩(compress)
# -d 解压缩(decompress)
##Examples:
	xz -d filename.tar.xz	# 将会生成filename.tar文件
```

### .bz2

```shell
$ bzip2 --help
bzip2, a block-sorting file compressor.  Version 1.0.6, 6-Sept-2010.
   usage: bzip2 [flags and input files in any order]
# -z 压缩(compress)
# -d 解压缩(decompress)
## Examples:
	bzip2 -d filename.tar.bz2	# 将会生成filename.tar文件
```

### .gz

```shell
$ gzip --help
Usage: gzip [OPTION]... [FILE]...
Compress or uncompress FILEs (by default, compress FILES in-place).
# -d 解压缩(decompress)
## Examples:
	gzip -d filename.tar.gz		# 将会生成filename.tar文件
```



---



## 下载

```shell
$ wget --help
GNU Wget 1.19.4, a non-interactive network retriever.
Usage: wget [OPTION]... [URL]...
```

