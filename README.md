# 打包工具 webpack&Parcel

## webpack

- webpack 是一种前端资源构建工具，是一个静态模块打包器。
将一些浏览器识别不了语法，统一整合成浏览器可以识别的语法。解决了分别编译费时费力的问题。
将一些样式、字体、图片等资源与引入资源的js文件做成关系依赖图，形成chunk块，再对块进行处理，经过打包，形成bundle。

- webpack 有五个核心的概念。 entry、output、loader、plugins。 
入口entry（以哪个文件为入口起点开始打包，分析构建内部依赖图）
出口output（webpack打包后的资源bundles输出到哪里去，以及如何命名）
加载loader（让webpack能够去处理非JavaScript文件）
插件plugins（用于执行范围更广的任务）
模式mode（开发/生产）
因为有着这些概念，webpack是高度可配置的。

---
	/*
	  index.js：webpack入口起点文件
	  输出到 ./build/built.js
	  webpack ./src/index.js -o ./build/built.js --mode=development
	*/
	function add(x, y){
		return x + y;
	}

	console.log(add(1, 2));

---

## parcel
- 相比webpack, parcel在使用上更为简单。parcel不需要安装任何插件，也不需要进行配置。
parcel支持许多开箱即用的转换器和内置的编译器。

- 例如可以使用 Babel 转换 JavaScript ，使用 PostCSS 转换 CSS ，使用 PostHTML 转换 HTML。
***


# ES6

## 1.变量的解构赋值

解构本质上来说，就是模式的匹配。按照一定模式，从数组和对象中提取值，对变量进行赋值。
只要等号两边的模式相同，左边的变量就会被赋予对应的值。

### 解构的简单应用

- 交换变量的值

- 从函数中返回多个值

- 提取json    //没用过， 不太懂用这个做什么


	let jsonData = {
		id:42,
		status:"OK",
		data:[876, 5309],
	}

	let {id, status, data, number} = jsonData;

- map的遍历    //也没看太懂

---
	var map=new Map()
	map.set('fist','hello');
	map.set('second','world');
	for(let [key, value] of map){
		console.log(key, value);
	}

	// 只遍历key
	for(let [key] of map){
		console.log(key);
	}

	// 只遍历value
	for(let [, value] of value){
		console.log(value);
	}
---  
***

## 2.数组的扩展

- 扩展运算符与正常的函数参数可以结合使用，扩展运算符后面还可以放置表达式。

- 扩展运算符的应用 
（1）复制数组
（2）合并数组
（3）与解构赋值结合
（4）字符串
（5）实现了 Iterator 接口的对象
（6）Map 和 Set 结构，Generator 函数

- Array.from方法用于将类似数组的对象和可遍历的对象转为真正的数组

- Array.of方法用于将一组值，转换为数组。

- copyWithin()方法，在当前数组内部，将指定位置的成员复制到其他位置（会覆盖原有成员），然后返回当前数组。
- find方法，用于找出第一个符合条件的数组成员。

- fill方法使用给定值，填充一个数组。

## 3.对象的扩展
- ES6 允许在大括号里面，直接写入变量和函数，作为对象的属性和方法。这样的书写更加简洁。

## 4.函数的扩展
- ES6 允许为函数的参数设置默认值，即直接写在参数定义的后面。

## 5.对象的新增方法
- ES6 提出“Same-value equality”（同值相等）算法
Object.is就是部署这个算法的新方法。它用来比较两个值是否严格相等，与严格比较运算符（===）的行为基本一致。

- Object.assign()方法用于对象的合并，将源对象（source）的所有可枚举属性，复制到目标对象（target）。


## 6.Promise
- Promise是一个容器，里面保存着某个未来才会结束的事件（通常是一个异步操作）的结果。

- 从语法上说，Promise 是一个对象，从它可以获取异步操作的消息。Promise 提供统一的 API，各种异步操作都可以用同样的方法进行处理。
***

# JS 语法转换插件 babel

- babel是一个JavaScript编译器

- 主要用于将ES6版本的代码转换为向后兼容的 JavaScript 语法，以便能够运行在当前和旧版本的浏览器或其他环境中

- 编译过程分为三个阶段：解析、转换和生成。

- babel 本身不具有任何转化功能，需要配置插件，转化的功能会被分配到一个个plugin里。

- 插件分为语法插件和转译插件

  语法插件让babel能够解析更多种语法而不报错。
  
  转译插件则是把源码转换为我们需要的形式并输出。

- 配置插件时需要两步

  1.将插件的名字增加到配置文件中 (根目录下创建 .babelrc 或者 package.json 的 babel 里面，格式相同)
  
  2.使用 npm install babel-plugin-xxx 进行安装

