#### Vue 环境搭建

安装node.js

安装npm

安装vue-cli

用webpa创建一个带有vue环境的文件夹

进入文件夹

执行 npm run dev

## 第一步 node环境安装

1.1 如果本机没有安装node运行环境，请下载node 安装包进行安装
1.2 如果本机已经安装node的运行换，请更新至最新的node 版本
下载地址：<https://nodejs.org/en/> 或者 <http://nodejs.cn/>或者http://nodejs.cn/download/（中文网，个人看不懂英文，直接进这个最方便）

## 第二步 node环境检测

为了快乐的使用命令行，我们推荐使用 gitbas
1.1 下载git 并安装
下载地址 [https://git-for-windows.githu...](https://git-for-windows.github.io/)
安装成功后 右键菜单

我们可以看到 Gti Bash Here 。说明我们已经安装成功git
1.2 检测node 是否安装成功
右键空白，选择 Gti Bash Here 

1.2.1 在终端输入 node -v查看版本号

如果输出版本号，说明我们安装node 环境成功
随便我们可以查看 npm 的 版本号
可以使用 npm -v



## 第三步 vue-cli脚手架安装

2.1 如果访问外网比较慢，可以使用淘宝的镜像 <https://npm.taobao.org/>
打开命令终端 npm install -g cnpm --registry=[https://registry.npm.taobao.org](https://registry.npm.taobao.org/)
回车之后，我就可以可以快乐的用 cnpm 替代 npm

恭喜你，你已经成功安装了 cnpm
但是此后，我们还是使用 npm 来运行命令

2.2 接下来就是重点了 安装vue-cli
npm install vue-cli -g

2.3 进入我们的项目目录，右键 Gti Bash Here
2.4 初始化项目 vue init webpack vue-demo

一直回车直到

是否要安装 vue-router 项目中肯定要使用到 所以 y 回车

是否需要 js 语法检测 目前我们不需要 所以 n 回车

是否安装 单元测试工具 目前我们不需要 所以 n 回车

是否需要 端到端测试工具 目前我们不需要 所以 n 回车

接下来 ctr+c 结束

2.5 进入 cd vue-demo

2.6 执行 npm install

如果出现下图，说明安装成功

2.7 接下来执行 npm run dev

默认浏览器会自动打开

> `注意：如果您的浏览器是ie9以下的版本，请升级浏览器到最新版本或者下载谷歌浏览器或者火狐浏览器进行预览。在地址栏输入 http://localhost:8080/#/进行访问

恭喜，你已经成功安装，并运行起来vue基础项目，踏入了vue的大门。



vue项目搭建npm run dev 出现的问题 

出现 I Your application is running here: http://localhost:8083 
这句话的意思是你的程序在8083端口运行。 
解决办法：目录中config下的index.js修改如下： 

将autoOpenBrowser:false ;改为true 