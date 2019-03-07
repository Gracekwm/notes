## vue之vue-cookies安装使用以及注意事项

### 安装

```
npm install vue-cookies --save
```

在main.js引入

```
import VueCookies from 'vue-cookies'//引入
Vue.use(VueCookies)//挂载
```

### 使用(api)	

#### $cookies.config() 全局配置

```
$cookies.config(expireTimes[,path])  // default: expireTimes = 1d , path=/

```

> //**expireTimes** cookie有效时间,默认1d(可以为到期时间点，也可以为有效时间段，
>
> 在vue-cookies中传入**Infinity||-1**被认该cookie**永久有效**，传入**'0'**则**关闭浏览器的时候销毁cookie)**
> //**path** 默认'/',设置path: '/projectName/'指定项目名下'/projectName/'使用

**示例**

```
this.$cookies.config('30d')//30天后过期
window.$cookies.config('30d')//30天后过期
this.$cookies.config(new Date(2019,03,13).toUTCString())//2019年3月13日过期
this.$cookies.config(60 * 60 * 24 * 30,'');//30天后过期，cookie所在目录为默认 '/' 根目录
```

#### $cookies.set() 设置一个cookie

```
$cookies.set(keyName, value[, expireTimes[, path[, domain[, secure]]]])   //return this
```

> **key:** cookie名
>  注意 *$cookies key names Cannot be set to ['expires', 'max-age', 'path', 'domain', 'secure']* 
>
>  **value:** cookie值
>  vue-cookie会自动帮你把对象转为json *if (value && value.constructor === Object ){value = JSON.stringify(value)}* 
>
>  **expireTimes:** cookie有效时间，默认时间为1d
>  可以为到期时间点，也可以为有效时间段，在vue-cookies中传入Infinity||-1被认该cookie永久有效，传入'0'则关闭浏览器的时候销毁cookie
>
>  **path:** cookie所在目录，默认 '/' 根目录
>  设置path: '/projectName/'指定项目名下'/projectName/'使用
>
>  **domain:** cookie所在的域，默认为请求地址
>
>  **secure:** Secure属性是说如果一个cookie被设置了Secure=true，那么这个cookie只能用https协议发送给服务器，用http协议不发送。



#### $cookies.get()  获取一个cookie

```
$cookies.get(keyName)  // return value 
```

#### $cookies.remove()  删除一个cookie

```
$cookies.remove(keyName [, path [, domain]])  // return this
```

#### $cookies.isKey()  某个cookie是否存在

```
$cookies.isKey(keyName)  // return false or true
```

#### $cookies.keys()  设置一个cookie  获取所有cookie名

```
this.$cookies.keys()  // return a array
```

#### 注意

> **过期时间** 单位默认是秒
>
> 可以使用 y,m,d,h,min,s;**不能同时使用两个单位**
>
> **$cookies 的key**值不能设置为 ['expires','max-age','path','domain','secure']

参考：https://www.npmjs.com/package/vue-cookies