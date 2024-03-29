---
description: 《第一本 tintin++ 编程书》
---

# 前言✅

## 前言的前言

好像所有的书都有个前言，但好像着急的人都很少看前言。既然如此，笔者决定不在这里写什么重要的东西，所以如果你着急想要快速上手的话，可以直接跳过本章内容。

等等，在你划走之前，先跟你确认三件事情：

* 除本章外，本书其余章节中常常将 TinTin++ 简写为 tt++ 或者 tt。
* 假设你已经知道 TinTin++ 是一门可编程的 MUD 客户端，并且想要学好它。
* 假设你已经知道 MUD 是一种基于文字（感官上 ）和 TELNET 协议（技术上）的多人网络游戏。

好了，接下来你可以阅读：

{% content-ref url="yue-du-zhi-nan.md" %}
[yue-du-zhi-nan.md](yue-du-zhi-nan.md)
{% endcontent-ref %}

## 为什么创作本书

笔者自己用了几年的 TinTin++，在这期间虽然得到过不少朋友的帮助，但坦率来说，过程还是比较曲折的。刚开始几个月基本上可以说是完全摸不着头脑，经常被一个小错误就卡住很久，严重影响书写机器人的节奏感。究其原因，无非有三：

#### 1，TinTin++ 是一门小众语言

MUD 本身就是一类小众游戏，TinTin++ 作为一种 MUD 客户端，在如今的 MUD 圈子中，也算不上是主流。小众中的小众，导致网络上很少有 TinTin++ 相关的资料。不用说书了，就连文档，都少之又少。所以本书自诩为《第一本 TinTin++ 编程书》，确有想要填补这一空白的初衷。希望读者籍由本书，能够在面对 TinTin++ 时，不再盲人摸象，遇到问题时也能够有所帮助。

#### 2，TinTin++ 的语法比较特别

「TinTin++ 是一门基于替换的语言」，笔者常常跟朋友们这么讲。和你所接触到的大多数编程语言不同，TinTin++ 不是一门需要编译的、有着严格的语法规范和 AST（抽象语法树）的古板的编程语言。它是一门解释执行的脚本语言。它没有清晰的词法和语法分界线，除非代码执行到了那里，否则谁也不知道它的语句从哪里开始，到哪里结束。它有许多丰富的转义和内插功能，比一般的脚本语言都要复杂得多。这虽然可以让它变得更强大，但常常在你没有意识到的时候让你掉进陷阱。更令人头痛的是，随着 TinTin++ 的更新，这一切还常常发生变化，甚至可能还会遇到 BUG。

#### 3，MUD 编程场景比较特别

也许你之前已经接触过编程，甚至还写过一些小软件。于是当你接触了 MUD 后，你可能会想到，这些重复性的工作非常枯燥，所以你想要写一个机器人。但很快你会发现，MUD 编程与你之前接触过的编程场景存在很大不同：你不能把你想做的事情一口气全都写下来，就像你以前写 DOS 批处理或者 shell script 那样，发送给服务器。在一些服务器上，这样做可能会被雷劈（是真的雷劈，不是在骂人），而另外一些比较友好的服务器，则会给你一个「命令过多」的友好提示。这期间还可能会遇到一些恶作剧的玩家或者 NPC，让你的命令无法得到预期的效果。于是你不得不面对「异步编程」，就是将你要做的事情分成若干个相对可靠的步骤，然后一小段一小段地发送给服务器，然后等待服务器的应答，根据应答情况再决定下一步应该如何做。渐渐地，你会感到你将花费大量的精力来做这种异步控制和错误处理。这是其它编程场景中很少遇到的事情。

希望上面的这些文字没有吓倒你，并没有阻止你想要继续征服 TinTin++ 的野心。

或者你已经开始打退堂鼓了？已经开始犹豫，既然 TinTin++ 有这么多缺点，那要不要换个客户端试试？那下面笔者再为 TinTin++ 说几句好听的。

## 为什么选择 TinTin++

尽管 TinTin++ 有这样或者那样的缺点，但它对于许多人来说，仍然是最好的选择。在某些情况下，它甚至是唯一的选择。且听笔者道来：

#### 1，TinTin++ 是最古老的 MUD 客户端，是许多其它同样古老的客户端曾经模仿的蓝本，并且仍在更新

MUD 曾经是一种非常热门的游戏种类，在那个时期，诞生了许多优秀的 MUD 客户端，包括一些收费客户端。但是随着 MUD 游戏玩的人越来越少，这些 MUD 客户端大多已不再更新。一部分玩家出于个人习惯原因，仍然坚持使用，但随着软硬件环境的变化，如同许多古董软件一样，使用障碍越来越多。玩家们被迫寻找新的替代品，适应新的软件操作习惯，重新制作他们的机器人。

TinTin++ 诞生于 1992 年，至今已有 30 年历史。作为最古老的 MUD 客户端，它的语法设计影响了许多后续客户端的语法。但 TinTin++ 至今仍在更新，仅 2019～2022 就有 16 次版本发布。新版本带来的一些新特性比如 GBK 编码和 UTF-8 编码转换让这款古老的 MUD 客户端即使是在今天也仍然不落后于时代。而一些新秀则缺乏经年累月的沉淀，还在补足特性奋起直追当中。

#### 2，TinTin++ 是开源软件，你可以自由地、免费地获得它，并享受来自社区的支持

