# S-Captcha 验证码


### 在前端项目中集成 `S-Captcha`

1. 在 `html -> head` 中集成 `js` 和 `css` 资源
2. 在需要展示验证码的地方加入一个 `div` 标签
3. 页面加载完成后，调用 `SCaptcha` 接口来生成验证码

### javascript `SCaptcha` 接口

`SCaptcha` 作为 javascript class 提供给外部调用，对其进行实例化即可自动生成验证码。

```javascript
var options = { 
    businessid: "xxx",
    element: xxx       // HTMLElement 类型，
    callback
};
new SCaptcha(options);
```

`SCaptcha` 类构造器接收一个 `object` 做为参数

- `businessid`: 业务 ID
- `element`: 需要展示验证码的 `div` 对象
- `callback`: 验证完成后的回调函数



### 一个简单的样例

```html
<html>
    <head>
        <script src="http://796b1128a51578da.safepoint.s-captcha-r1.com/v1/static/web.js"></script>
        <link rel="stylesheet" type="text/css" href="http://796b1128a51578da.safepoint.s-captcha-r1.com/v1/static/web.css">
    </head>
    <body>
        <div id="s-captcha"></div>
        <script>
            new SCaptcha({
                "businessid": 'business-id', 
                "element": document.getElementById('s-captcha'),
                "callback":  (err, msg, token) => {
                    console.log(err, msg, token)
                }
            })
        </script>
    </body>
</html>
```

> 注意: js 和 css 是在线动态生成的，请不要保存到本地
