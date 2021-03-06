# 基本命令介绍

看到Bash提示符之后，表明我们可以开始使用命令行和系统进行交互了。

## 基本命令

基本命令格式:

    command [options] [arguments]

* command：命令
* options：--单词   或   -单字
* arguments：参数，有时候选项也带参数。

在查看命令帮助时，会出现``[]``,``<>``,``|``等符号，它们的含义如下：

* 无任何特殊符号 代表必选参数
* ``[]``       表示是可选的;
* ``<>``       表示可变选项，一般是多选一，而且必须是要选其一。
* ``x|y|z``    多选一，如果加上[]，可不选。如果加上{}，必选其一。
* ``-abc``     多选，如果加上[]，可不选。

### echo

在终端上打印字符串到标准输出。

    Usage: echo [-neE] [arg ...]

常用参数:

```
-e: 启用特殊转义字符(\t, \b, \n等)
-n: 行末不添加换行符
```

用法示例:

```bash
$ echo hello world                                # hello world
$ echo -e '\033[32;49;1mhello world\033[39;49;0m' # 自己试试看这个结果是什么？
```

### ls

``ls``的作用为显示指定目录的文件。

    Usage: ls [OPTION]... [FILE]...

常用参数:

```
-l: 重要参数，以长列表形式显示
-a: 列出所有文件，包含隐藏文件
-R: 递归目录列出文件
-d: 显示目录本身，而非目录下文件
```

用法示例

```bash
$ ls                    # 列出当前目录下所有非隐藏文件
$ ls .                  # 同上
$ ls -a                 # 列出当前目录下所有文件
$ ls /tmp/              # 列出指定目录下文件
$ ls /var/log/boot.log  # 列出指定文件
```

### cd

切换当前的工作目录

    Usage: cd [-L|[-P [-e]] [-@]] [dir]

用法示例:

```bash
$ cd /path/       # 跳转到指定目录
$ cd              # 跳转到家目录
$ cd ~            # As above
$ cd ~USERNAME    # 跳转到指定用户的家目录
$ cd -            # 跳转到上一次所在目录
```

### cat

打开文件

    Usage: cat [OPTION]... [FILE]...

常用参数:

```
-n: 显示行号
```

用法示例:

```bash
$ cat file1 file2 file3    # 在当前终端下依次打开3哥文件
$ cat -n file1              # 打开单个文件，并显示行号
```

> 倒序打开文件可以用命令``tac``，即``cat``反向写

### pwd

显示当前工作目录

    pwd: pwd [-LP]

用法示例:

    $ pwd   # 打印当前绝对路径
