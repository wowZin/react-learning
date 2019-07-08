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

[完整代码： demo2-1.html](./demo2-1.html)

### 基于脚手架构建react-app ###

基于脚手架构建的react-app更加灵活，一个完整的脚手架可以快速高效的完成react的初始化的工作，同时开发者可以根据不同的需求进一步定制或者优化脚手架。以官方脚手架为例快速搭建一个react应用。

### 
	// 必要环境准备
	// 1.node.js 8.10+, 低版本也兼容，但是8.10已经是主流版本了
    // 2.npm 5.2+， npm5.2+才有npx命令，npx是npm自动搜索npm包中可执行脚本的命令
	
	// 开始安装并执行react官方脚手架
	npx create-react-app demo2-2
    cd demo2-2
	// 开发/调试应用
    npm start
	// 打包成静态资源-生产中使用
    // npm run build  
###

### 基于html vs 基于脚手架 ###

基于html优点:   
1. 基于html的构建方式更适合用于一些demo编辑      
2. 用于在其他框架里集成临时过渡方式    
基于html缺点:    
1. 加载react源码脚本时间较长，交互体验不好       
2. 灵活性差，几乎不可定制    
3. 实现热更新非常复杂，调试成本较高    

基于脚手架优点:    
1. 携带打包工具（webpack），生成代码更少   
2. 灵活性高，可定制度高    
3. 支持热更新（官方脚手架），调试方便    
4. 对三方库的引入更灵活    
基于脚手架缺点:    

1. 通常脚手架学习成本更高    