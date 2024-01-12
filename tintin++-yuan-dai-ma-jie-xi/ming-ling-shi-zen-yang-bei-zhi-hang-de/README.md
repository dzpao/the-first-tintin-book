# 命令是怎样被执行的❌

命令执行的总入口是 `script_driver()`，不论是命令行输入还是执行脚本最终都是通过它。调用路径分别如下：

* 命令行输入： `update.c:mainloop()` => `update.c:update_input()` => `input.c:process_input()` => `parse.c:parse_input()` => `tokenize.c:script_driver()`

`process_input()` 本质上仍然是事件循环的一部分，一次只捕获一个按键，因此最终是否真的调用 `parse_input()` 取决于用户是否按下了回车键。这部分处理在 `cursor.c` 中进行，按下回车键后会设置标记 `TINTIN_FLAG_PROCESSINPUT`，否则就会跳过后续处理：

```
	if (!HAS_BIT(gtd->flags, TINTIN_FLAG_PROCESSINPUT))
	{
		pop_call();
		return;
	}
```

* 执行脚本：`files.c:do_read()` => `files.c:read_file()` => `tokenize.c:script_driver()`

注意 `read_file()` 中有一个相当长的前置处理，在交给 `script_driver()` 之前，实际上就已经做了一些粗略的词法处理：

* 去掉注释
* 处理花括号
* 忽略 `'\r'`，去掉 `'\n'`，并且根据命令分隔符（也就是 `';'`）拆分命令。
* FIXME: 没找到关于转义字符的处理，不确定是何时处理的。
