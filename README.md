# adminSystem #
基于Node.js+Express+mysql+webpack+Vue2 +vuex+axios+Element UI 的全栈后台管理系统解决方案

## 前言 ##
这是一套基于node.js开发的全栈MVC后台管理系统，也就是前端人员自己进行数据库的增删改查，输出API接口，然后通过代理，调用API接口进行页面展示。

在开发过程中，我们需要同时启动两套端口服务，一套是后端服务（Node.js+Express+mysql），搭建好node的运行环境，cd到项目根目录，输入命令 supervisor app.js启动（开发环境笔者喜欢用supervisor，便于修改，当然你也可以用forever或者PM2），启动后可以通过http://localhost:3000进行访问，一套是前端服务（webpack+Vue2+vuex+axios+Element UI），cd到项目根目录，输入npm run dev启动。后端服务主要是对数据库进行增删改查，输出API接口；前端服务主要是调用API接口，进行页面的展示。

此套系统，我们引入了Element UI，方便用户进行页面视图展示，当然还可以引用其他的UI系统，具体根据项目需要引入就行。

## 功能 ##
- [x] Node.js+Express+mysql
- [x] Element UI
- [x] 登录/注销
- [x] 表格
- [x] 表单
- [x] 图表 :bar_chart:
- [x] 富文本编辑器
- [x] markdown编辑器
- [x] 图片拖拽/裁剪上传
- [x] 支持切换主题色 :sparkles:
- [x] 列表拖拽排序


## 目录结构介绍 ##

	|-- build                            // webpack配置文件
	|-- config                           // 项目打包路径
	|-- routers 						 // API路由目录
	|-- views 						 	 // ejs模板目录
	|-- static 						 	 // 静态资源文件，包括图片、样式、js等
	|-- src                              // 源码目录
	|   |-- components                   // 组件
	|       |-- common                   // 公共组件
	|           |-- Header.vue           // 公共头部
	|           |-- Home.vue           	 // 公共路由入口
	|           |-- Sidebar.vue          // 公共左边栏
	|		|-- page                   	 // 主要路由页面
	|           |-- BaseCharts.vue       // 基础图表
	|           |-- BaseForm.vue         // 基础表单
	|           |-- BaseTable.vue        // 基础表格
	|           |-- Login.vue          	 // 登录
	|           |-- Markdown.vue         // markdown组件
	|           |-- Readme.vue           // 概述组件
	|           |-- Upload.vue           // 图片上传
	|           |-- VueEditor.vue        // 富文本编辑器
	|           |-- VueTable.vue         // vue表格组件
	|   |-- App.vue                      // 页面入口文件
	|   |-- main.js                      // 程序入口文件，加载各种公共组件
	|-- .babelrc                         // ES6语法编译配置
	|-- .editorconfig                    // 代码编写规格
	|-- .gitignore                       // 忽略的文件
	|-- index.html                       // 入口html文件
	|-- package.json                     // 项目及工具的依赖配置文件
	|-- README.md                        // 说明


## 安装步骤 ##

	复制adminSystem文件夹到相应的磁盘 ，以后提供git clone 下载     // 把模板下载到本地
	cd adminSystem    // 进入模板目录
	npm install       // 安装项目依赖，等待安装完成之后

## 本地开发 ##
	### 第一种方式 ###
	//001 开启服务器，浏览器访问 http://localhost:3000/testApi 或者http://localhost:3000/testApi/abc
	supervisor app 或者 npm start app

	//002 开启服务器，浏览器访问 http://localhost:8080
	npm run dev

	### 第二种方式（初次搭建建议采用） ###
	//001 执行构建命令，生成的dist文件夹
	npm run build

	//002 开启服务器，浏览器访问 http://localhost:3000 或者 http://localhost:3000/testApi 或者http://localhost:3000/testApi/abc
	supervisor app 或者 npm start app

	//003 开启服务器，浏览器访问 http://localhost:8080
	npm run dev

## 构建生产 ##
	// 执行构建命令，生成的dist文件夹放在服务器下即可访问
	npm run build
	
	//打包发布
	打包发布时候，src目录不需要发布

	//pm2线上访问 浏览器访问 http://项目域名
	pm2 start app
