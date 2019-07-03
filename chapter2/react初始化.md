# react初始化 #

简介: react是一个基于js的UI构建框架，它可以与其它UI框架共存于一个应用。使用react有两种方式：1.基于html引入，2.基于npm构建，前者适合临时使用一下react的组件和部分api，后者更适合构建一个完整的react应用。

####  基于HTML的初始化 ####
html构建react应用适合于临时使用一下react的api或者编写demo，具体步骤如下：

1. 新建demo2-1.html文件
### 
	<!DOCTYPE html>
	<html>
	  <head>
	    <meta charset="UTF-8" />
	    <title>Simple Demo</title>
	  </head>
	  <body>
	  </body>
	</html>
###
2. 通过script标签引入react包   
### 
	<!-- 开发模式使用development.js,以便于调试源码-->
	<script src="https://unpkg.com/react@16/umd/react.development.js" crossorigin></script>
	<script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js" crossorigin></script>
	
	<!-- 生产模式使用min.js, 缩小包的大小以便快速加载-->
	<!-- <script crossorigin src="https://unpkg.com/react@16/umd/react.production.min.js"></script>-->
	<!-- <script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.production.min.js"></script>-->
###
3. 配置babel使得程序可以使用jsx语法（react组件最高效的语法）  
### 
	<-- 这种引入babel方式及其不稳定， 不建议生产模式下使用 -->
	<script src="https://unpkg.com/babel-standalone@6.15.0/babel.min.js"></script>
###
4. 使用react api构建应用
### 
	// step1： 在body中添加一个容器元素作为react根元素
	<div id="root"></div>
	
	// step2: 添加js脚本，执行react-api构建react组件， 注意script标签type使用text/babel
	<script type="text/babel">
		ReactDom.render(
		  <h1>Hello React</h1>,
		  document.getElementById("root")
		)
	</script>
###

完成代码： demo2-1.html