# npm install 报错整理

## 一.找不到Python执行文件

```
gyp ERR! configure error
gyp ERR! stack Error: Can't find Python executable "python", you can set the PYTHON env variable.
gyp ERR! stack     at PythonFinder.failNoPython (D:\guohang\code\ui-portal-Air\node_modules\node-gyp\lib\configure.js:484:19)
gyp ERR! stack     at PythonFinder.<anonymous> (D:\guohang\code\ui-portal-Air\node_modules\node-gyp\lib\configure.js:509:16)
gyp ERR! stack     at callback (D:\guohang\code\ui-portal-Air\node_modules\node-gyp\node_modules\graceful-fs\polyfills.js:295:20)
gyp ERR! stack     at FSReqWrap.oncomplete (fs.js:154:21)
gyp ERR! System Windows_NT 10.0.18362
gyp ERR! command "D:\\Program Files (x86)\\node\\node.exe" "D:\\guohang\\code\\ui-portal-Air\\node_modules\\node-gyp\\bin\\node-gyp.js" "rebuild" "--verbose" "--libsass_ext=" "--libsass_
cflags=" "--libsass_ldflags=" "--libsass_library="
gyp ERR! cwd D:\guohang\code\ui-portal-Air\node_modules\node-sass
gyp ERR! node -v v10.13.0
gyp ERR! node-gyp -v v3.8.0
gyp ERR! not ok
```


网上查找解决办法，执行如下语句就可以了

1.安装windows-build-tools

```
npm install --global --production windows-build-tools
```

2、安装node-gyp

```
npm install --global node-gyp
```



但是在安装windows-build-tools时就报错如下

```
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! windows-build-tools@5.2.2 postinstall: `node ./dist/index.js`
npm ERR! Exit status 1
npm ERR!
npm ERR! Failed at the windows-build-tools@5.2.2 postinstall script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     C:\Users\孔维敏\AppData\Roaming\npm-cache\_logs\2020-02-12T02_31_28_970Z-de

bug.log

```



## 二.版本不兼容

```
Node Sass does not yet support your current environment: Windows 64-bit with false
```

单独安装不兼容插件

```
npm install Node Sass
```





## 三.找不到相应模块

```
 FATAL Cannot find module 'XXXXXX'
```

单独安装相应模块

```
npm install XXXXXX
```

