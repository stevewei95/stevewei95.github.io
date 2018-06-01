---
title: Homebrew 的安装和使用
date: 2018-06-01 14:04:24
categories:
  - mac
tags:
  - mac
  - homebrew
  - 包管理
---
Homebrew 是一款 macOS 平台下的软件包管理工具，拥有安装、卸载、更新、查看、搜索等很多实用的功能。包管理工具可以让你安装和更新程序变得更方便，目前在 OS X 系统中最受欢迎的包管理工具就是 Homebrew。

## 系统要求

- Intel CPU
- OS X 10.9 or higher
- Xcode 命令行工具 `$ xcode-select --install`
- 支持shell (sh 或者 bash)

## 安装和卸载

**\* 注意：安装过程中请确保 mac 处于网络连通状态。**

- **安装**

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

  将以上命令粘贴至终端。脚本会在执行前暂停，并说明将它将做什么。

- **卸载**

```shell
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
```

要卸载 Homebrew，请在终端提示下粘贴以上命令。
下载 [卸载脚本](https://raw.githubusercontent.com/Homebrew/install/master/uninstall) 并运行`./uninstall --help`以查看更多卸载选项。

## Homebrew 能干什么

使用 Homebrew 安装 Apple macOS 没有预装但 [你需要的东西](https://github.com/Homebrew/homebrew-core/tree/master/Formula "Homebrew 软件包列表")。

## Homebrew 基本使用

- 安装任意包

```shell
$ brew install <packageName>
```

- 示例：安装 wget

```shell
$ brew install wget
```

- 卸载任意包

```shell
$ brew uninstall <packageName>
```

- 示例：卸载 git

```shell
$ brew uninstall git
```

- 查询可用包

```shell
$ brew search <packageName>
```

- 查看已安装包列表

```shell
$ brew list
```

- 查看任意包信息

```shell
$ brew info <packageName>
```

- 更新 Homebrew

```shell
$ brew update
```

- 查看 Homebrew 版本

```shell
$ brew -v
```

- 查看 Homebrew 帮助信息

```shell
$ brew -h
```

- 输出示例:

```shell
Example usage:
  brew search [TEXT|/REGEX/]
  brew info [FORMULA...]
  brew install FORMULA...
  brew update
  brew upgrade [FORMULA...]
  brew uninstall FORMULA...
  brew list [FORMULA...]

Troubleshooting:
  brew config
  brew doctor
  brew install --verbose --debug FORMULA

Contributing:
  brew create [URL [--no-fetch]]
  brew edit [FORMULA...]

Further help:
  brew commands
  brew help [COMMAND]
  man brew
  https://docs.brew.sh
```

## 注意事项

在 macOS X 10.11系统以后，/usr/local/ 等系统目录下的文件读写是需要系统 root 权限的，以往的 Homebrew 安装如果没有指定安装路径，会默认安装在这些需要系统 root 用户读写权限的目录下，导致有些指令需要添加 sudo 前缀来执行，比如升级 Homebrew 需要：

```shell
$ sudo brew update
```

如果你不想每次都使用 sudo 指令，你有两种方法可以选择:

1. 对 /usr/local 目录下的文件读写进行 root 用户授权。

```shell
$ sudo chown -R $USER /usr/local
```

示例：

```shell
$ sudo chown -R stevewei /usr/local
```

2. （推荐）安装 Homebrew 时对安装路径进行指定，直接安装在不需要系统 root 用户授权就可以自由读写的目录下。

```shell
<install path> -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

-----

**\* 更多 Homebrew 官方文档请参考 [这里](https://docs.brew.sh/)**
