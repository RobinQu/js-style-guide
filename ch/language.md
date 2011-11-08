语言规则
=======

* 总是使用var声明变量: *Always*
* **NAMES_LIKE_THIS** 作为常量声明. 使用 **@const** 标记. 避免使用const关键字
* *Always* 使用分号结尾.
* 不要在｛｝代码块内部申明函数，应使用var变量声明函数: *Never*
* 优先使用标准功能: *Always*
* 禁止使用Object、Array等基础对象构造函数: *Never*
* 多层的prototype继承: *Not-preferred*
* 闭包: *Careful*
* eval(): *Not-preferred*
* with(): *Never*
* **this** keyword: *Careful*
* for-in-loop: *Careful*
* 关联数组: *Never*
* 多行字符串: *Never*
* 修改原生对象的prototype: *Never*
* 一个作用域内只使用一个var *Always*
* 当与0或空字符串比较时，[使用===](https://developer.mozilla.org/en/JavaScript/Reference/Operators/Comparison_Operators) *Always*