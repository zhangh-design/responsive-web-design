## head中meta参数

我们在开发一个网站时（通常会有 WEB和WAP）通常会设置很多的`meta`头信息，那我们先来了解下主流网站的一些设置。

先上一个 慕课网 的meta配置代码片段：

```
<meta charset="utf-8">
<title>慕课网-程序员的梦工厂</title>
<meta http-equiv="X-UA-Compatible" content="IE=edge, chrome=1">
<meta name="renderer" content="webkit" />
<meta name="mobile-agent" content="format=wml"; url="https://m.imooc.com/">
<link rel="alternate" media="only screen and (max-width: 640px)" href="https://m.imooc.com/">
<meta name="mobile-agent" content="format=xhtml"; url="https://m.imooc.com/">
<meta name="mobile-agent" content="format=html5"; url="https://m.imooc.com/">
<meta property="qc:admins" content="77103107776157736375" />
<meta property="wb:webmaster" content="c4f857219bfae3cb" />
<meta http-equiv="Access-Control-Allow-Origin" content="*" />
<meta http-equiv="Cache-Control" content="no-transform " />
<meta http-equiv="Cache-Control" content="no-siteapp" />
<link rel="dns-prefetch" href="//www.imooc.com" />
<link rel="dns-prefetch" href="//img.imooc.com" />
<link rel="dns-prefetch" href="//img.mukewang.com" />
<link rel="apple-touch-icon" sizes="76x76" href="/static/img/common/touch-icon-ipad.png">
<link rel="apple-touch-icon" sizes="120x120" href="/static/img/common/touch-icon-iphone-retina.png">
<link rel="apple-touch-icon" sizes="152x152" href="/static/img/common/touch-icon-ipad-retina.png">
<meta name="Keywords" content=""/>
<meta name="Description" content="慕课网（IMOOC）是IT技能学习平台。慕课网(IMOOC)提供了丰富的移动端开发、php开发、web前端、android开发以及html5等视频教程资源公开课。并且富有交互性及趣味性，你还可以和朋友一起编程。" />
<meta name="360-site-verification" content="efec9ca9c0c2bf49b8f54f8ea4626ea8" />
<meta name="baidu-site-verification" content="f81e4a13096b3a7cab15fe1d39773a4e"/>

```

京东商城的设置：

```
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes"/>
<link rel="dns-prefetch" href="//static.360buyimg.com"/>
<link rel="dns-prefetch" href="//misc.360buyimg.com"/>
<link rel="dns-prefetch" href="//img10.360buyimg.com"/>
<link rel="dns-prefetch" href="//img11.360buyimg.com"/>
<link rel="dns-prefetch" href="//img12.360buyimg.com"/>
<link rel="dns-prefetch" href="//img13.360buyimg.com"/>
<link rel="dns-prefetch" href="//img14.360buyimg.com"/>
<link rel="dns-prefetch" href="//img20.360buyimg.com"/>
<link rel="dns-prefetch" href="//img30.360buyimg.com"/>
<link rel="dns-prefetch" href="//d.3.cn"/>
<link rel="dns-prefetch" href="//d.jd.com"/>
<link rel="icon" href="//www.jd.com/favicon.ico" mce_href="//www.jd.com/favicon.ico" type="image/x-icon"/>
<meta name="Keywords" content="网上购物,网上商城,手机,笔记本,电脑,MP3,CD,VCD,DV,相机,数码,配件,手表,存储卡,京东"/>
```

