# 讲解
---

# index01.html

> 当网页加载完毕，AngularJS 自动开启

> `ng-app` 指令告诉 AngularJS，`<div>`元素是AngularJS 应用程序的所有者

> `ng-model` 指令把输入域的值绑定到应用程序变量name

> `ng-bind` 指令把应用程序变name绑定到某个段落的 innerHTML

> **如果您移除了`ng-app`指令，HTML 将直接把表达式显示出来，不会去计算表达式的结果**

---

# index02.html

> 表达式

> AngularJS 表达式 与 JavaScript 表达式

> - 类似于 JavaScript 表达式，AngularJS 表达式可以包含字母，操作符，变量。

> - 与 JavaScript 表达式不同，AngularJS 表达式可以写在 HTML 中。

> - 与 JavaScript 表达式不同，AngularJS 表达式不支持条件判断，循环及异常。

> - 与 JavaScript 表达式不同，AngularJS 表达式支持过滤器。

---

# index03.html

> AngularJS 应用

> AngularJS 模块定义应用:`var app = angular.module('myApp', []); // AngularJS 模块`

> AngularJS 控制器控制应用:
```javasrcipt
app.controller('myCtrl', function($scope) { // AngularJS 控制器
    $scope.firstName= "John";
    $scope.lastName= "Doe";
});
```
