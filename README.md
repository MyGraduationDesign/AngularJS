# AngularJS
AngularJS Learning
---
# AngularJS指令(ng作为前缀[])
AngularJS 通过 ng-directives 扩展了 HTML。

**
HTML5 允许扩展的（自制的）属性，以 data- 开头。
AngularJS 属性以 ng- 开头，但可以使用 `data-ng-` 来让网页对 HTML5 有效。
**

> `ng-app` 指令定义一个 AngularJS 应用程序

> `ng-model` 指令把元素值（比如输入域的值）绑定到应用程序

> `ng-bind` 指令把应用程序数据绑定到 HTML 视图

> `ng-init` 指令初始化 AngularJS 应用程序变量

---

# AngularJS功能

> - AngularJS 把应用程序数据绑定到 HTML 元素

> - AngularJS 可以克隆和重复 HTML 元素

> - AngularJS 可以隐藏和显示 HTML 元素

> - AngularJS 可以在 HTML 元素"背后"添加代码

> - AngularJS 支持输入验证

---

# AngularJS表达式

> - AngularJS 表达式写在双大括号内：{{ expression }}

> - AngularJS 表达式把数据绑定到 HTML，这与 ng-bind 指令有异曲同工之妙

> - AngularJS 将在表达式书写的位置"输出"数据

> - AngularJS 表达式 很像 JavaScript 表达式：它们可以包含文字、运算符和变量

---

# AngularJS应用

> - AngularJS 模块（Module） 定义了 AngularJS 应用

> - AngularJS 控制器（Controller） 用于控制 AngularJS 应用

> - `ng-app`指令定义了应用, ng-controller 定义了控制器