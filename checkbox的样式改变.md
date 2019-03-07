#### checkbox的样式改变

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>纯CSS3实现自定义美化复选框</title>
    <style type="text/css">
        label {
            position: relative;
            cursor: pointer;
        }

        input {
            cursor: pointer;
        }

        input:checked+.show-box {
            background: #2292f0;
        }

        .show-box {
            position: absolute;
            top: 0;
            left: 0;
            width: 16px;
            height: 16px;
            border-radius: 2px;
            border: 1px solid #2292f0;
            background: white;
        }

        .show-box:before {

            content: '';
            position: absolute;
            top: 2px;
            left: 6px;
            width: 3px;
            height: 8px;
            border: solid white;
            border-width: 0 2px 2px 0;
            transform: rotate(45deg);
        }
    </style>
</head>

<body>
    <label>
        <input type="checkbox" />
        <div class="show-box"></div>
    </label>
</body>

</html>
```

