# React项目创建到部署到Github-Pages

### 项目创建

1. 环境

   ​	[node](https://nodejs.org/en/download/) >=10.16和node管理工具[yarn](https://yarn.bootcss.com/docs/install/#mac-stable)

2. Create React App

   官方提供的方法如下：

   ```shell
   npx create-react-app my-app
   cd my-app
   npm start
   ```

   

3. 查看webpack相关信息

   ````shell
   yarn eject
   ````

   

4. 删除文件从零开始

   * 将src下的所有文件都删除

   * 将public文件下除favicon.ico（应用程序顶部icon图标）和index.html（应用程序的入口文件）之外的文件都删除掉

   * 删除public->index.html中两个link标签

   * 编写代码

     在src目录下，创建一个index.js，手动导入React、ReactDOM

     ```js
     import React from "react";
     import ReactDOM from 'react-dom';
     
     ReactDOM.render(<h1>Hello React</h1>, document.getElementById("root"));
     ```

### 将项目部署到Github-Pages

1. 安装gh-pages

   ```shell
   npm install gh-pages --save-dev
   ```

   

2. 修改package.json

   * 新增homepage

     ```shell
     "name": "react_demo",
      "version": "1.1.0",
      "private": true,
      "homepage": "./",  //加上这一句
     ```

   * 新增deploy

     ```shell
     "scripts": {
             ...
          	"deploy": "gh-pages -d build" //加上这一句
     }
     ```

3. 推送项目

   * 编译

     ```shell
     yarn build
     ```

   * 推送

     ```shell
     yarn deploy
     ```

   完成以上操作后github上会多出一个叫gh-pages的分支，在设置中将Pages的分支选择为gh-pages分支，选择root保存，部署完成。

### 以上来自对下面两篇文章的整合

> [create-react-app项目部署到Github-Pages](https://segmentfault.com/a/1190000019290048)

> [Rect脚手架](https://zhuanlan.zhihu.com/p/149712752)