***

#antd

- antd 是基于 Ant Design 设计体系的 React UI 组件库

- form表单
高性能表单控件，自带数据域管理。包含数据录入、校验以及对应样式。

- list列表
可承载文字、列表、图片、段落，常用于后台数据展示页面。

- table表格
展现大量结构化的数据
对数据进行排序、搜索、分页、自定义操作等复杂行为



***
#dva

- dva是react的轻框架

- dva = React-Router + Redux + Redux-saga

- 核心概念
State：一个对象，保存整个应用状态
View：React 组件构成的视图层
Action：一个对象，描述事件
connect 方法：一个函数，绑定 State 到 View
dispatch 方法：一个函数，发送 Action 到 State

//后续部分看不懂

***

#nvm

- nvm是一个nodejs的版本管理工具。通过它可以安装和切换不同版本的nodejs。

#npx

- 用途：使用npx可以在命令行直接执行本地已安装的依赖包命令

- npx的原理，就是在运行它时，执行下列流程：

  1.去node_modules/.bin路径检查npx后的命令是否存在，找到之后执行；
  
  2.找不到，就去环境变量$PATH里面，检查npx后的命令是否存在，找到之后执行;
  
  3.还是找不到，自动下载一个临时的依赖包最新版本在一个临时目录，然后再运行命令，运行完之后删除，     不污染全局环境。
***


#node 

- nodejs遵循了CommonJS规范

- CommonJS就是一个JavaScript模块化的规范，该规范最初是用在服务器端的node的，前端的webpack也是对   CommonJS原生支持的。

- 根据这个规范，每一个文件就是一个模块，其内部定义的变量是属于这个模块的，不会对外暴露，也就是说不会污染全局变量。

- CommonJS的核心思想就是通过 require 方法来同步加载所要依赖的其他模块，然后通过 exports 或者     module.exports 来导出需要暴露的接口。
***
- 优点：
CommonJS规范在服务器端率先完成了JavaScript的模块化，解决了依赖、全局变量污染的问题，这也是js运行在服务器端的必要条件。

- 缺点：
由于 CommonJS 是同步加载模块的，在服务器端，文件都是保存在硬盘上，所以同步加载没有问题
但是对于浏览器端，需要将文件从服务器端请求过来，那么同步加载就不适用了，所以，CommonJS是不适用于浏览器端的
***
#node和ES6的模块区别：

https://blog.csdn.net/sinat_31900531/article/details/88691196
https://www.jianshu.com/p/fa4a86ce4c72
//一点都看不懂



***
#fs：  
- fs 模块提供了用于与文件系统进行交互（以类似于标准 POSIX 函数的方式）的 API。
所有的文件系统操作都具有同步和异步的形式。

- 大多数 fs 操作接受的文件路径可以指定为字符串、Buffer、或 URL 对象（使用 file: 协议）。

- 字符串形式的路径会被解释为 UTF-8 字符序列（标识绝对或相对的文件名）。 相对路径会相对于当前工作目录（由 process.cwd() 指定）进行处理。

- 对于大多数 fs 模块的函数， path 或 filename 参数可以传入 WHATWG URL 对象。 仅支持使用 file: 协议的 URL 对象。
***
#path：
- path 模块提供了一些实用工具，用于处理文件和目录的路径。

- module：在 Node.js 模块系统中，每个文件都被视为一个独立的模块。

- 模块内的本地变量是私有的，因为模块由 Node.js 封装在一个函数中

- Node.js 直接运行一个文件时， require.main 会被设为它的 module。 
这意味着可以通过 require.main === module 来判断一个文件是否被直接运行
  ***      

#eslint

- ESLint是一个用来检查代码的工具，可以让程序员在编码的过程中发现问题。

- ESLint 使用 Espree 解析 JavaScript。

- ESLint 使用 AST 去分析代码中的模式。

- ESLint 是完全插件化的。每一个规则都是一个插件并且你可以在运行时添加更多的规则。
***
###ESlint的特点

- 内置规则和自定义规则共用一套规则 API。

- 内置的格式化方法和自定义的格式化方法共用一套格式化 API。

- 额外的规则和格式化方法能够在运行时指定。

- 规则和对应的格式化方法并不强制捆绑使用。

- 每条规则都是各自独立的，可以根据项目情况选择开启或关闭。

- 用户可以将结果设置成警告或者错误。

- ESLint 并不推荐任何编码风格，规则是自由的。

- 所有内置规则都是泛化的。

***

#TSlint

- TSLint是可扩展的静态分析工具，用于检查TypeScript代码的可读性，可维护性和功能性错误。
  并且可以使用自己的lint规则，配置和格式化程序进行自定义。

