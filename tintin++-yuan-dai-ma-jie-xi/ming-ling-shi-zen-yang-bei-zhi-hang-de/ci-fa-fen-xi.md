# 词法分析❌

词法分析主要是提供了一些工具函数，都在 `parse.c` 中，而语法解析和代码执行则主要是在 `tokenize.c` 当中。后者会调用前者。

这些工具函数都是一些超高频操作：

* `get_arg_all`: 吞掉所有字符，直到分号为止。
* `get_arg_at_brackets`: 吞掉一对方括号和它们中间的内容，支持嵌套。
* `get_arg_to_brackets`:
* `get_arg_in_brackets`: 和 `get_arg_at_brackets` 非常相似（吐槽），没仔细看有什么区别。
*   `get_arg_in_braces`: 吞掉一对花括号和它们中间的内容，支持嵌套。

    注意这里有个情况，如果待处理的文本不是以花括号开头的话，则分两种情况：

    1. 如果提供了 `GET_ALL` 记号，则执行 `get_arg_with_spaces` 逻辑
    2. 如果没提供 `GET_ALL` 记号，则执行 `get_arg_stop_spaces` 逻辑
* 低频函数 `get_arg_stop_digits`: 吞掉一个字符串，遇到数字时停止。有一些细节，暂未深究 FIXME。
* 低频函数 `get_arg_stop_spaces`: 吞掉一个字符串，遇到空白时停止。有一些细节，暂未深究 FIXME。
* 低频函数 `get_arg_with_spaces`: 吞掉一个字符串，直到分号时停止。有一些细节，暂未深究 FIXME。
* `sub_arg_all`: 先执行 `get_arg_all`，然后执行替换。
* `sub_arg_in_braces`: 先执行 `get_arg_in_braces`，然后执行替换。
* `sub_arg_stop_spaces`: 先执行 `get_arg_stop_spaces`，然后执行替换。

这些函数的原型都很像，基本都是这样：

```
const char *get_arg_xxx(struct session *ses, const char *source, char *output, int flag);
const char *sub_arg_xxx(struct session *ses, const char *source, char *output, int flag, int sub);
```

其中 `source` 指向需要解析的源代码，`output` 则指向用作存放提取物的目标缓冲区，函数返回值则指向剩余的源代码。

`flag` 参数和 `sub` 参数会对它们的行为产生重要的影响：

* `GET_ONE`: 遇到空格时停止。
* `GET_ALL`: 遇到分号时才停止。
* `GET_NST`: 允许方括号嵌套。
* `GET_VBT`: 遇到分号时也不停止。
* `GET_SPC`: 保留空白。

`sub` 参数的值请参考 [wen-ben-ti-huan.md](wen-ben-ti-huan.md "mention")。

这里面最常用是 `get_arg_in_braces` 和 `sub_arg_in_braces`，各有数百次的调用。其次是 `get_arg_to_brackets` 和 `get_arg_in_brackets`，各有二十多次调用。其余用得很少。

`sub_arg_in_braces` 可以看作是 `get_arg_in_braces` 和 `substitute` 的组合。

