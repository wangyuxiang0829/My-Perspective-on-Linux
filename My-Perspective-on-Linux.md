# My Perspective on Linux

## 变量

### 普通变量

```
$ a=10
$ echo $a
10
```

### 全局变量

```
$ echo $USER ##当前登陆系统的用户的用户名
wangyuxiang0829
$ echo $HOME ##当前用户的主目录
/home/wangyuxiang0829
$ cd $HOME ##切换到用户主目录
$ cd ~ ##另一种方式切换到用户主目录
$ echo ~ ##等价于$HOME
/home/wangyuxiang0829
```

```
$ echo $PATH ##等价于windows中环境变量->系统变量->Path
...
$ PATH=$PATH:/home/wangyuxiang0829/workspace ##添加某个路径进环境变量
```



## 打包与解包

### zip与unzip



### tar

```
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



## 压缩与解压缩

### .xz

```
$ xz --help
Usage: xz [OPTION]... [FILE]...
Compress or decompress FILEs in the .xz format.
# -z 压缩(compress)
# -d 解压缩(decompress)
##Examples:
	xz -d filename.tar.xz	# 将会生成filename.tar文件
```

### .bz2

```
$ bzip2 --help
bzip2, a block-sorting file compressor.  Version 1.0.6, 6-Sept-2010.
   usage: bzip2 [flags and input files in any order]
# -z 压缩(compress)
# -d 解压缩(decompress)
## Examples:
	bzip2 -d filename.tar.bz2	# 将会生成filename.tar文件
```

### .gz

```
$ gzip --help
Usage: gzip [OPTION]... [FILE]...
Compress or uncompress FILEs (by default, compress FILES in-place).
# -d 解压缩(decompress)
## Examples:
	gzip -d filename.tar.gz		# 将会生成filename.tar文件
```



## 下载

```
$ wget --help
GNU Wget 1.19.4, a non-interactive network retriever.
Usage: wget [OPTION]... [URL]...
```

