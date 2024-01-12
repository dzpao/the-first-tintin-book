# tintin\_data\* gtd❌

这是全局唯一的数据结构，任何时候都可以用 `gtd` 变量来访问。通过它几乎可以找到所有的其它数据结构。

* `gtd->ses`: 当前会话。
* `gtd->level`: 当前调用层级相关数据。
* `gtd->screen`: 屏幕尺寸相关数据。
* `gtd->script_stack` / `gtd->script_index`: 调用栈。
* `gtd->vars`: 存储 `%0~%99`。
* `gtd->args`: 还是 `%0~%99`，指向 `gtd->vars`。
* `gtd->cmds`: 存储 `&0~&99`。
