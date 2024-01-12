# 文本替换❌

* `SUB_ARG` / `#line sub ARGUMENTS`: 替换参数，即 `%1~%99`。
* `SUB_BRA` / `#line sub BRACES`: 替换花括号，即 `{` 和 `}` 变为普通字符，不再拥有特殊含义。
* `SUB_CMD` / `#line sub COMMANDS`: 替换正则表达式捕获组，即 `&1~&99`。
* `SUB_VAR` / `#line sub VARIABLES`: 替换变量。包括 `$`、`*`、`&` 语法都受它控制。
* `SUB_FUN` / `#line sub FUNCTIONS`: 替换函数调用。
* `SUB_COL` / `#line sub COLORS`: 替换颜色代码，即 `<...>` 语法。参考 `#help colors`。
* `SUB_ESC` / `#line sub ESCAPES`: 替换转义字符。参考 `#help escape`。
* `SUB_EOL` / `#line sub EOL`: 在字符串末尾添加行结束符。实际的行结束符由 `#cursor flag EOL` 的值决定。
* `SUB_LNF` / `#line sub LNF`: 在字符串末尾添加 `LF`。
* `SUB_SEC` / `#line sub SECURE`: 安全模式，抑制大多数语法。
* `SUB_LIT`: `#line sub LITERAL`: 字面值，FIXME
* `SUB_NONE`: 什么也不替换。
* `SUB_SIL`: 保留，什么也不会发生。
