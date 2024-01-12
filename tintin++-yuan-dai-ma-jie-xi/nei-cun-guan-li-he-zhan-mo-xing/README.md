# 内存管理和栈模型❌

tt++ 有一个自己的内存管理系统，但同时也大量使用了 C 原生的分配回收机制。

自己管理的内存应该都在这里维护：

```
struct memory_data
{
	struct stack_data      ** debug;
	int                       debug_len;
	int                       debug_max;

	struct str_data        ** stack;
	int                       stack_len;
	int                       stack_cap;
	int                       stack_max;

	struct str_data        ** list;
	int                       list_len;
	int                       list_max;

	int                     * free;
	int                       free_len;
	int                       free_max;
};
```

可以看出主要是三部分内容：崩溃报错时用的调用栈，以及基于栈模型的内存池，还有各种 list（应该是模拟了堆的作用）。

对应的源代码是 `memory.c`，方法应该还算齐备，如果善用它们的话，应该
