整数 `1` ，浮点数 `1.2` ，字符 `'a'` ，字符串 `"abc"` , 逻辑类型 `true`
以及空元组类型 `()` 可以使用字面量表示。

整数（除十进制外）可以选择使用十六进制、八进制或者二进制表达。
十六进制、八进制或者二进制表达分别用前缀 `0x` ，`0o` 或 `0b` 表示。

为了提升可读性，数值字面量中可以插入下划线。例如：
`1_000` 和 `1000` 相同， `0.000_001` 和 `0.000001` 相同。

我们需要告诉编译器我们所使用的字面量的类型。 目前，
我们使用后缀 `u` 来指明字面量是一个无符号整数，
使用后缀 `i` 来说明字面量是一个有符号整数。在 [另一章节][type], 
中，我们会覆盖到类型系统的内容。并在在 [相应章节][type-literal]中
给出关于有类型标注的字面量（type annotating literals）的更多细节。

操作符及其优先级与[类C语言（C-like languages）][op-prec]都是一致的。

{literals.play}

[op-prec]: https://en.wikipedia.org/wiki/Operator_precedence#Programming_languages
[type]: /type.html
[type-literal]: /type/literals.html
