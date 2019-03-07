#### vue项目出现闪现的问题

1.如果只是文本,在网页上刷新的时候出现“{{   }}”

代码如下：

```html
<div class="test">
    {{test}}
</div>
```

```js
date:{
    test:"test"
}
```

只需把HTML改为如下格式就完全ojbk了

```html
<div class="test" v-text="test">
</div>
```





2.如果是某个需要隐藏的div在刷新的时候闪现

# vue -- v-cloak解决刷新或者加载出现闪烁（显示变量）

2017年04月25日 10:35:22 [bobobocai](https://me.csdn.net/bobobocai) 阅读数：24393



版权声明：本文为博主原创文章，未经博主允许不得转载。	https://blog.csdn.net/bobobocai/article/details/70676951

在使用vue绑定数据的时候，渲染页面时会出现变量闪烁，例如



```
<div class="#app">
    <p>{{value.name}}</p>
</div>
```



在加载的时候会看到



```
{{value.name}}
```

在页面出现，过了几秒之后才会渲染数据，在vue中有个指令可以解决这个问题，v-cloak



那么，v-cloak要放在什么位置呢，是不是每个需要渲染数据的标签都要添加这个指令，经过试验发现，v-cloak并不需要添加到每个标签，只要在el挂载的标签上添加就可以，



```
<div class="#app" v-cloak>
    <p>{{value.name}}</p>
</div>
```

而且，在css里面要添加





```
[v-cloak] {
    display: none;
}
```

这样就可以防止页面闪烁了。



但是有的时候会不起作用，可能的原因有二：

1、v-cloak的display属性被层级更高的给覆盖掉了，所以要提高层级



```
[v-cloak] {
    display: none !important;
}
```



2、样式放在了@import引入的css文件中

v-cloak的这个样式放在@import 引入的css文件中不起作用，可以放在link引入的css文件里或者内联样式中

