# 服务端渲染 VS 客户端渲染

### 客户端渲染路线：

1. 请求一个html -
2.  服务端返回一个html 
3. 浏览器下载html里面的js/css文件 
4. 等待js文件下载完成 
5. 等待js加载并初始化完成 
6. js代码终于可以运行，由js代码向后端请求数据( ajax/fetch ) 
7. 等待后端数据返回 
8. react-dom( 客户端 )从无到完整地，把数据渲染为响应页面

服务端渲染路线：

1. 请求一个html 
2. 服务端请求数据( 内网请求快 ) 
3. 服务器初始渲染（服务端性能好，较快） 
4.  服务端返回已经有正确内容的页面 
5.  客户端请求js/css文件 
6.  等待js文件下载完成 
7.  等待js加载并初始化完成 
8. react-dom( 客户端 )把剩下一部分渲染完成( 内容小，渲染快 )