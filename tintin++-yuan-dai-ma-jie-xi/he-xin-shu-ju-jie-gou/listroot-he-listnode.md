# listroot 和 listnode

list 是 TinTin++ 源码中非常重要的基础数据结构，顾名思义它就是一个列表，一维的有序的集合，这种基础数据结构可以用来存放大多数 TinTin++ 定义块。参见 `#info` 命令的输出，以及 `#info aliases` 等命令。

大体来说，一个 listnode 描述一个定义块，而 listroot 则是一组 listnode 的集合，但是和别处不同，这里采用了数组而非双向链表来储存多个 listnode。数组的长度由 `listroot->used` 给出，第一个元素位置为 `listroot->list[0]`, 最后一个则是 `listroot->list[listroot->used-1]`。

注意 listnode 本身并没有类型字段，也就是说它的类型由 `listroot->type` 给出，换言之 listroot 只能用来储存同类型的 listnode，同一个 listroot 下的 listnode 具有相同类型。

另外，`listroot->flags` 为整个 list 提供了一些掩码，有如下这些：

```
#define LIST_FLAG_IGNORE              BV01
#define LIST_FLAG_PRIORITY            BV02
#define LIST_FLAG_MESSAGE             BV03
#define LIST_FLAG_DEBUG               BV04
#define LIST_FLAG_INFO                BV05
#define LIST_FLAG_LOG                 BV06
#define LIST_FLAG_CLASS               BV07
#define LIST_FLAG_READ                BV08
#define LIST_FLAG_WRITE               BV09
#define LIST_FLAG_HIDE                BV10
#define LIST_FLAG_INHERIT             BV11
#define LIST_FLAG_REGEX               BV12
#define LIST_FLAG_NEST                BV13
#define LIST_FLAG_CASE                BV14
#define LIST_FLAG_DEFAULT             LIST_FLAG_MESSAGE
```

### 特殊的 list

每一次 `push_script_stack()`都会为新栈帧创建一个 listroot，用来存放该栈帧专属的 #local 变量，该 listroot 的类型为 LIST\_VARIABLE。
