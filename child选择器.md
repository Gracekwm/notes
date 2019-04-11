### css child选择器妙用：倒数第n，奇数列，偶数列，倍数列，第n个到最后，第一个到n

1、first-child

first-child表示选择列表中的第一个标签。

2、last-child

last-child表示选择列表中的最后一个标签

3、nth-child(3)

表示选择列表中的第3个标签，上面代码中的3也可以改成其它数字，如4、5等。想选择第几个标签，就填写几。

4、nth-child(2n)  倍数列可以是3,4,5...........n

这个表示选择列表中的偶数标签，即选择 第2、第4、第6…… 标签。

5.nth-child(even)

同4系数为2时，这个表示选择列表中的偶数标签，即选择 第2、第4、第6…… 标签。

6、nth-child(2n-1)

这个表示选择列表中的奇数标签，即选择 第1、第3、第5、第7……标签。

7、nth-child(odd)

同6系数为2时，这个表示选择列表中的奇数标签，即选择 第1、第3、第5、第7……标签。

8、nth-child(n+3)

这个表示选择列表中的标签从第3个开始到最后。

9、nth-child(-n+3)

这个表示选择列表中的标签从0到3，即小于3的标签。

10、nth-last-child()

这个表示选择列表中的倒数第n个标签。

示例:

```html
<!DOCTYPE html>
<html>
<head>
<style> 
p:nth-last-child(2)
{
background:#ff0000;
}
</style>
</head>
<body>

<h1>这是标题</h1>
<p>第一个段落。</p>
<p>第二个段落。</p>
<p>第三个段落。</p>
<div>第四个段落。</div>
<p>第五个段落。</p>

</body>
</html>
<!--没有元素改变颜色-->
```



11、 :nth-last-of-type() 

规定属于其父元素的第二个子元素的每个 p 元素，从最后一个子元素开始计数：          

```html
<!DOCTYPE html>
<html>
<head>
<style> 
p:nth-last-of-type(2)
{
background:#ff0000;
}
</style>
</head>
<body>

<h1>这是标题</h1>
<p>第一个段落。</p>
<p>第二个段落。</p>
<p>第三个段落。</p><!--红色背景-->
<div>第四个段落。</div>
<p>第五个段落。</p>

</body>
</html>
```

​           