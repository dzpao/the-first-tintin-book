# 安装与启动❌

## 我该选择什么版本？

TinTin++ 在几乎所有操作系统上都可以使用。TinTin++ 社区目前主要存在以下版本，可供不同的用户选择使用：

*   **正式版**

    即 TinTin++ 正式对外发布的版本，一般来说会滞后 6 个月左右。笔者书写本文时，最新的正式版版本为 2.02.41，于 2024-01-03 日发布。
*   **beta 版**

    由于 TinTin++ 更新频繁，正式版相对来说不够新。而大部分 TinTin++ 更新可能是为了修改某个 BUG 或者增加某个重要的新功能。那么对于想要及时获得这些更新的朋友，beta 版是一个更好的选择。
*   **包管理器维护的版本**

    作为一款老牌开源软件，不论是正式版，还是 beta 版，官方都是以源代码的形式进行发布，这意味着用户需要自行编译。那么对于不想安装编译器的朋友来说，如果你的操作系统提供了一份包管理器维护的版本，对你来说就是一个不错的选择。这个版本一般都是某个次新的正式版，由于 TinTin++ 自身占有的安装空间很小，因此很适合用来做初步的学习和了解。
*   **WinTin++**

    由于 Windows 下的编译环境较难搭建，也没有好用的包管理器，因此 TinTin++ 官方提供了一份预编译的 Windows 安装包，一般称之为 WinTin++。但是 WinTin++ 没有 beta 版，只有正式版。
*   **PaoTin++**

    如前所述，正式版不够新，可能有 BUG 或者缺少某个关键的特性，测试版又要懂编译，Windows 下的编译环境很难安装，其它操作系统的编译方法又不统一，如此种种，都成为了 TinTin++ 用户新手之路上的绊脚石。有鉴于此，笔者创建了 PaoTin++ 项目，可以在包括 Windows 在内的所有操作系统都能够实现一键安装，并且是最新版本（比 beta 版功能还要多）。

## 如何安装？

如前所述，TinTin++ 有不同的版本，根据版本的不同，相应的安装方式也有所不同。

1.  **直接用包管理器安装**。

    许多 Linux 发行版，以及 macOS 都有收录 TinTin++，你只要用你的包管理器（apt、yum、brew等）搜索 tintin，应该就可以搜得到。
2.  **源码安装**。

    适用于大部分 Unix 系统。包括苹果、安卓、Linux、BSD，等等。这种安装方式要求用户先安装编译器，然后下载一份源代码，还要安装少量的编译依赖包，最后再完成编译。

    源代码可以从 [GitHub](https://github.com/scandum/tintin) 上下载到。

    具体安装方法参考：[https://tintin.mudhalla.net/install.php](https://tintin.mudhalla.net/install.php)。
3.  **预编译的 WinTin++**。

    可以从这里找到安装包：[https://github.com/scandum/tintin/releases](https://github.com/scandum/tintin/releases)。
4.  **安装 PaoTin++**。

    请参考：[https://pkuxkx.net/wiki/tools/paotin](https://pkuxkx.net/wiki/tools/paotin)

## 除了这些，我还需要什么？

TinTin++ 是一款终端下的应用。这意味着要想运行它就需要一款终端模拟器。终端模拟器一般运行在本地桌面，通过 shell 或者 ssh 的方式连接到 TinTin++ 进程，根据你的桌面操作系统的不同，建议选择如下终端模拟器：

* macOS：iTerm2，或者 wezTerm、kitty、alacritty
* Windows：Windows Terminal，或者 wezTerm、MobaXterm、Xshell
* Linux：Sakura、wezTerm

WinTin++ 自带了 minitty，比较丑，追求美观的朋友建议改用 Windows Terminal。

## 如何启动？

进入你的终端模拟器，连接到本地 shell，或者通过 ssh 连接到远程 shell，然后输入 `tt++`，就可以进入 TinTin++。

* WinTin++ 用户也可以选择通过桌面快捷方式启动
* 如果你是通过源码自行编译的版本，记得把编译产物 `tt++` 放到你的 `$PATH` 环境变量中的某个目录
* PaoTin++ 用户请注意查看文档，观察安装后指引。

## 链接汇总

* 官网：[https://tintin.mudhalla.net/](https://tintin.mudhalla.net/)
* 源代码：[https://github.com/scandum/tintin](https://github.com/scandum/tintin)
* 正式版：
  * 官网: [https://tintin.mudhalla.net/download.php](https://tintin.mudhalla.net/download.php)
  * GitHub: [https://github.com/scandum/tintin/releases](https://github.com/scandum/tintin/releases)
* 测试版：[https://www.mudhalla.net/tintin-beta.tar.gz](https://www.mudhalla.net/tintin-beta.tar.gz)
* WinTin++：[https://github.com/scandum/tintin/releases](https://github.com/scandum/tintin/releases)
* PaoTin++:  [https://pkuxkx.net/wiki/tools/paotin](https://pkuxkx.net/wiki/tools/paotin)

###



