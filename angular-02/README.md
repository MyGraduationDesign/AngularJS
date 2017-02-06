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