# AngularJS 模块

> - 模块定义了一个应用程序。

> - 模块是应用程序中不同部分的容器。

> - 模块是应用控制器的容器。

> - 控制器通常属于一个模块。

## 创建模块

> 通过 AngularJS 的 angular.module 函数来创建模块

```script
<div ng-app="myApp">...</div>
<script>
	var app = angular.module("myApp", []); 
</script>
```

> "myApp" 参数对应执行应用的 HTML 元素。

> 现在你可以在 AngularJS 应用中添加控制器，指令，过滤器等。

## 添加控制器

> 使用 ng-controller 指令来添加应用的控制器

```script
<div ng-app="myApp" ng-controller="myCtrl">
{{ firstName + " " + lastName }}
</div>

<script>
	var app = angular.module("myApp", []);
	app.controller("myCtrl", function($scope) {
		$scope.firstName = "John";
		$scope.lastName = "Doe";
	});
</script>
```

> __在模块定义中 [] 参数用于定义模块的依赖关系。__

> __中括号[]表示该模块没有依赖，如果有依赖的话会在中括号写上依赖的模块名字。__


## 添加指令

```script
<div ng-app="myApp" runoob-directive></div>

<script>
	var app = angular.module("myApp", []);
	app.directive("runoobDirective", function() {
		return {
			template : "我在指令构造器中创建!"
		};
	});
</script>
```

# AngularJS 表单(输入控件)

> - input 元素

> - select 元素

> - button 元素

> - textarea 元素

## 实例

```html
<div ng-app="myApp" ng-controller="formCtrl">
  <form novalidate>
    First Name:<br>
    <input type="text" ng-model="user.firstName"><br>
    Last Name:<br>
    <input type="text" ng-model="user.lastName">
    <br><br>
    <button ng-click="reset()">RESET</button>
  </form>
  <p>form = {{user}}</p>
  <p>master = {{master}}</p>
</div>

<script>
var app = angular.module('myApp', []);
app.controller('formCtrl', function($scope) {
    $scope.master = {firstName: "John", lastName: "Doe"};
    $scope.reset = function() {
        $scope.user = angular.copy($scope.master);
    };
    $scope.reset();
});
</script>
```
> --novalidate 属性是在 HTML5 中新增的。禁用了使用浏览器的默认验证。--

> - ng-app 指令定义了 AngularJS 应用。

> - ng-controller 指令定义了应用控制器。

> - ng-model 指令绑定了两个 input 元素到模型的 user 对象。

> - formCtrl 函数设置了 master 对象的初始值，并定义了 reset() 方法。

> - reset() 方法设置了 user 对象等于 master 对象。

> - ng-click 指令调用了 reset() 方法，且在点击按钮时调用。

> - novalidate 属性在应用中不是必须的，但是你需要在 AngularJS 表单中使用，用于重写标准的 HTML5 验证。

# AngularJS 输入验证(表单和控件的验证)

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<script src="http://cdn.static.runoob.com/libs/angular.js/1.4.6/angular.min.js"></script>
</head>
<body>

<h2>验证实例</h2>

<form ng-app="myApp" ng-controller="validateCtrl" 
name="myForm" novalidate>

<p>用户名:<br>
<input type="text" name="user" ng-model="user" required>
<span style="color:red" ng-show="myForm.user.$dirty && myForm.user.$invalid">
<span ng-show="myForm.user.$error.required">用户名是必须的。</span>
</span>
</p>

<p>邮箱:<br>
<input type="email" name="email" ng-model="email" required>
<span style="color:red" ng-show="myForm.email.$dirty && myForm.email.$invalid">
<span ng-show="myForm.email.$error.required">邮箱是必须的。</span>
<span ng-show="myForm.email.$error.email">非法的邮箱地址。</span>
</span>
</p>

<p>
<input type="submit"
ng-disabled="myForm.user.$dirty && myForm.user.$invalid ||  
myForm.email.$dirty && myForm.email.$invalid">
</p>

</form>

<script>
var app = angular.module('myApp', []);
app.controller('validateCtrl', function($scope) {
    $scope.user = 'John Doe';
    $scope.email = 'john.doe@gmail.com';
});
</script>

</body>
</html>
```
> AngularJS ng-model 指令用于绑定输入元素到模型中。

> 模型对象有两个属性： user 和 email。

> 我们使用了 ng-show指令， color:red 在邮件是 $dirty 或 $invalid 才显示。

> - $dirty	表单有填写记录

> - $valid	字段内容合法的

> - $invalid	字段内容是非法的

> - $pristine	表单没有填写记录