TinTin++ 目前的版本托管在 [github](https://github.com/scandum/tintin) 上，遵守 GPLv3 协议。这意味着你可以自由地获取它的源代码，根据自己的需要进行修改、定制，将它移植到你的专属硬件上。即使你自己并不具备这个能力，但你也要明白，正因为 TinTin++ 是这样的软件，所以才可以被那些来自于全世界的具有能力的开发者合作维护，而不会随着个人或者公司对它丧失兴趣而从世上消失。这也是 TinTin++ 能够存世 30 年不灭的根本原因。

TinTin++ 的开源软件属性也意味着会拥有更加开放的社区。来自全世界的用户一起交流心得，聚焦技术，拒绝灌水，让任何你在使用过程中遇到的问题都能够得到最快速的解决。

#### 3，TinTin++ 有一门专门面对 MUD 场景的 DSL（领域特定的编程语言），灵活，高效，强大

MUD 客户端除了提供玩家与 MUD 服务器交互的人机界面之外，有一个重要的作用就是制作并使用机器人。有人说，开发一个 MUD 客户端很容易，但设计一门适合编写机器人的编程语言，就不那么容易了。这也是为什么早期有许多客户端都借鉴 TinTin++ 语法的原因了，在那个脚本语言匮乏的年代，TinTin++ 的语法实际上成为了 MUD 客户端事实上的标准。

随着新世纪的到来，脚本语言越来越丰富，陆续就有客户端将 VB Script、JavaScript、Lua、Python、PHP 等脚本语言集成进来，以吸引那些本就会这些语言的玩家，或者是弥补自身脚本语言功能上的不足。由于这些脚本语言资料相对比较丰富，功能强大，因此逐渐受到越来越多的欢迎。近年来逐渐成为开发机器人的主流。

然而，写 MUD 机器人毕竟不是开发软件。新脚本语言看似满足需求，实则南辕北辙。用它们开发的机器人噪音代码太多，干扰了正常的 MUD 流程，随着代码量的增多，也日益变得难以维护。而且 MUD 游玩过程中，并不始终都是盯着屏幕上的机器人干活，自己在一边发呆。有时候也需要亲自操作才行。这时候一门简洁、高效、灵活、强大的 MUD 编程语言就可以让你如鱼得水。

#### 4，TinTin++ 是跨平台的，可在苹果电脑、路由器、家庭 NAS、Docker、VPS、手机、树莓派、电视机上运行

如前所述，TinTin++ 是开源软件。它是 C 语言写的，并且依赖非常少（仅 zlib 和 pcre 两个 library），因此可以被移植到大多数平台上。如果你不仅仅只是为了提高你的游戏角色的数据值，而是喜欢折腾的话，TinTin++ 将会非常适合你。

#### 5，TinTin++ 支持的 MUD 功能最全

作为一个 MUD 客户端，TinTin++ 有如下特性：

* 支持 PCRE 的触发器、别名、gag（文本消除）、高亮、替换、按键宏、定时器、延迟响应、事件
* 支持关联数组（类比别的语言的 table 或者 map）
* 丰富的文本格式化功能
* 可搜索的滚动缓冲区
* 64 位浮点数
* 逻辑运算和算术运算
* 自动画地图并可通过 VT100 来显示地图
* 多会话支持
* 加载和解析任何文件
* 执行命令行脚本
* 透过 ssh/sftp 等客户端来运行命令行程序，并可以通过 TinTin++ 脚本语言全面控制
* 切分屏幕以区分客户端输入和 MUD 输出
* 用 VT100 控制字符来绘制状态条
* 基于滚动缓冲区的 tab 补全
* xterm 256 色、真彩色
* MUD 用到的大多数 TELNET 选项
* MCCP（MUD 客户端压缩协议）、MMCP（MUD 聊天协议）

限于篇幅，以上只是一个不完整清单。更多内容请参考[官网说明](https://tintin.mudhalla.net/)。

#### 6，TinTin++ 不仅可以用来玩游戏

虽然 TinTin++ 是一个 MUD 客户端，但它也可以当作是一种 Unix shell 命令语言，或者是多路复用程序，或者自动化工具。大多数控制台程序（比如 bash）都可以通过 TinTin++ 唤起，并且允许创建高亮、进行替换、设置触发、定时器、别名，或者是提取文本到另一个子窗口，把多个流组合成一个，等等。这允许你修改大多数控制台程序的外观、交互界面，以及行为。

如果你恰好知道 expect 工具的话，你会发现 TinTin++ 实际上是一个更加强大的 expect。而如果你之前做过日志分析之类的工作的话，你会发现用 TinTin++ 重构你的日志分析工具也许会让业务逻辑显得更清晰，代码更好维护。

#### 7，TinTin++ 是一款真正的 MUD 客户端

MUD 本质上是文字游戏，借助于 TELNET 协议与 vt100 控制字符，让 TTY 界面变得色彩斑斓，内容丰富。因此所有的 GUI MUD 客户端，本质上都首先必须是一个终端模拟器。可是，有什么 MUD 客户端的终端模拟功能能强过真正的终端模拟器呢？对于那些真正喜欢终端应用，喜欢 TUI，喜欢命令行的玩家来说，与其使用一个蹩脚的 GUI MUD 客户端，还不如换一个真正的终端模拟器，让 MUD 回归到它 TUI 的本质上来，让 MUD 客户端做好一个 TUI App 该做的事，去帮助你喜爱的终端模拟器做好那些触发器和写机器人的工作吧！这就是 TinTin++ 的定位。

TinTin++ 的竞品虽多，但真正可以脱离 GUI 运行在你的终端模拟器里的，也仅有 TinTin++ 而已。只有这样，也才有可能部署在那些不带 GUI 的环境里挂机。

好了。本章就先说这些吧。