[移动端h5页面meta标签设置](https://www.jianshu.com/p/9408557ea9a9)

[html5 各种头部、meta标签的功能介绍](https://www.jianshu.com/p/4d27e82b925b)

#### 我们来逐一分析下里面的 meta 标签的作用

规定 HTML 文档的字符编码

```
<meta charset="utf-8">
```

---

`IE=edge`告诉IE使用最新的引擎渲染网页（[这句代码可以改变360兼容模式下以何种版本的IE去渲染页面](https://www.cnblogs.com/nxl0908/p/7245837.html)）

chrome=1则可以激活Chrome Frame，这样写可以达到的效果是如果安装了GCF，则使用GCF来渲染页面，如果未安装GCF，则使用最高版本的IE内核进行渲染。（[谷歌内嵌浏览器框架GCF，这个插件可以让用户的IE浏览器外观不变，但用户在浏览网页时，实际上使用的是Google Chrome浏览器内核，而且支持IE6、7、8等多个版本的IE浏览器，谷歌这个墙角挖的真给力！](https://blog.csdn.net/ccfxue/article/details/70739646)）

```
<meta http-equiv="X-UA-Compatible" content="IE=edge, chrome=1">
```

---

[强制浏览器启用Chromium内核，为用户提供最好的使用体验。](https://blog.csdn.net/AiHuanhuan110/article/details/89090019)

通常和上一个属性一起结合使用，也就是最好两个都配置防止出现某一个不起作用。

```
<meta name="renderer" content="webkit"/>
```

---

[移动适配之网页Meta标注声明](https://www.yudouyudou.com/jiaochengheji/wangzhanjianshe/85.html)

[wml|xhtml|html5]——根据手机页的协议语言，选择其中的一种。

url=url——后者代表当前PC页所对应的手机页url

`https://m.imooc.com/`我们首先确定这是一个手机端的`url`地址不是pc网页端的`url`地址（pc端是`https://www.imooc.com/`）。

生效情况：标注Meta声明这一适配方案仅在百度移动搜索中生效，即只有当用户通过百度移动搜索访问站点时，适配才会生效;通过其他渠道则不生效

```
<meta name="mobile-agent" content="format=wml"; url="https://m.imooc.com/">
<meta name="mobile-agent" content="format=xhtml"; url="https://m.imooc.com/">
<meta name="mobile-agent" content="format=html5"; url="https://m.imooc.com/">
```

---

[移动站适配rel=alternate PC页和H5页适配标注](https://www.cnblogs.com/osfipin/p/5852037.html)

1.在pc版网页上，添加指向对应移动版网址的特殊链接rel="alternate"标记，这有助于百度发现网站的移动版网页所在的位置；

2.同时在移动版网页上，添加指向对应pc版网址的链接rel="canonical"标记。

```
<link rel="alternate" media="only screen and (max-width: 640px)" href="https://m.imooc.com/">
```

---

这个是让网站加入QQ登录接口，这段代码可放在<head></head>之间。
申请腾讯接口后，会得到这样的代码，加入接口之后，你的网站上面的注册登录功能，别人可以直接用QQ登录，省去注册的麻烦。

```
<meta property="qc:admins" content="77103107776157736375" />
```

微博登陆声明

```
<meta property="wb:webmaster" content="c4f857219bfae3cb" />
```

---

**Access-Control-Allow-Origin**

Access-Control-Allow-Origin是HTML5中定义的一种解决资源跨域的策略。

设置为 * 表示该资源谁都可以用

如果请求的url是静态的html页面，则需要在页面中添加meta标签代码

```
<meta http-equiv="Access-Control-Allow-Origin" content="*" />
```

---

[禁止百度转码](http://www.luoxiao123.cn/1357.html)

目前的互联网状况是WEB网远多于WAP网页，目前绝大多数移动端的浏览器都不能直接浏览WEB网页。为确保移动设备能顺利访问网页必须对WAP搜索结果中的WEB网页进行格式转换，转换为WAP网页，使其能在移动终端浏览器被浏览。

百度转码会去除WEB页面中不能在手机浏览器上浏览的内容和无法用WAP描述语言描述的部分内容，并将网页布局由2维布局适配为1维布局。

各大搜索引擎均拥有并提供类似转码技术。

注意：no-transform 后面有个空格，不知道是不是百度官方给的格式写错了。

```
<meta http-equiv="Cache-Control" content="no-transform " />
<meta http-equiv="Cache-Control" content="no-siteapp" />
```

---


页面缓存时间的最大值是0秒，目的是不让页面缓存，每次访问必须到服务器读取

我觉得开发时可能会用到

```
<meta http-equiv="Cache-Control"content="max-age=0"/>
```

---

[dns-prefetch—DNS预解析技术](https://www.51xuediannao.com/html5/dns-prefetch.html)

设置DNS预获取（dns-prefetch）有两个作用：

1.减少DNS的请求次数

2.进行DNS预先获取。

当网页打开时，浏览器会在加载网页时对网页中的域名进行解析缓存，这样在你单击当前网页中的连接时就无需进行DNS的解析，减少用户等待时间，提高用户体验。

```
<link rel="dns-prefetch" href="//www.imooc.com" />
<link rel="dns-prefetch" href="//img.imooc.com" />
<link rel="dns-prefetch" href="//img.mukewang.com" />
```

---

现今移动设备越来越多，苹果为iOS设备配备了apple-touch-icon私有属性，添加该属性，在iPhone,iPad,iTouch的safari浏览器上可以使用添加到主屏按钮将网站添加到主屏幕上，方便用户以后访问。实现方法是在HTML文档的<head>标签加入下面代码即可。

apple-touch-icon 标签支持sizes属性，可以用来放置对应不同的设备。

```
<link rel="apple-touch-icon" sizes="76x76" href="/static/img/common/touch-icon-ipad.png">
<link rel="apple-touch-icon" sizes="120x120" href="/static/img/common/touch-icon-iphone-retina.png">
<link rel="apple-touch-icon" sizes="152x152" href="/static/img/common/touch-icon-ipad-retina.png">
```

---

[meta SEO(给搜索引擎看的meta标签 name keywords)](https://www.cnblogs.com/xk1994/p/7879110.html)

1、Keywords (关键字)

说明：为搜索引擎提供的关键字列表

用法：`<Meta name="Keywords" Content="关键词1,关键词2，关键词3,关键词4,……">`

2、Description (简介)

说明：Description用来告诉搜索引擎你的网站主要内容。

用法：`<Meta name="Description" Content="你网页的简述">`

```
<meta name="Keywords" content="网上购物,网上商城,手机,笔记本,电脑,MP3,CD,VCD,DV,相机,数码,配件,手表,存储卡,京东"/>
<meta name="Description" content="慕课网（IMOOC）是IT技能学习平台。慕课网(IMOOC)提供了丰富的移动端开发、php开发、web前端、android开发以及html5等视频教程资源公开课。并且富有交互性及趣味性，你还可以和朋友一起编程。" />
```

---

baidu-site-verification是百度网址认证

baidu-site-verification
这个是百度认证你个人网站的啊，你登录百度站长工具后台，然后点认证站点，就有相应代码，你把它放到/header前面就可以了

360-site-verification 是360网址认证

有些网站也是没有设置这个`meta`的（京东pc网站），不影响使用，应该也是和seo有关系。

```
<meta name="360-site-verification" content="efec9ca9c0c2bf49b8f54f8ea4626ea8" />
<meta name="baidu-site-verification" content="f81e4a13096b3a7cab15fe1d39773a4e"/>
```

---

[link标签实现给网页标题前加一个小图标favicon.ico](https://www.cnblogs.com/zyl-Tara/p/8492109.html)

```
<link rel="icon" href="//www.jd.com/favicon.ico" mce_href="//www.jd.com/favicon.ico" type="image/x-icon"/>
```

```
<link rel="Shortcut Icon" href="./favicon.ico" type="image/x-icon">
```

---

content属性值 :

- width: 视口宽度

- height: 视口高度

- device-width：渲染表面的宽度，就是设备屏幕的宽度。

- device-height：渲染表面的高度，就是设备屏幕的高度。

- intial-scale:页面首次被显示是可视区域的缩放级别，取值1.0则页面按实际尺寸显示，无任何缩放

- maximum-scale=1.0, minimum-scale=1.0;可视区域的缩放级别，maximum-scale用户可将页面放大的程序，1.0将禁止用户放大到实际尺寸之上。

- user-scalable:是否可对页面进行缩放，no 禁止缩放

[京东PC端网站主页的设置]：

```
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes"/>
```

简书PC端网站主页的设置：

```
<meta name="viewport" content="width=device-width, initial-scale=1.0,user-scalable=no">
```

[百度手机端主页的设置](https://note.youdao.com/)：

```
<meta name="viewport" content="width=device-width,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no">
```


---

**背景:**

最近在做一个 vue 项目，项目中的一些图片来自外网，动态的赋值给src属性,结果加载不出来，如果拿上地址直接给src属性，可以加载出来, 查看控制台的network，错误信息为 403(forbidden)

**解决方案:**

在index.html的head标签内加上一个meta标签

```
<meta name="referrer" content="no-referrer"/>
```

---

Apple iOS 设备设置

```
<meta name=”apple-mobile-web-app-title” content=”标题”> iOS 设备 begin

<meta name=”apple-mobile-web-app-capable” content=”yes”/> 添加到主屏后的标题（iOS 6 新增）
```








