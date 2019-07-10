# jsx介绍 #

简介： jsx（javascript-xml）是js语法的一种扩展，本质上是一种对象的表现形式，用于描述UI（dom元素信息）信息，为了写法便捷好记，因此采用了xml写法风格。

### 为什么使用 ###

在react中（或者其他支持jsx的ui框架中），元素或者组件都被标记为虚拟dom，虚拟dom只是一个包含了dom信息的对象，操作一个对象的开销很低，而jsx可以很好的表达出dom的结构和信息。

### 原理 ###

jsx语法本身不属于js和xml规范，jsx有自己的语法规范，并且jsx作为一种js语法扩展，不会内置于任何浏览器或者js引擎，因为这会破坏js规范和js执行标准。那么如果要使用jsx扩展语法，必须通过特定的预处理器（例如：babel）将其转变为标准的js语法。

jsx重点是描述元素信息，包括元素类型、属性、事件、子元素等，用对象的形式表达如下：
### 
	// 元素信息
	elementObj: {
		'elementType',   // 元素类型 div/h1...
		{...props},      // 元素属性
		{...children}    // 元素子节点对象
	}
###
支持jsx的ui框架会将jsx所描述的元素信息加载到virtual-dom中缓存，之后会在恰当的时间映射到真实的dom完成渲染。

### 规范 ###

**写法:** jsx采用了xml的写法风格，因此一个完整的jsx语法一定有成对的开闭符号--<></>  
### 
	const element = <div>元素类型及开闭符号一定要成对出现！</div>;
### 
**属性值:**jsx的属性采用赋值写法即： key=value， 其中value可以是任意合法的js表达式
### 
	const element = <div value="test">属性可以是任何js的表达式</div>;
	const element = <div value=1>属性可以是任何js的表达式</div>;
	const element = <div value=false>属性可以是任何js的表达式</div>;
	const element = <div value={expression}>属性可以是任何js的表达式</div>;
	const element = <div {...props}>属性可以是任何js的表达式</div>;
### 
**内容:**jsx内容可以是任何一个合法的js表达式或者一个jsx
### 
	const element = <div>属性可以是任何js的表达式</div>;
	const element = <div>{expression}</div>;
	const element = <div value=false>属性可以是任何js的表达式</div>;
	const element = <div><span>另一个jsx</span></div>;
###
[demo2-2](./demo2-2/a.jsx)简单展示了基于react映射的jsx语法